# Who this is for

SpinWheelPlus runs in the browser — free spin wheels and mystery boxes. These docs are in English for anyone, anywhere.

People use it for fair picks where others are watching: classrooms, small giveaways, team games, live streams, and “who goes first” moments. If trust matters, you want the draw to look and feel honest. That’s the point of the product.

## Who shows up

| Who | Typical use | Start here | Embed? |
|-----|-------------|------------|--------|
| Teachers & students | Names, groups, prompts, quick games | [Home](https://spinwheelplus.com/) or [Mystery box](https://spinwheelplus.com/mystery-box) | Usually just share a link |
| Small business & marketing | Promos, transparent draws on your site | Publish, then share or embed | Often embed on a landing or shop page |
| Events & teams | Prizes, internal fun, live reveals | Publish with clear rules | Link is enough; embed for a mini-site |
| Bloggers & landing pages | Interactive block inside one article | Publish → **Embed** | Yes |

## Link first (default)

After you publish, send people:

- `https://spinwheelplus.com/wheel/{slug}`
- `https://spinwheelplus.com/mystery-box/{slug}`

They open it in class, on Twitch, in WhatsApp — done. No code.

## When embed is worth it

Use embed when the wheel or box should sit **on your website** — same story as your brand, one scrollable page.

1. Build and publish on SpinWheelPlus ([create and publish](create-and-publish.md)).
2. On your **detail page** (`/wheel/…` or `/mystery-box/…`), hit **Embed** and paste on your site.

How-to for WordPress and the rest: [quick start](quick-start.md), [platforms](platforms/wordpress.md).

## Fair draws

We use **`crypto.getRandomValues()`** in the browser where the platform allows it — same family of API browsers use for security-sensitive randomness. You set weights and prizes; the audience sees what you configured. Linking to your public SpinWheelPlus page helps people double-check the same setup outside your embed.

## Forms and data

SpinWheelPlus doesn’t force a signup form on every wheel or box. **You** decide in settings — guest form, logs, limits, and so on. Whatever applies on the hosted page applies inside the embed too.

This GitHub repo is only documentation. It doesn’t collect user data.

## “Powered by” on your page

You can show or hide the small badge on the host site from embed settings (`data-logo` or the options in the **Embed** dialog). Details: [loader reference](loader-reference.md).

## Say hi

Doc ideas or something broken in the guide: **spinwheelplus@gmail.com**
