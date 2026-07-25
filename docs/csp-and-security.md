# CSP and security

## Isolation model

- The loader runs on **your** origin.
- The wheel or box runs in a **SpinWheelPlus iframe** (`spinwheelplus.com`).
- Host CSS does not pierce the iframe; widget styles do not leak to your page.

SpinWheelPlus sets `Content-Security-Policy: frame-ancestors *` on embed routes so you may iframe them from any HTTPS or HTTP parent (subject to your own CSP).

## Host site Content-Security-Policy

If the widget never appears, your site may block third-party scripts or frames.

| Directive | Allows |
|-----------|--------|
| `script-src` | Loading `https://spinwheelplus.com/embed/v1/loader.js` |
| `frame-src` (or legacy `child-src`) | Embedding `https://spinwheelplus.com/embed/…` and `https://spinwheelplus.com/mystery-box/…/embed` |

Example header (adjust to your policy):

```http
Content-Security-Policy: script-src 'self' https://spinwheelplus.com; frame-src 'self' https://spinwheelplus.com;
```

WordPress security plugins, Shopify app firewalls, and corporate proxies often inject CSP — ask your admin to whitelist SpinWheelPlus.

## postMessage

When listening for spin results, **always** verify `event.origin` is your SpinWheelPlus domain before reading `event.data`.

The official loader does this before calling `data-on-result`.

## Ad blockers and privacy tools

Rarely block unknown third-party scripts. Test in a clean browser profile if the embed works on spinwheelplus.com but not on your domain.

## Secrets

Do not put API secrets in embed snippets. v1 embed is public iframe + optional client-side callbacks only.
