# Iframe query parameters

Both embed surfaces parse the same query string options:

- Spin wheel: `https://spinwheelplus.com/embed/{slug}?…`
- Mystery box: `https://spinwheelplus.com/mystery-box/{slug}/embed?…`

The loader builds these automatically from its `data-*` attributes.

## Parameters

| Param | Values | Default (bare URL) | Default (dialog copy) |
|-------|--------|--------------------|------------------------|
| `sound` | `on` \| `off` | `off` | `on` |
| `popup` | `on` \| `off` | `off` | `off` |
| `chrome` | `minimal` \| `full` | `minimal` | `minimal` |
| `title` | `on` \| `off` | `off` | `off` |
| `bg` | `transparent` \| `brand` \| `#rrggbb` | `transparent` | `brand` |
| `width` | 200–1200 | `400` | `400` |
| `height` | 200–1200 | `width` if omitted | `400` (inline) |
| `size` | 200–1200 | Legacy square alias | — |

**Not in iframe URL:** `logo`, `mode`, `position`, `collapsed`, `z-index` (loader-only).

## Two defaults contexts

If you paste a **direct iframe URL** manually, defaults match the “bare URL” column (quiet embed: sound off, transparent frame).

If you copy from the **SpinWheelPlus embed dialog**, defaults match the “dialog copy” column (sound on, brand frame, logo on host via loader).

## Sidebar layouts

When using the loader in sidebar mode, width/height query params follow inline rules for the iframe inside the panel; panel width comes from loader `data-width`.

## Frame background (`bg`)

| Value | Effect |
|-------|--------|
| `transparent` | Clear frame — blends with host page or custom wheel scene |
| `brand` | SpinWheelPlus gradient matting |
| `#rrggbb` | Solid color behind the widget |

Customize **page/scene** backgrounds on SpinWheelPlus are separate from this frame setting.

## Volume

Spin/tick/winner loudness uses wheel or box **Customize** sound settings, not URL params.
