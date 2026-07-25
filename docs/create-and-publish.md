# Create your wheel or mystery box, then embed

You don’t get embed code from GitHub. You make the wheel or box on [SpinWheelPlus](https://spinwheelplus.com), publish it, then either **share the link** (what most people do) or copy **Embed** from the detail page.

```
Editor  →  Customize  →  Save & publish  →  Detail page  →  Share link  OR  Embed on your site
```

---

## Spin wheel

| Step | Where | What to do |
|------|--------|------------|
| 1. Create | [Homepage editor](https://spinwheelplus.com/) | Names in **Entries**; **Customize** when you want design, sound, weights. |
| 2. Save | Side panel **Save** | Sign in to keep a hosted wheel on your account. |
| 3. Publish | Publish dialog | You get `/wheel/your-slug`. Enable **Allow embed** if another site will iframe it. |
| 4. Embed | `/wheel/{slug}` | **Embed** in the top actions → copy script or link. |
| 5. Your site | Your HTML | Paste. See [quick start](quick-start.md). |

Homepage spin works without publish. Embed needs a published slug and embed allowed.

---

## Mystery box

| Step | Where | What to do |
|------|--------|------------|
| 1. Create | [Mystery box hub](https://spinwheelplus.com/mystery-box) | Prizes in **Entries**; **Customize** for style, sound, session limits. |
| 2. Save | **Save** | Sign in for cloud save. |
| 3. Publish | Publish dialog | `/mystery-box/your-slug`; **Allow embed** for third-party sites. |
| 4. Embed | `/mystery-box/{slug}` | **Embed** → `data-box` snippet or iframe URL ending in `/embed`. |
| 5. Your site | Your page | Paste. See [mystery box embed](mystery-box.md). |

[/mystery-box](https://spinwheelplus.com/mystery-box) is the editor. Embed always targets **`/mystery-box/{slug}`**, not the hub.

---

## Settings that affect embed

| Setting | Effect |
|---------|--------|
| **Allow embed** | Off → visitors see “embed not allowed”. |
| Password / schedule / visibility | Same as the public page. |
| **Hide entries panel** (box) | Same on embed and hosted; no extra embed toggle in v1. |

---

## Next

- Tweaks: [loader reference](loader-reference.md), [iframe params](iframe-query-params.md)
- Sample slugs: [live examples](live-examples.md)
- Widget blocked? [CSP & security](csp-and-security.md)
