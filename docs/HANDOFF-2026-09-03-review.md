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
3. ~~No ticketing / pricing section.~~ **Superseded 2026-09-09:** Kevin King (owner) supplied hours and prices by email on Sept 8, 2026. See `docs/TASKS-2026-09-09-owner-copy-changes.md`.
4. Never commit to `main`; branch + PR.

## What is verified vs. unverified

**Verified from Facebook (safe):**
- Name, "Since 1990", logo
- All site images are byte-identical to files served by the Facebook page (MD5-matched 2026-09-03); the logo is a crop of the Facebook banner. None are AI-generated.
- A maze exists: the "Shape Search Game" cards in the pass photo read "search the maze for 5 shape stations"
- Admission passes exist: the pass in the photo is a **one general admission** pass, expires Oct 31, 2026 (so the season likely runs through October)
- Aug 23, 2026 post: "Our first day will be Sept12th" and "we are having issues with our website, so please check fb"
- Tagline: "family friendly experience free from the dark side of Halloween"
- Address: 1555 Andrews Street NE, Hartville, OH 44632
- Phone: (330) 877-6241
- Email: kingswaypumpkin@gmail.com
- Opening day: Saturday, September 12, 2026
- ~18K Facebook followers

**From Jim's concept copy — NOT verified with the farm (fact-check these):**
- Hayrides / hay wagon (the maze itself is confirmed, "corn" is not)
- Petting zoo & play area
- "Free parking, right at the gate"
- Farm stand snacks / seasonal treats
- School & group bookings welcome
- "Started with a single field" origin story
- "Genuine working farm with real harvest traditions"

**Inferred by Claude (check):**
- The pass in the gallery photo is a general-admission pass, not a season pass (alt text fixed 2026-09-03)
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
- [x] Mobile pass done 2026-09-03: full-page render checked at 375px, no overflow. Nav links still hidden under 720px (no hamburger) — anchor CTAs cover it for a one-pager; revisit only if more sections are added
- [x] Google Maps iframe replaced with a click-to-load "Show map" button + "Open in Google Maps" link (saved ~400 KB of Maps JS on first load)
- [x] Lighthouse mobile (simulated slow 4G): before 76 perf / 91 a11y; after fixes 100 perf / 94+ a11y locally. Re-run against production after merge
- [x] Contrast: white-on-orange (2.92:1) failed AA on the announcement bar and buttons; now brown-on-orange (4.87:1)
- [x] Google Fonts now load non-blocking (media=print swap); `opening-2026.jpg` removed from the gallery (cropped text); hero image preloaded; images sized + lazy
- [ ] Apex DNS: as of 2026-09-03 evening, some resolvers still cached the old SiteGround A record (35.209.89.159) showing an "Under Maintenance" page. Registry delegation and Vercel NS are correct; this clears on TTL expiry. Re-check with `dig @8.8.8.8 kingswaypumpkinfarm.com A`

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
