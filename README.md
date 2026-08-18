# wh2040-playbook — archived redirect shell

**This repo holds no content. Do not take data from it.**

The Implementation Playbook Navigator lives in the `wh2040` repo as a Next.js
route at `womenshealth2040.org/playbook`, with one page per named need at
`/playbook/<code>`. The canonical 28-need register is
`wh2040/src/data/activities.json`, which matches the published names in
`wh2040-facts → references/named-needs.md` exactly.

## What this repo is

A Vercel project whose only job is `vercel.json`: a 308 from
`wh2040-playbook.vercel.app` (and any path under it) to
`womenshealth2040.org/playbook`. It is kept deployed so old external links keep
resolving. There is no custom domain attached.

## What was removed, and why (18 Aug 2026)

- `data/activities.json`
- `data/activities-mapped.json`
- `public/index.html`

The two data files carried a **legacy generation of the register in which all 28
need names were wrong** — "Nordic Women's Health Research Career Program" where
the published Playbook says "Research career pipeline", and so on for the rest.
That generation circulated in the estate until 17 Aug 2026 and reached published
output before it was caught. It was also on a different schema
(`id` / `title` / `subtitle` / `loop` / `builds_on`), so nothing could safely
consume it anyway.

`public/index.html` was a 3,046-line standalone React + Babel navigator, two
generations behind the one that was itself replaced by the route in August 2026.
Nothing served it: the redirects catch every path before the output directory is
reached.

The icon PNGs under `public/` are duplicates of `wh2040/public/playbook/*.png`
and are kept only so the build has an output directory.

**Never take a need name from anywhere but the canonical register.**
