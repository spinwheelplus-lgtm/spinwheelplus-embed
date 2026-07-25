# WordPress, Shopify, and mobile

## WordPress

### Custom HTML block

1. Edit page or post → add **Custom HTML** block.
2. Paste the embed snippet from SpinWheelPlus (or from [quick start](../quick-start.md)).
3. Publish and view the front end — the block editor preview may not execute third-party scripts.

### Classic editor

Use the **Text** tab and paste the full `<div>` + `<script>` block.

### CSP plugins

If you use Wordfence, Solid Security, or similar, add `spinwheelplus.com` to allowed script and frame sources. See [CSP & security](../csp-and-security.md).

## Shopify

1. **Online Store → Themes → Customize**.
2. Add a **Custom Liquid** or **HTML** section where the theme allows raw HTML.
3. Paste the loader snippet.
4. Some themes defer script execution — if the wheel is blank, try placing the script after the mount `<div>` as in our examples.

Shopify Content Security Policy may require whitelisting SpinWheelPlus in theme or app settings.

## Mobile apps and WebView

Skip the loader when you control the WebView:

```
https://spinwheelplus.com/embed/{slug}?width=400&height=400&sound=on&bg=brand
```

```
https://spinwheelplus.com/mystery-box/{slug}/embed?width=480&height=520&sound=on&bg=brand
```

For spin results without the loader, attach a `postMessage` handler in the native shell — see [postMessage API](../postmessage-api.md).

## iframe-only CMS embeds

Some CMS products only allow iframe embeds (no custom script). Use the iframe snippets from [quick start](../quick-start.md). Sidebar mode and `data-on-result` require the loader script.
