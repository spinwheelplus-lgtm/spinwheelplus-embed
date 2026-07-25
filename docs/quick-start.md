# Quick start

Use this page when you already have a published wheel or mystery box on [SpinWheelPlus](https://spinwheelplus.com).

**Copy-paste examples below** use live production content ([live examples](live-examples.md)):

- Wheel: [Birthday - my store](https://spinwheelplus.com/wheel/birthday-my-store-wks8vf) — slug `birthday-my-store-wks8vf`
- Mystery box: [Bookstore - Birthday](https://spinwheelplus.com/mystery-box/bookstore-birthday-8aj3sj) — slug `bookstore-birthday-8aj3sj`

## Before you embed

1. Save and publish your wheel or mystery box.
2. Enable **Allow embed** in publish settings.
3. Confirm the public page loads without a login.

If embed is disabled, the iframe shows an “embed not allowed” message.

## Option A — Copy from SpinWheelPlus (recommended)

- **Spin wheel:** open `/wheel/{slug}` → **Embed** → copy script or direct link.
- **Mystery box:** open `/mystery-box/{slug}` → **Embed** → copy script or direct link.

Copied snippets use your production domain from SpinWheelPlus (`NEXT_PUBLIC_SITE_URL` on their servers).

## Option B — Minimal script tag

### Spin wheel

```html
<div id="my-wheel"></div>
<script
  async
  src="https://spinwheelplus.com/embed/v1/loader.js"
  data-wheel="birthday-my-store-wks8vf"
  data-target="#my-wheel"
  data-mode="inline"
  data-width="400"
  data-height="400"
></script>
```

### Mystery box

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
></script>
```

## Option C — Iframe only (no loader)

Works for both products. You lose sidebar UI, host-page badge injection, and the loader’s `data-on-result` bridge (use `postMessage` for wheels — see [postMessage API](postmessage-api.md)).

**Wheel:**

```html
<iframe
  src="https://spinwheelplus.com/embed/birthday-my-store-wks8vf?sound=off&width=400&height=400&bg=brand"
  width="400"
  height="400"
  style="border:0;background:transparent"
  title="Spin wheel"
  loading="lazy"
  allow="autoplay"
></iframe>
```

**Mystery box:**

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

## Next steps

- [Spin wheel embed](spin-wheel.md) — sidebar mode and spin results
- [Mystery box embed](mystery-box.md) — layout and sizing tips
- [CSP & security](csp-and-security.md) — if nothing appears on your site
