# postMessage API (spin wheels)

When a user completes a spin inside an embedded **spin wheel** iframe, the iframe sends a message to `window.parent`.

**Mystery box embeds do not send this message in v1.**

## Message type

```text
spinwheelplus:result
```

## Payload

```json
{
  "type": "spinwheelplus:result",
  "version": 1,
  "slug": "birthday-my-store-wks8vf",
  "item": {
    "id": "entry-id",
    "name": "Alice",
    "index": 2
  }
}
```

| Field | Description |
|-------|-------------|
| `slug` | Wheel slug |
| `item.id` | Entry identifier from the wheel |
| `item.name` | Display label of the winning slice |
| `item.index` | Zero-based slice index |

## Option A — `data-on-result` (with loader)

```html
<script>
  function onSpinWheelResult(payload) {
    console.log(payload.item.name);
  }
</script>
<script
  async
  src="https://spinwheelplus.com/embed/v1/loader.js"
  data-wheel="birthday-my-store-wks8vf"
  data-on-result="onSpinWheelResult"
></script>
```

The loader checks `event.origin` matches the script host, then calls your function.

## Option B — Manual listener

Required for iframe-only embeds or custom integrations:

```javascript
window.addEventListener("message", function (event) {
  if (event.origin !== "https://spinwheelplus.com") return;
  if (!event.data || event.data.type !== "spinwheelplus:result") return;
  console.log("Winner:", event.data.item.name);
});
```

Always validate `event.origin` against your SpinWheelPlus domain.

## Versioning

`version` is `1` today. Future versions may add fields; ignore unknown keys in parsers.
