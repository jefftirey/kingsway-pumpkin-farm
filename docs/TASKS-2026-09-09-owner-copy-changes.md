# Task list — owner copy changes (Kevin King email, Sept 8, 2026)

**Status:** PLAN ONLY. Nothing below has been coded. Approve, strike, or edit each task, then we build on a `feature/owner-copy-changes` branch and PR.

**Direction from Jeff (Sept 9):** strip the page to sourced facts only. Two approved sources: Kevin King emails and the Facebook page. Jim's concept copy is not a source. Tasks 14–19 do the stripping. Part A2 is the resulting page copy, ready to approve as a whole.

**Source of truth for this list:** Kevin King's email to Jim, Sept 8, 2026 9:04 PM ("Site changes and additions"), forwarded by Jim. Kevin is the farm owner, so his email overrides the earlier "no hours / no pricing" rule in the handoff doc.

**Site today:** one page, `public/index.html`. Sections in order: nav, announcement bar, hero, Attractions (`#attractions`), About (`#about`), Make the most of your day (`#plan`), Plan your visit (`#visit`), Around the farm (`#photos`), footer.

---

## Part A — Numbered tasks

Legend: **Where** = section on the page. **Old** = exact text on the live site now. **New** = proposed text, using Kevin's words wherever possible.

### 1. Add hours to the Visit section

- **Where:** Plan your visit (`#visit`), the definition list on the left. Insert a new row after "Opening day".
- **Old:** No hours row exists. The section intro says hours are on Facebook.
- **New:**
  - **Hours** — Monday–Saturday 10:00 am–7:00 pm. Sunday 1:00–6:00 pm. Last admission 30 minutes before close.
- **From Kevin:** "Monday - Saturday 10-7:00, Sunday 1-6. Last admission taken 1/2 hour before close."
- **Note:** Kevin didn't say when the season ends. The admission pass on Facebook expires Oct 31, 2026. Ask him (see Part C).

### 2. Rewrite the Visit section intro

- **Where:** Plan your visit (`#visit`), the paragraph under the heading.
- **Old:** "Hours, admission and daily updates are posted on our Facebook page. Questions, group bookings or just saying hello? Call, email, or message us on Facebook."
- **New:** "Daily updates and weather calls are posted on our Facebook page. Questions, group bookings or just saying hello? Call, email, or message us on Facebook."
- **Why:** Hours and admission will now be on the page, so the sentence is wrong as written.

### 3. Add a new Admission section

- **Where:** New section, id `#admission`, heading "Hours & Admission". Recommended position: between "Make the most of your day" (`#plan`) and "Plan your visit" (`#visit`). Alternative: put it directly after Attractions. Your call.
- **Old:** Nothing. Pricing was deliberately omitted.
- **New (proposed layout, three cards plus a fine-print line):**

  **General Admission — $12 per person**
  Ages 3 and under are free. Admission includes the wagon ride, farm animals, corn maze, straw tunnel, corn box, pedal karts and more.

  **Monday–Thursday — $10 per person**
  Weekday discount on general admission.

  **Kids Barrel Train — $2 per ride**
  For riders 48" and under. Not included in admission.

  **Pumpkins are priced separately.** Pumpkins are sold by size, about $0.35 per pound depending on variety.

  **Payment.** Cash gladly accepted with no fee. A 3% fee applies to all credit card transactions.

- **From Kevin (verbatim):**
  - "General Admission $12.00 per person, 3 and under free."
  - "Admission includes numerous farm attractions including wagon ride, farm animals, corn maze, straw tunnel, corn box, pedal karts, etc."
  - "Monday - Thursday general admission discounted to $10.00"
  - "Kids barrel train ride tickets, 48" and under $2.00 each"
  - "3% fee on all CC transactions, cash gladly accepted with no fee."
  - "Pumpkins are NOT included in the admission price, pumpkins are priced by the size, approx. .35 per pound depending on variety."
- **Decision needed:** Do the hours live in this new section, in Visit (task 1), or both? Recommendation: both. Hours at the top of the Admission section, and the short row in Visit next to the address.

### 4. Add the wagon ride schedule

- **Where:** Two places. (a) The Attractions card for the wagon ride (task 6). (b) A new card in "Make the most of your day" (`#plan`).
- **Old:** No schedule anywhere. Attractions card reads "Jump on the wagon for a breezy farm tour, then test your way through the maze."
- **New (plan card):**
  **🚜 Wagon rides**
  Saturdays and Sundays in September. Daily starting October 1. Weather permitting, so check Facebook before you come.
- **From Kevin:** "Wagon rides only run on Saturdays and Sundays in September. Daily wagon rides begin Oct 1st. Wagon rides are weather permitting, please check facebook for updates."

### 5. Add "Hours & Admission" to the nav

- **Where:** Header nav.
- **Old:** Attractions · About · Plan Your Day · Visit & Contact · Facebook
- **New:** Attractions · Hours & Admission · About · Plan Your Day · Visit & Contact · Facebook
- **Note:** Nav is hidden under 720px (no hamburger). Six links may crowd tablets. If it wraps badly, drop "About" from the nav; the section stays on the page.

### 6. Update the Attractions cards to match Kevin's attraction list

- **Where:** Attractions (`#attractions`). Currently three cards.
- **Old:**
  1. 🎃 **The Pumpkin Patch** — "Hundreds of pumpkins in every size and shape, waiting to come home with you."
  2. 🚜 **Hayrides & Corn Maze** — "Jump on the wagon for a breezy farm tour, then test your way through the maze."
  3. 🐐 **Petting Zoo & Play Area** — "Say hello to the farm animals and let the little ones burn off some energy."
- **New (six cards):**
  1. 🎃 **Pumpkins** — "Hundreds of pumpkins in every size and shape. Priced by the pound, sold separately from admission."
  2. 🚜 **Wagon Ride** — "A breezy ride around the farm. Weekends in September, daily from October 1, weather permitting."
  3. 🌽 **Corn Maze** — "Find your way through this year's maze. (Blurb depends on task 8.)"
  4. 🐐 **Farm Animals** — "Say hello to the animals that call Kingsway home."
  5. 🛞 **Pedal Karts, Straw Tunnel & Corn Box** — "Plenty of ways for the little ones to burn off energy."
  6. 🚂 **Kids Barrel Train** — "A farm favorite for riders 48" and under. $2 per ride."
- **Why:** Kevin's list names "wagon ride, farm animals, corn maze, straw tunnel, corn box, pedal karts." The site says "hayrides" and "petting zoo," neither of which he used. "Petting zoo" implies hands-on contact we can't confirm. "Play area" is not in his list.
- **Decision needed:** Keep the card grid at 3 wide (two rows) or switch to a checklist style. Six cards is fine with the existing `auto-fit` grid.

### 7. Terminology sweep: "hayride" → "wagon ride"

- **Where:** Everywhere the word appears.
  - Hero lead: "…ride the hay wagon and make this fall unforgettable."
  - `<meta name="description">`: "Pumpkin patch, hayrides, corn maze and family-friendly fall fun since 1990."
  - Attractions card title "Hayrides & Corn Maze" (covered by task 6).
- **Old:** "hayrides" / "hay wagon"
- **New:** "wagon rides" / "the wagon"
  - Hero lead: "Wander the pumpkin patch, get lost in the corn maze, hop on the wagon ride and make this fall unforgettable. Family-friendly fun, free from the dark side of Halloween."
  - Meta description: "Kingsway Pumpkin Farm in Hartville, Ohio. Pumpkins, wagon rides, corn maze, farm animals and family-friendly fall fun since 1990. Open Mon–Sat 10–7, Sun 1–6. 2026 season opens September 12."
- **Why:** Use the owner's word. Keeps the site consistent with Facebook and the gate signage.

### 8. Add the 2026 corn maze image and blurb

- **Where:** New block. Options: (a) inside the Corn Maze card in Attractions, (b) a dedicated "This Year's Maze" section after Attractions, (c) the gallery. Recommendation: (b), with the aerial design image, because Kevin sent it specifically and it's the one thing on the farm that changes every year.
- **Old:** No maze image. The only maze reference on the site is the card text and the "Shape Search" game cards in the gallery pass photo.
- **New (placeholder copy until Kevin answers Part C):**
  **This year's corn maze**
  "Every fall we cut a new design into the corn. Here's the 2026 maze from above. Find the five Shape Search stations along the way." (Only if the Shape Search game is still running.)
- **Blocked on:** The maze image itself. It was attached to Kevin's original email to Jim. It is not in your Gmail (searched for Kevin, Kingsway, maze, and Jim's address) and not in Downloads, Desktop, Documents, Pictures or iCloud. Drop it into `public/images/` (any name; we'll rename to `corn-maze-2026.jpg`) or forward the email.
- **Ask Kevin:** Is it OK to publish the full design before opening day, or does he want it kept as a surprise until people walk it? Some farms only post it after the season.

### 9. Update the old-URL redirect for hours & pricing

- **Where:** `vercel.json`, redirects.
- **Old:** `/hours-pricing` → `/#visit`
- **New:** `/hours-pricing` → `/#admission` (or whatever id task 3 lands on)

### 10. Update docs to reflect the owner's decision

- **Where:** `README.md` ("Content source" paragraph) and `docs/HANDOFF-2026-09-03-review.md` (Hard rule #3 and the "Deliberately omitted" list).
- **Old:** README: "Hours and admission are intentionally not listed until the farm confirms them." Handoff: "No ticketing / pricing section. Dropped on purpose."
- **New:** "Hours and admission come from Kevin King's email of Sept 8, 2026 (see docs/TASKS-2026-09-09-owner-copy-changes.md). Update only from the owner."

### 11. Add LocalBusiness structured data with hours

- **Where:** `<head>` of `public/index.html`, a JSON-LD block.
- **Old:** None.
- **New:** `LocalBusiness` (or `TouristAttraction`) with name, address, phone, email, `sameAs` Facebook URL, `openingHoursSpecification` (Mon–Sat 10:00–19:00, Sun 13:00–18:00), and `priceRange` "$". Not visible on the page. Helps Google show hours in search.
- **Why now:** This was on the review checklist but was blocked on not having hours. Kevin just gave them.

### 12. Announcement bar (optional, timing)

- **Where:** The orange bar under the nav.
- **Old:** "🎃 2026 season opens Saturday, September 12 — see you at the farm!"
- **New, on or after Sept 12:** "🎃 Open Mon–Sat 10–7, Sun 1–6 · Wagon rides weekends in September, daily from Oct 1"
- **Note:** Not a change for this PR. Listed so we remember to swap it after opening day.

### 13. Season dates row (pending Kevin)

- **Where:** Plan your visit (`#visit`) definition list. Change the "Opening day" row into a "Season" row once we have an end date.
- **Old:** "Opening day — Saturday, September 12, 2026"
- **New:** "Season — September 12 through [end date], 2026"
- **Blocked on:** Kevin. See Part C.

### 14. Cut the "Petting Zoo & Play Area" card

- **Where:** Attractions (`#attractions`), card 3.
- **Old:** "🐐 Petting Zoo & Play Area — Say hello to the farm animals and let the little ones burn off some energy."
- **New:** Removed. Replaced by the "Farm Animals" and "Pedal Karts, Straw Tunnel & Corn Box" cards in task 6.
- **Why:** "Petting zoo" and "play area" are Jim's words, not Kevin's. No source.

### 15. Cut the unsourced "Make the most of your day" cards

- **Where:** `#plan` section. All four cards.
- **Old:**
  - "🅿️ Parking — Free, right at the gate."
  - "👟 What to bring — Comfortable shoes and a camera. It's a working farm, so dress for the weather."
  - "🍎 Food & drink — Farm stand snacks and seasonal treats available on site."
  - "🏫 Groups & field trips — School and group visits welcome. Call or email to arrange a date."
- **New:** Section removed. Its slot becomes the Hours & Admission section (task 3). The wagon ride schedule card from task 4 moves into Hours & Admission.
- **Why:** None of the four is sourced. Parking, food and groups come back one at a time when Kevin confirms them.

### 16. Strip the About section to sourced facts

- **Where:** About (`#about`).
- **Old:**
  - Heading: "Growing family memories"
  - Paragraph: "A family farm, fired up for fall. Kingsway Pumpkin Farm started with a single field and a simple promise: give families a place to slow down, pick a pumpkin, and make memories together. More than 35 years later, that's still what we do."
  - Bullets: "Families, friends and school groups welcome" / "A genuine working farm with real harvest traditions" / "Safe, spacious grounds for little ones to roam" / "Family owned and operated in Hartville since 1990"
- **New:**
  - Heading: "Growing family memories" (keep, it's a slogan not a claim)
  - Paragraph: "Kingsway Pumpkin Farm has been growing pumpkins and fall memories in Hartville, Ohio since 1990. A family-friendly experience, free from the dark side of Halloween."
  - Bullets: removed.
- **Why:** The origin story, "working farm," "harvest traditions," "safe spacious grounds" and "school groups" are all Jim's. "Since 1990" and the Halloween line are on Facebook. "Family owned and operated" is dropped until Kevin says it.

### 17. Trim the hero and pumpkin card to sourced claims

- **Where:** Hero lead and Attractions card 1.
- **Old:** Hero: "Wander the pumpkin patch, get lost in the corn maze, ride the hay wagon and make this fall unforgettable. Family-friendly fun, free from the dark side of Halloween." Card: "Hundreds of pumpkins in every size and shape, waiting to come home with you."
- **New:** Hero: "Pick a pumpkin, find your way through the corn maze, hop on the wagon ride. Family-friendly fun, free from the dark side of Halloween." Card: "Priced by the pound, about 35 cents depending on variety. Not included in admission."
- **Why:** "Hundreds" and "pumpkin patch" are unsourced. Kevin gave us the price, so the card says that instead.

### 18. Footer tagline

- **Where:** Footer.
- **Old:** "© 2026 Kingsway Pumpkin Farm · A family farm growing pumpkins, memories and a whole lot of fall fun."
- **New:** "© 2026 Kingsway Pumpkin Farm · Hartville, Ohio · Since 1990"
- **Why:** "A family farm" is unsourced. The replacement is all facts.

### 19. Add a Sources section to the README

- **Where:** `README.md`.
- **Old:** "All facts (address, phone, email, opening date, tagline) come from [Facebook]. Hours and admission are intentionally not listed until the farm confirms them."
- **New:** A "Sources" heading listing the two approved sources: Kevin King emails (by date, starting Sept 8, 2026) and the Facebook page. One rule: every factual claim on the page must trace to one of them. Jim's concept copy is not a source.
- **Why:** Stops the next round of freestyling.

---

## Part A2 — Proposed final page copy, top to bottom

Everything below is sourced. **K** = Kevin's email Sept 8, 2026. **FB** = Facebook page. Read this as the approved page; if a line is wrong, mark it.

**Nav:** Attractions · Hours & Admission · About · Visit & Contact · Facebook

**Announcement bar:** 🎃 2026 season opens Saturday, September 12 — see you at the farm! (FB)

**Hero**
- Kicker: Hartville, Ohio · Since 1990 (FB)
- Headline: Memories grow on the vine. (slogan, keep)
- Lead: Pick a pumpkin, find your way through the corn maze, hop on the wagon ride. Family-friendly fun, free from the dark side of Halloween. (K, FB)
- Buttons: Plan your visit · Follow on Facebook

**Attractions — "A whole farm of fall fun"**
- Intro: Everything at Kingsway is made for kids, parents and grandparents alike. (generic, keep or cut)
- 🎃 Pumpkins — Priced by the pound, about 35 cents depending on variety. Not included in admission. (K)
- 🚜 Wagon Ride — Weekends in September, daily from October 1. Weather permitting, check Facebook. (K)
- 🌽 Corn Maze — Find your way through this year's maze. [2026 design image once received] (K, FB)
- 🐐 Farm Animals — Say hello to the animals. (K)
- 🛞 Pedal Karts, Straw Tunnel & Corn Box — All included with admission. (K)
- 🚂 Kids Barrel Train — Riders 48" and under. $2 per ride. (K)

**Hours & Admission** (new, replaces "Make the most of your day")
- Hours: Monday–Saturday 10 am–7 pm. Sunday 1–6 pm. Last admission 30 minutes before close. (K)
- General Admission $12 per person. Ages 3 and under free. Includes wagon ride, farm animals, corn maze, straw tunnel, corn box, pedal karts and more. (K)
- Monday–Thursday $10 per person. (K)
- Kids Barrel Train $2 per ride, 48" and under. (K)
- Pumpkins sold separately, by the pound, about 35 cents depending on variety. (K)
- Cash gladly accepted with no fee. 3% fee on all credit card transactions. (K)
- Wagon rides run Saturdays and Sundays in September and daily starting October 1, weather permitting. Check Facebook for updates. (K)

**About — "Growing family memories"**
- Kingsway Pumpkin Farm has been growing pumpkins and fall memories in Hartville, Ohio since 1990. A family-friendly experience, free from the dark side of Halloween. (FB)
- Photo: pumpkin display (FB)

**Visit & Contact — "Plan your visit"**
- Intro: Daily updates and weather calls are posted on our Facebook page. Questions or just saying hello? Call, email, or message us on Facebook. (dropped "group bookings")
- Opening day: Saturday, September 12, 2026 (FB)
- Hours: Mon–Sat 10–7, Sun 1–6. Last admission 30 min before close. (K)
- Address, phone, email, map (FB)

**Around the farm** (gallery, 3 FB photos, unchanged)

**Footer:** © 2026 Kingsway Pumpkin Farm · Hartville, Ohio · Since 1990

**Meta description:** Kingsway Pumpkin Farm in Hartville, Ohio. Pumpkins, wagon rides, corn maze, farm animals and family-friendly fall fun since 1990. Open Mon–Sat 10–7, Sun 1–6. 2026 season opens September 12. (K, FB)

**Removed entirely:** petting zoo, play area, free parking, what to bring, food & drink, groups & field trips, origin story, working farm, harvest traditions, safe spacious grounds, school groups, family owned and operated, "hundreds of pumpkins," "pumpkin patch," hayride.

---

## Part B — Corn maze notes

What we know:

- Kevin: "I also attached this years corn maze." The attachment is a top-down design showing the maze cut as artwork. Not yet in hand (task 8).
- Facebook (verified Sept 3): the "Shape Search Game" cards read "search the maze for 5 shape stations." So the maze has a game layer for kids.
- The maze is included in general admission (Kevin's list).
- The site currently mentions the maze in exactly three places: hero lead ("get lost in the corn maze"), the Attractions card, and the meta description. No image, no theme, no size, no time estimate.

What we don't know and should ask Kevin (also in Part C):

- Theme or name of the 2026 design.
- Acreage and total path length.
- Typical time to complete. Farms usually quote "30–45 minutes" or similar.
- Whether there are separate easy and hard sections, or one loop.
- Whether the Shape Search game runs in 2026 and whether the game cards are free at the gate.
- Whether he wants the design shown before opening day.
- Is it lit or open after dark? His hours end at 7 pm, so probably not, but worth one question since the site's tagline is "free from the dark side of Halloween."

---

## Part C — Activities inventory (for a "Things to Do" / "Plan Your Visit" page)

Every activity mentioned by the owner, on Facebook, or on the current site. Grouped by how well it's confirmed.

### Confirmed by the owner (Kevin's email, Sept 8, 2026)

| # | Activity | Included in admission? | What we know | Open question |
|---|---|---|---|---|
| 1 | Wagon ride | Yes | Sat/Sun in September, daily from Oct 1, weather permitting | How long is the ride? Where does it go? Does it drop you at the pumpkin field? |
| 2 | Farm animals | Yes | Listed as an attraction | Which animals? Can kids feed or pet them? Feed for sale? |
| 3 | Corn maze | Yes | New design each year; 2026 image exists | Time to complete, acreage, theme (see Part B) |
| 4 | Straw tunnel | Yes | Listed | Age range? |
| 5 | Corn box | Yes | Listed (a sandbox filled with dried corn kernels) | Age range? |
| 6 | Pedal karts | Yes | Listed | Kids only or adults too? Height limits? |
| 7 | Kids barrel train ride | No, $2 per ride | Riders 48" and under | Runs all day? Weekends only? |
| 8 | Pumpkins | No, by the pound, approx. $0.35/lb by variety | Priced by size | Pick-your-own in the field, or pre-picked display? Gourds, mums, corn stalks too? |
| 9 | "etc." | Yes | Kevin wrote "numerous farm attractions including … etc." | **Ask him for the full list.** There are more than six. |

### Confirmed from Facebook (verified Sept 3, 2026)

| # | Activity | What we know | Open question |
|---|---|---|---|
| 10 | Shape Search Game (in the maze) | Cards say "search the maze for 5 shape stations" | Still running in 2026? Free? Prize for finishing? |
| 11 | General admission pass | One-visit pass, expires Oct 31, 2026 | Is there a season pass? Is Oct 31 the closing date? |

### On the site now, NOT confirmed by owner or Facebook

These came from Jim's earlier concept copy. Keep only if Kevin confirms.

| # | Claim on the site | Where it appears | Risk |
|---|---|---|---|
| 12 | "Petting Zoo & Play Area" | Attractions card 3 | "Petting" implies contact. Kevin said "farm animals." Task 6 fixes wording. |
| 13 | Play area | Attractions card 3 | Not in Kevin's list, though straw tunnel / corn box / pedal karts probably are the play area. |
| 14 | "Parking — Free, right at the gate." | Plan section card | Unverified. Likely true, but ask. |
| 15 | "Food & drink — Farm stand snacks and seasonal treats available on site." | Plan section card | Unverified. Is there a concession stand? Cider, donuts, kettle corn? Food trucks on weekends? |
| 16 | "Groups & field trips — School and group visits welcome." | Plan section card | Unverified. Group rate? Weekday-only? Minimum size? |
| 17 | "Started with a single field" origin story | About section | Unverified. |
| 18 | "Genuine working farm with real harvest traditions" | About bullet | Unverified. |

### Not on the site, not mentioned anywhere, worth asking about

Typical for a farm this size. Only add what Kevin confirms.

| # | Possible activity or amenity | Why ask |
|---|---|---|
| 19 | Photo spots (hay bale displays, pumpkin wall, cutouts) | The Facebook hero photo shows a staged pumpkin/hay/scarecrow display, so at least one exists |
| 20 | Hay bale pyramid or climbing stack | Common companion to a straw tunnel |
| 21 | Slides, tire swings, tricycle track, duck races, giant jumping pillow | Common "etc." items |
| 22 | Restrooms (real or portable), accessible? | Every "plan your visit" page needs this |
| 23 | Stroller and wheelchair access on paths and wagon | Frequently asked by families |
| 24 | Pets allowed? | Jim's concept copy said "well-behaved pups welcome." The gallery has a farm dog photo. Unverified. |
| 25 | Picnic tables / bring your own food? | Ties to item 15 |
| 26 | Birthday parties, private group bookings | Ties to item 16 |
| 27 | Season end date and any late-October hour changes | Needed for tasks 1 and 13 |
| 28 | Rain policy: does the farm close, or only the wagon? | Kevin said wagon rides are weather permitting. Is the rest of the farm open in rain? |
| 29 | Payment methods beyond cash and card (Venmo, etc.) | Ties to the 3% fee line |
| 30 | Best time to visit / how long to plan for | The single most useful line on a "plan your visit" page. Typical answer: "Most families spend 2 to 3 hours." Needs Kevin. |

### Proposed shape of a "Things to Do" page (for later, not this PR)

One page or one long section, in this order:

1. **How long to plan for** — one sentence. (Pending item 30.)
2. **Included with admission** — the confirmed list (items 1–6, 10, plus whatever "etc." turns out to be), each with one line and a time estimate where Kevin gives one.
3. **Extra cost** — barrel train ($2), pumpkins (by the pound), anything else.
4. **Wagon ride schedule** — September weekends, October daily, weather permitting.
5. **Good to know** — parking, restrooms, strollers, food, pets, rain, payment.
6. **Groups and field trips** — if confirmed.

---

## Questions for Kevin (consolidated, ready to paste into an email)

1. What's the full list of attractions included in admission? You wrote "etc." after pedal karts.
2. When does the season end? Do hours change in late October?
3. Corn maze: what's this year's theme, how big is it, and about how long does it take to walk? Is the Shape Search game running again?
4. Are you OK with us showing the maze design on the site before opening day?
5. Pumpkins: pick-your-own in the field, pre-picked, or both? Gourds, mums, corn stalks?
6. Farm animals: which animals, and can kids feed or pet them?
7. Is there food or drink for sale on site? Can people bring their own?
8. Is parking free?
9. Restrooms, stroller and wheelchair access: anything we should say?
10. Pets allowed?
11. School groups, field trips, birthday parties: yes or no, and is there a group rate?
12. If it rains, is the farm open with just the wagon closed, or does everything close?
13. Roughly how long do most families spend at the farm?
