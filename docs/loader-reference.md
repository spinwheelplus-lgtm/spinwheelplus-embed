# Loader reference (`embed/v1/loader.js`)

Script URL: `https://spinwheelplus.com/embed/v1/loader.js` (replace domain if you self-host a white-label deployment).

## Product selector (required)

Set **exactly one** of:

| Attribute | Product |
|-----------|---------|
| `data-wheel="{slug}"` | Spin wheel → iframe `/embed/{slug}` |
| `data-box="{slug}"` | Mystery box → iframe `/mystery-box/{slug}/embed` |

Missing both logs a console error and does not mount.

## Layout

| Attribute | Values | Default |
|-----------|--------|---------|
| `data-mode` | `inline` \| `sidebar` | `inline` |
| `data-target` | CSS selector | Inline: element after script |
| `data-width` | 200–1200 px | `400` |
| `data-height` | 200–1200 px | Inline only; defaults to width |
| `data-size` | 200–1200 px | Legacy square alias — prefer width/height |

### Sidebar-only

| Attribute | Values | Default |
|-----------|--------|---------|
| `data-position` | `left` \| `right` \| `top` \| `bottom` | `right` |
| `data-collapsed` | `true` \| `false` | `true` if omitted |
| `data-z-index` | 1–99999 | `9999` |

When `data-collapsed="false"`, the panel opens on page load (matches **Auto-show** in the SpinWheelPlus embed dialog).

## Runtime options (passed into iframe query)

| Attribute | Values | Dialog default |
|-----------|--------|----------------|
| `data-sound` | `on` \| `off` | `on` |
| `data-popup` | `on` \| `off` | `off` |
| `data-chrome` | `minimal` \| `full` | `minimal` |
| `data-title` | `on` \| `off` | `off` |
| `data-bg` | `transparent` \| `brand` \| `#rrggbb` | `brand` |

## Host-page only (not in iframe URL)

| Attribute | Values | Default |
|-----------|--------|---------|
| `data-logo` | `on` \| `off` | `on` in copied snippets |
| `data-on-result` | Global function name | — (wheels only) |

### Branding badge (`data-logo="on"`)

The loader injects a real `<a href="https://spinwheelplus.com/">` on the **host document** (top-right of inline box or open sidebar panel):

- 16px logo icon
- Expands to “Powered by SpinWheelPlus” on hover or touch
- Hidden while a sidebar panel is collapsed

Set `data-logo="off"` to hide attribution on your page.

## Spin results (wheels)

`data-on-result="myCallback"` calls `window.myCallback(payload)` after each spin. The loader validates `postMessage` origin before invoking the callback.

See [postMessage API](postmessage-api.md) for the payload shape and manual listeners.

## Full inline example

```html
<div id="widget"></div>
<script>
  function myCallback(payload) {
    console.log(payload);
  }
</script>
<script
  async
  src="https://spinwheelplus.com/embed/v1/loader.js"
  data-wheel="birthday-my-store-wks8vf"
  data-target="#widget"
  data-mode="inline"
  data-width="400"
  data-height="400"
  data-sound="on"
  data-logo="on"
  data-bg="brand"
  data-on-result="myCallback"
></script>
```
