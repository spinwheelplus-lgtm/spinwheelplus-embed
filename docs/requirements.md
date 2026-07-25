# Requirements

## Allow embed

The wheel or mystery box owner must enable **Allow embed** when publishing.

If disabled:

- Spin wheel iframe shows an embed-denied state.
- Mystery box iframe shows an embed-denied state.

There is no public API key in v1 — access control is the publish flag plus normal page rules (password, schedule, visibility).

## Public access

Anonymous visitors can embed **public** wheels and boxes without logging into SpinWheelPlus.

Password-protected, scheduled, or draft content follows the same rules as on spinwheelplus.com. If the hosted page would block a visitor, the embed iframe will too.

## Slug

Use the slug from the public URL:

- Wheel: `https://spinwheelplus.com/wheel/{slug}`
- Box: `https://spinwheelplus.com/mystery-box/{slug}`

Embed paths use the same `{slug}` value.

## Attribution

`data-logo="on"` (default in dialog snippets) shows a “Powered by SpinWheelPlus” link on the host page. You may set `data-logo="off"`; please keep attribution when your site policy allows — it helps others discover fair random tools.

## Indexing

Embed iframe routes are `noindex`. SEO value stays on the marketing pages at `/wheel/{slug}` and `/mystery-box/{slug}`.

## Planned (not in v1)

- Per-wheel domain whitelist
- Embed analytics dashboard

See the product [CHANGELOG](../CHANGELOG.md) in this repo for documentation updates.
