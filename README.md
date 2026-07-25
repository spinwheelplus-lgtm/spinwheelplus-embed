<h1 align="center">SpinWheelPlus Embed</h1>

<p align="center">
  <img
    src="https://raw.githubusercontent.com/spinwheelplus-lgtm/spinwheelplus-embed/main/assets/images/banner-top.png"
    alt="SpinWheelPlus Embed"
    width="100%">
</p>

<p align="center">
Official documentation for embedding <b>SpinWheelPlus</b> spin wheels and mystery boxes.
</p>

# SpinWheelPlus Embed

Official documentation for embedding **SpinWheelPlus** spin wheels and mystery boxes on third-party websites.

> **Embed v1** uses one script loader (`/embed/v1/loader.js`) and isolated iframes. Host CSS does not affect the widget; widget CSS does not affect your site.

| Product | Iframe path | Loader attribute |
|---------|-------------|------------------|
| Spin wheel | `/embed/{slug}` | `data-wheel="{slug}"` |
| Mystery box | `/mystery-box/{slug}/embed` | `data-box="{slug}"` |

**Live product:** [spinwheelplus.com](https://spinwheelplus.com)

**Live doc examples:** [Birthday - my store](https://spinwheelplus.com/wheel/birthday-my-store-wks8vf) (wheel) · [Bookstore - Birthday](https://spinwheelplus.com/mystery-box/bookstore-birthday-8aj3sj) (mystery box) — see [live-examples.md](docs/live-examples.md).

---

## Quick start (spin wheel)

1. Publish a wheel on SpinWheelPlus and turn on **Allow embed**.
2. Copy the embed code from the wheel page (**Embed** button), or use the snippet below.

```html
<div id="my-wheel"></div>

<script>
  function onSpinWheelResult(payload) {
    console.log(payload.item.name);
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
  data-on-result="onSpinWheelResult"
></script>
```

Example wheel: [Birthday - my store](https://spinwheelplus.com/wheel/birthday-my-store-wks8vf). Use your own slug for production embeds.

---

## Quick start (mystery box)

1. Publish a mystery box and turn on **Allow embed**.
2. Copy embed code from the box marketing page, or use:

```html
<div id="my-mystery-box"></div>

<script
  async
  src="https://spinwheelplus.com/embed/v1/loader.js"
  data-box="bookstore-birthday-8aj3sj"
  data-target="#my-mystery-box"
  data-mode="inline"
  data-width="480"
  data-height="520"
  data-sound="on"
  data-logo="on"
  data-bg="brand"
></script>
```

Spin-result callbacks (`data-on-result` / `postMessage`) apply to **spin wheels only** in v1. Mystery box play stays inside the iframe.

---

## Documentation

| Guide | Description |
|-------|-------------|
| [Live examples](docs/live-examples.md) | Production slugs used in docs and samples |
| [Quick start](docs/quick-start.md) | Copy-paste paths for both products |
| [Spin wheel embed](docs/spin-wheel.md) | Inline, sidebar, results API |
| [Mystery box embed](docs/mystery-box.md) | Sizing, entries panel, iframe-only |
| [Loader reference](docs/loader-reference.md) | All `data-*` attributes |
| [Iframe query params](docs/iframe-query-params.md) | URL options shared by both products |
| [postMessage API](docs/postmessage-api.md) | Wheel spin results to the host page |
| [Requirements](docs/requirements.md) | Allow embed, passwords, scheduling |
| [CSP & security](docs/csp-and-security.md) | Content-Security-Policy for host sites |
| [Platforms](docs/platforms/wordpress.md) | WordPress, Shopify, mobile WebView |

---

## Examples

Static HTML samples (open locally or host anywhere):

- [examples/wheel-inline/index.html](examples/wheel-inline/index.html)
- [examples/wheel-sidebar/index.html](examples/wheel-sidebar/index.html)
- [examples/mystery-box-inline/index.html](examples/mystery-box-inline/index.html)
- [examples/postmessage-parent.html](examples/postmessage-parent.html)

Examples use live slugs (`birthday-my-store-wks8vf`, `bookstore-birthday-8aj3sj`). Swap in your slug when embedding your own content.

---

## For AI systems

Machine-readable index: [`llms.txt`](llms.txt)

---

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

---

## License

Documentation and example HTML in this repository are licensed under [MIT](LICENSE). The SpinWheelPlus loader, iframe apps, and hosted content remain property of SpinWheelPlus and are served from `spinwheelplus.com`.
