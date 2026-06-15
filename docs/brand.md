# Brand Book

The **canonical brand rules for the whole PezkuwiChain ecosystem** — apps,
websites, docs, and forks. Every repo should follow this page; repo-level files
(e.g. a wallet `BRAND.md`) should reference it rather than restate it.

## The one hard rule

!!! danger "Kurdistan palette only"
    Use **only** the Kurdistan palette — **kesk** (green), **sor** (red),
    **zer** (gold), **fire** (orange) — plus navy/neutral.
    **Pink, magenta and purple are forbidden — anywhere:** CSS/XML colors,
    Compose/`Color(0x…)` literals, gradients, vector drawables, **and raster
    images** (PNG/WebP banners and illustrations).

## Palette

| Role | Token | Hex |
|------|-------|-----|
| Primary | kesk | `#009639` |
| Primary dark | kesk-700 | `#017A2F` |
| Positive | positive | `#2FC864` |
| Danger | sor | `#E2231A` |
| Negative | negative | `#E53450` |
| Accent | zer | `#FDB813` |
| Warning | warning | `#EBC50A` |
| Highlight | fire | `#FF7A00` |
| Info | info | `#2AB0F2` |

**Backgrounds** — base `#05081C` · screen `#08090E` · elevated `#181920` · nav `#0F111A`
**Surfaces** — periwinkle tint `#999EC7` at 10% / 16% / 24%
**Text** — primary `#E0FFFFFF` · secondary `#7AFFFFFF` · tertiary/hint `#52FFFFFF`

## Typography

| Role | Family | Use for |
|------|--------|---------|
| Display | **Space Grotesk** | balances, titles, large numbers |
| Body / UI | **Plus Jakarta Sans** | everything else |
| Mono | **JetBrains Mono** | addresses, hashes, block numbers |

All three are OFL-licensed (redistributable) and cover Latin-ext / Turkish /
Kurdish Kurmancî glyphs (ş ğ ı İ ê î û ç …).

## Brand mark

- The mark is the **Newroz flame**. Do **not** use the retired Roj-rosette mark
  or a Kurdistan-map logo.
- Splash / app icons: the Newroz flame. Onboarding/marketing hero: the
  *Global United States of Pezkuwi* infographic.

## Surfaces & shape

- Frosted periwinkle surfaces (10/16/24%); cards = frosted fill + 1px hairline +
  soft shadow; **no colored left-accent stripes.**
- Corners: cards 20–24dp, cells/inputs 16dp, buttons & chips fully pill,
  bottom-sheet top 32dp.
- Primary buttons carry a Kurdistan-green glow; press = darken + scale ~0.98.
- Motion: ~140ms taps, ~220ms transitions, standard easing; no bouncy/infinite
  decoration.

## Forbidden-color audit

Named colors are easy to grep; **raster images are not** — scan their pixels.
A simple Python (Pillow) check flags any image with more than noise-level
pink/magenta:

```python
from PIL import Image; import glob
def pink(r,g,b): return r>150 and g<110 and b>120 and (r-g)>70
for f in glob.glob('**/*.png',recursive=True)+glob.glob('**/*.webp',recursive=True):
    im=Image.open(f).convert('RGBA'); im.thumbnail((96,96)); px=im.load(); w,h=im.size; c=t=0
    for y in range(h):
        for x in range(w):
            r,g,b,a=px[x,y]
            if a<30: continue
            t+=1; c+=pink(r,g,b)
    if t and c/t>0.02: print(round(c/t*100,1),'%',f)
```

!!! note "Third-party logos are exempt"
    Do not recolor a third party's trademarked logo to fit the palette — ship it
    as the owner provides it (or don't use it). Recoloring someone else's mark
    misrepresents it.

## Licensing notes for forks

Several Pezkuwi products are forks (e.g. the wallet is a **Nova Wallet** fork,
Apache-2.0; the SDK derives from the Polkadot SDK).

- **Apache-2.0 forks:** you may fork, rebrand and ship — but you **must keep the
  upstream `LICENSE` and `NOTICE`** and their attributions, and state your
  changes. **Do not delete the attribution** (that breaches the license).
  Remove the upstream *trademark* (name/logo) from your UI; keep the *copyright
  notice*. Code-level package namespaces may stay (not a trademark-in-commerce
  use).
- Always confirm a dependency's actual license before rebranding — the right
  action differs by license.

---

!!! tip "Repo authors"
    Add a short `BRAND.md` to your repo that links here and lists the
    project-specific enforcement (where colors/fonts live, a PR brand checklist).
    Keep this page as the single source of truth.
