# SpinWheelPlus Embed — docs repo

Official **public** documentation for embedding spin wheels and mystery boxes. The running product lives at [spinwheelplus.com](https://spinwheelplus.com); loader and iframes are served from the Next.js app repo.

## Maintainer sync

When embed behavior changes in the main app:

1. Update `docs/embed-guide.md` and `docs/embed-spec.md` in the Next.js repo.
2. Mirror user-facing changes into this repo (`docs/`, `examples/`, `CHANGELOG.md`).
3. Bump `llms.txt` if canonical URLs or capabilities change.

## Publish to GitHub

```bash
cd spinwheelplus-embed
git init
git add .
git commit -m "docs: initial embed v1 documentation"
gh repo create spinwheelplus/spinwheelplus-embed --public --source=. --push
```

Adjust org/name if your GitHub account differs, then set `NEXT_PUBLIC_EMBED_DOCS_URL` on production to match.
