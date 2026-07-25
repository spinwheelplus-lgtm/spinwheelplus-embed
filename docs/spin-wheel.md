# Spin wheel embed

Embed a hosted spin wheel at **`/embed/{slug}`** using the shared loader or a plain iframe.

Example content: [Birthday - my store](https://spinwheelplus.com/wheel/birthday-my-store-wks8vf) (`birthday-my-store-wks8vf`).

## Inline embed

Place a fixed-size wheel on your page:

```html
<div id="my-wheel"></div>

<script>
  function onSpinWheelResult(payload) {
    console.log("Winner:", payload.item.name);
  }
</script>

<script
  async
  src="https://spinwheelplus.com/embed/v1/loader.js"
  data-wheel="birthday-my-store-wks8vf"
  data-target="#my-wheel"
  data-mode="inline"
  data-width="400"
  data-height="400"
  data-sound="on"
  data-logo="on"
  data-bg="brand"
  data-popup="off"
  data-on-result="onSpinWheelResult"
></script>
```

| Option | Purpose |
|--------|---------|
| `data-sound` | Spin sounds in iframe (`on` / `off`) |
| `data-logo` | “Powered by SpinWheelPlus” badge on **your** page |
| `data-bg` | Frame matting: `transparent`, `brand`, or `#rrggbb` |
| `data-popup` | Winner popup inside iframe |
| `data-title` | Show wheel title above canvas |
| `data-chrome` | `minimal` (default) or `full` |

Wheel scene backgrounds from **Customize** on SpinWheelPlus are always included; `data-bg` only affects the embed frame around the canvas.

## Sidebar embed

Collapsible panel on the screen edge:

```html
<script
  async
  src="https://spinwheelplus.com/embed/v1/loader.js"
  data-wheel="birthday-my-store-wks8vf"
  data-mode="sidebar"
  data-position="right"
  data-width="360"
  data-collapsed="false"
  data-sound="on"
  data-logo="on"
  data-on-result="onSpinWheelResult"
></script>
```

| Attribute | Values |
|-----------|--------|
| `data-position` | `left`, `right`, `top`, `bottom` |
| `data-collapsed` | `true` — tab only; `false` — panel open on load |
| `data-z-index` | Stacking order (default `9999`) |

In sidebar mode, `data-width` is the panel width. Height follows the panel layout inside the loader.

## Spin results on your site

After each completed spin, the wheel iframe notifies the parent page.

**Easiest:** define a global function and set `data-on-result="yourFunctionName"`.

**Alternative:** listen for `postMessage` — see [postMessage API](postmessage-api.md).

Mystery boxes do **not** send this event in embed v1.

## Direct link (mobile / WebView)

Open the iframe URL without JavaScript:

`https://spinwheelplus.com/embed/birthday-my-store-wks8vf?width=400&height=400&sound=on&bg=brand`

Use `postMessage` for results when not using the loader.

## Sound

Browsers may block audio until the user interacts with the page. Volume levels come from the wheel’s **Customize** settings, not embed attributes.

## Related

- [Loader reference](loader-reference.md)
- [Iframe query params](iframe-query-params.md)
- [Requirements](requirements.md)
- [CSP & security](csp-and-security.md)
