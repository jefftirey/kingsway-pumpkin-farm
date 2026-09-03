# Handoff — Kingsway Pumpkin Farm site review

**Written:** 2026-09-03, end of build session
**Next session goal:** fact-check, copy review, image QA, meta/tags, and general polish of the live splash page.

## Current state

| | |
|---|---|
| Live URL | https://kingswaypumpkinfarm.com (and www) — SSL issued 2026-09-03 |
| Vercel | project `kingsway-pumpkin-farm`, team "jefftirey's projects", auto-deploys `main` |
| Repo | https://github.com/jefftirey/kingsway-pumpkin-farm |
| Local | `/Users/jefftirey/ai-workspace/kingsway-farm-project` |
| Page | `public/index.html` — single static file, inline CSS, no build step |
| Images | `public/images/` (5 files) |
| Open PR | #1 `docs/dns-handoff` — docs only, merge or close |
| Client | Jim (owns the domain, IONOS registrar; DNS now on Vercel nameservers) |

## Hard rules (from Jeff)

1. **Facebook is the ONLY approved source** for images and facts: https://www.facebook.com/profile.php?id=100064701789165. The old site on SiteGround was **hacked** — do not fetch kingswaypumpkinfarm.com history, Wayback, or anything derived from the old host.
2. **No AI-generated images.** Jim's earlier concept (landingsite.dev) used them and was rejected. Its *copy* was acceptable for ideas only.
3. **No ticketing / pricing section.** Dropped on purpose.
4. Never commit to `main`; branch + PR.

## What is verified vs. unverified

**Verified from Facebook (safe):**
- Name, "Since 1990", logo
- Tagline: "family friendly experience free from the dark side of Halloween"
- Address: 1555 Andrews Street NE, Hartville, OH 44632
- Phone: (330) 877-6241
- Email: kingswaypumpkin@gmail.com
- Opening day: Saturday, September 12, 2026
- ~18K Facebook followers

**From Jim's concept copy — NOT verified with the farm (fact-check these):**
- Corn maze, hayrides / hay wagon
- Petting zoo & play area
- "Free parking, right at the gate"
- Farm stand snacks / seasonal treats
- School & group bookings welcome
- "Started with a single field" origin story
- "Genuine working farm with real harvest traditions"

**Inferred by Claude (check):**
- "Season passes" card in the About section — based on a Facebook photo of a general-admission pass; wording is vague on purpose
- "More than 35 years" (1990 → 2026)
- "Family owned and operated" — plausible, not stated on Facebook

**Deliberately omitted:** hours, admission prices, closing date, weather policy, pet policy (Jim's copy said "well-behaved pups welcome" — left out as unverified).

## Review checklist for next session

### Fact-check
- [ ] Walk every claim above with Jim / the farm; remove anything they can't confirm
- [ ] Confirm opening day is still Sept 12 and whether a closing date should be listed
- [ ] Decide whether hours & admission go on the page or stay Facebook-only

### Copy
- [ ] Read the whole page aloud for tone — target: warm, plain, family-farm voice, no marketing gloss
- [ ] Hero headline "Memories grow on the vine" — keep or replace?
- [ ] Announcement bar wording (currently "🎃 2026 season opens Saturday, September 12 — see you at the farm!")
- [ ] Footer tagline
- [ ] Check for em-dashes/typos/consistency ("Kingsway Pumpkin Farm" vs "Kingsway Farm")

### Images (`public/images/`)
| File | Source | Issue |
|---|---|---|
| `logo.jpg` | cropped from FB banner | 345×300, wood-plank background baked in; ideally get a transparent PNG from Jim |
| `pumpkin-display.jpg` | FB post photo | 414×414 — used as hero background AND about image AND gallery; low-res, ask for original |
| `opening-2026.jpg` | FB post | 414×414, text is cropped ("ening Sept 12th for 20") — replace or drop |
| `season-pass.jpg` | FB post | 414×414, fine for gallery but implies passes exist — confirm |
| `farm-dog.jpg` | FB post | 414×414, cute, confirm it's the farm's dog |

- [ ] Ask Jim for original full-res photos (Facebook logged-out only serves 414px)
- [ ] Get more variety: corn maze, hayride, kids, animals — only real farm photos
- [ ] Favicon is currently the JPEG logo; make a proper square PNG/ICO
- [ ] OG image (`og:image`) points at `pumpkin-display.jpg` — low-res; replace with a 1200×630

### Tags / SEO / meta
- [ ] `<title>` and `meta description` review
- [ ] Add `og:url`, `twitter:card`, canonical link
- [ ] Add LocalBusiness JSON-LD (name, address, phone, geo, sameAs → Facebook)
- [ ] `robots.txt` and `sitemap.xml` (none exist yet)
- [ ] Heading hierarchy (one H1, H2 per section) — currently OK, re-check after edits
- [ ] Alt text on every image (present, review wording)

### Technical
- [ ] Mobile pass: nav collapses to nothing under 720px (links hidden, no hamburger) — decide if a mobile menu is needed for a one-pager or if anchor links are enough
- [ ] Google Maps iframe: works, but consider a static link if it slows the page
- [ ] Lighthouse run (perf / a11y / SEO)
- [ ] Contrast check on cream-on-brown text
- [ ] Google Fonts load (Lilita One + Nunito) — fine, or self-host

### Housekeeping
- [ ] Merge/close PR #1
- [ ] Jim: cancel SiteGround hosting, rotate IONOS + SiteGround passwords
- [ ] Google Search Console for kingswaypumpkinfarm.com (Jim or Jeff)
- [ ] Decide on analytics (none installed)

## How to work on it

```bash
cd /Users/jefftirey/ai-workspace/kingsway-farm-project
git checkout main && git pull
git checkout -b review/<topic>
# edit public/index.html
npx serve public                 # local look at http://localhost:3000 (file:// breaks the /images paths)
git push -u origin review/<topic> && gh pr create
```

Vercel builds a preview URL for every PR; production updates on merge to `main`.
