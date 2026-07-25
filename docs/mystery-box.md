# Mystery box embed

Embed a hosted mystery box (grid reveal randomizer) at **`/mystery-box/{slug}/embed`**.

The same **`/embed/v1/loader.js`** script supports mystery boxes via **`data-box`** instead of **`data-wheel`**.

Example content: [Bookstore - Birthday](https://spinwheelplus.com/mystery-box/bookstore-birthday-8aj3sj) (`bookstore-birthday-8aj3sj`).

## Inline embed

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
  data-chrome="minimal"
></script>
```

Mystery boxes often need **taller** embeds than wheels because of the prize grid and open animations. Start around 480×520 px and adjust after previewing on your page.

## Sidebar embed

Same attributes as spin wheels — use `data-box` and `data-mode="sidebar"`:

```html
<script
  async
  src="https://spinwheelplus.com/embed/v1/loader.js"
  data-box="bookstore-birthday-8aj3sj"
  data-mode="sidebar"
  data-position="right"
  data-width="400"
  data-collapsed="false"
  data-sound="on"
  data-logo="on"
></script>
```

## Entries panel

On the hosted marketing page, creators can hide the public entries side panel. That setting applies to embed and hosted play alike. There is no separate embed query flag for the panel in v1 — configure it when editing the box on SpinWheelPlus.

## Results and parent-page integration (v1)

**Spin wheels** can push each spin result to the host page via `data-on-result` or `postMessage`.

**Mystery box embed v1** does not emit `spinwheelplus:result` to the parent. Game state and reveals stay inside the iframe. Use hosted analytics on SpinWheelPlus or open the full box page if you need shareable logs.

## Direct iframe

```html
<iframe
  src="https://spinwheelplus.com/mystery-box/bookstore-birthday-8aj3sj/embed?sound=off&width=480&height=520&bg=brand"
  width="480"
  height="520"
  style="border:0;background:transparent"
  title="Mystery box"
  loading="lazy"
  allow="autoplay"
></iframe>
```

## Device play and refresh

Embed iframes use a separate device-play storage bucket from the hosted `/mystery-box/{slug}` page so refresh inside the embed does not share session limits with the marketing URL on the same browser.

## Related

- [Loader reference](loader-reference.md) — `data-box` vs `data-wheel`
- [Iframe query params](iframe-query-params.md)
- [Requirements](requirements.md)
