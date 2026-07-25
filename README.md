<h1 align="center">SpinWheelPlus Embed</h1>

<p align="center">
  <img
    src="https://raw.githubusercontent.com/spinwheelplus-lgtm/spinwheelplus-embed/main/assets/images/banner-top.png"
    alt="SpinWheelPlus Embed"
    width="100%">
</p>

<p align="center">
  How to put a SpinWheelPlus spin wheel or mystery box on <strong>your</strong> website.
</p>

<p align="center">
  <a href="https://spinwheelplus.com">Make a wheel</a>
  ·
  <a href="https://spinwheelplus.com/mystery-box">Make a mystery box</a>
  ·
  <a href="#how-to-get-embed-code">Get embed code</a>
  ·
  <a href="docs/quick-start.md">Paste-ready snippets</a>
</p>

---

## What you’re embedding

Hosted wheels and mystery boxes from [spinwheelplus.com](https://spinwheelplus.com). You build them there; your site shows them through a small script or iframe.

<p align="center">
  <a href="https://spinwheelplus.com/wheel/birthday-my-store-wks8vf">
    <img
      src="https://raw.githubusercontent.com/spinwheelplus-lgtm/spinwheelplus-embed/main/assets/images/wheel.png"
      alt="Spin wheel on SpinWheelPlus"
      width="420">
  </a>
  &nbsp;&nbsp;
  <a href="https://spinwheelplus.com/mystery-box/bookstore-birthday-8aj3sj">
    <img
      src="https://raw.githubusercontent.com/spinwheelplus-lgtm/spinwheelplus-embed/main/assets/images/box.png"
      alt="Mystery box on SpinWheelPlus"
      width="420">
  </a>
</p>

<p align="center">
  <sub>
    <a href="https://spinwheelplus.com/wheel/birthday-my-store-wks8vf">Example wheel</a>
    ·
    <a href="https://spinwheelplus.com/mystery-box/bookstore-birthday-8aj3sj">Example mystery box</a>
  </sub>
</p>

| Product | Embed URL | Loader tag |
|---------|-----------|------------|
| Spin wheel | `/embed/{slug}` | `data-wheel="{slug}"` |
| Mystery box | `/mystery-box/{slug}/embed` | `data-box="{slug}"` |

Under the hood it’s **embed v1**: one loader (`/embed/v1/loader.js`) and an iframe. Your site’s CSS doesn’t leak in, and the widget’s styles don’t leak out.

---

## Do you need embed at all?

Usually **no**. Most teachers, streams, and small events just publish a wheel or box and **send the link**:

- `https://spinwheelplus.com/wheel/your-slug`
- `https://spinwheelplus.com/mystery-box/your-slug`

That’s the fastest path — no HTML, no developer.

**Embed** is for when you want the same wheel or box **inside** your own page: a shop site, a campaign landing, a school blog, an intranet article. Same product, just framed on your domain.

Who it’s for and when to link vs embed: [audiences and use cases](docs/audiences-and-use-cases.md).

Questions or doc fixes: [spinwheelplus@gmail.com](mailto:spinwheelplus@gmail.com)

---

## How to get embed code

Nothing in this repo generates a wheel for you. You always start on SpinWheelPlus:

```
Create on site  →  Customize  →  Save & publish  →  Open your detail page  →  Embed
```

### Spin wheel

| Step | Go here | Do this |
|:--:|---------|---------|
| 1 | [spinwheelplus.com](https://spinwheelplus.com/) | Add names in **Entries**. |
| 2 | Same page | **Customize** — look, sounds, weights, background. |
| 3 | Same page | **Save** (sign in if asked) → **Publish**. Turn on **Allow embed** if you’ll use it on another site. |
| 4 | `https://spinwheelplus.com/wheel/your-slug` | This is your public page. Click **Embed** (near Share) and copy the code. |
| 5 | Your website | Paste where you want the wheel. |

Live example for step 4: [Birthday - my store](https://spinwheelplus.com/wheel/birthday-my-store-wks8vf) → **Embed**.

You can spin on the homepage without publishing. Embed only works after publish, from `/wheel/{slug}`.

### Mystery box

| Step | Go here | Do this |
|:--:|---------|---------|
| 1 | [spinwheelplus.com/mystery-box](https://spinwheelplus.com/mystery-box) | Add prizes in **Entries**. |
| 2 | Same page | **Customize** — box style, sounds, how many opens per session, etc. |
| 3 | Same page | **Save** → **Publish** with **Allow embed** if needed. |
| 4 | `https://spinwheelplus.com/mystery-box/your-slug` | **Embed** on this page — not on the `/mystery-box` editor hub. |
| 5 | Your website | Paste the snippet. |

Live example: [Bookstore - Birthday](https://spinwheelplus.com/mystery-box/bookstore-birthday-8aj3sj) → **Embed**.

Longer walkthrough: [create and publish](docs/create-and-publish.md).

---

## Paste-ready code (spin wheel)

Already published? Turn on **Allow embed**, then copy from the wheel page or use:

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

Swap `birthday-my-store-wks8vf` for your slug.

---

## Paste-ready code (mystery box)

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

`data-on-result` and `postMessage` spin callbacks are for **wheels only** in v1. Mystery box play stays inside the iframe.

---

## All docs

| Doc | What it covers |
|-----|----------------|
| [Audiences and use cases](docs/audiences-and-use-cases.md) | Classrooms, marketing, events — link vs embed |
| [Create and publish](docs/create-and-publish.md) | Editor to detail page |
| [Live examples](docs/live-examples.md) | Slugs used in this repo |
| [Quick start](docs/quick-start.md) | Iframe-only options too |
| [Spin wheel](docs/spin-wheel.md) | Sidebar mode, results |
| [Mystery box](docs/mystery-box.md) | Sizing, panel |
| [Loader reference](docs/loader-reference.md) | Every `data-*` attribute |
| [Iframe query params](docs/iframe-query-params.md) | URL options |
| [postMessage API](docs/postmessage-api.md) | Wheel results on your page |
| [Requirements](docs/requirements.md) | Allow embed, visibility |
| [CSP & security](docs/csp-and-security.md) | When the widget is blocked |
| [Platforms](docs/platforms/wordpress.md) | WordPress, Shopify, WebView |

**HTML examples:** [wheel-inline](examples/wheel-inline/index.html) · [wheel-sidebar](examples/wheel-sidebar/index.html) · [mystery-box-inline](examples/mystery-box-inline/index.html) · [postMessage](examples/postmessage-parent.html)

---

## For crawlers and AI

[`llms.txt`](llms.txt) — short index of this repo.

---

## License

Docs and sample HTML here are [MIT](LICENSE). The running app and loader live on [spinwheelplus.com](https://spinwheelplus.com).

Doc feedback: [spinwheelplus@gmail.com](mailto:spinwheelplus@gmail.com)
