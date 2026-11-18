# External evidence list: which outside numbers you may use, and how far

> **Written for Claude to follow, and for people to understand.** Follow `01-core-rules.md`; terms are in `glossary.md`.
> **What this is:** outside numbers and claims already checked, so nobody has to check them again from zero.
> **Four parts:** A, claims you may use (each with a use limit); B, popular claims with no reliable source; C, claims still waiting to be verified; D, slots for the user's own measurements.
> **Dates:** checks were done by the kit author in 2026. Platforms change. Every date only means "true as of then".

---

## How to use this list

**One sentence:** before using an outside number, look here. If it's listed, use it only within its limit.

**Example:** you want the "brand" search group to convert higher. You find E2, "brand-term conversion is at least 2× non-brand". Its limit is "bounds only, and direction", never the best estimate. So you may set the top of the range at 2× the average, and the main number still comes from the user's own data. Multiplying the main number by 2 breaks the rule.

### 1. Check this list first

- Listed, and your use stays inside its limit → use it and name the entry (e.g. "E2").
- Not listed → run the two checks in core rules 5.6 (your own data really can't answer it; you can see what was measured, and it matches your use). If it fails, mark it as a data gap.

### 2. Every entry has a use limit

Strongest to weakest:

| Limit | Meaning |
|---|---|
| Best estimate | May be used as the main number |
| Bounds only | May set the edge of a range, never the main number |
| Direction only | May say which way, never how much |

Four narrower limits:

| Limit | Meaning |
|---|---|
| Mechanism check only | Only answers "does this mechanism affect this data at all?" |
| Definition only | Only answers "what does this report field actually count?" |
| Period comparability only | Only answers "can these two periods be compared directly?" |
| Reference line only | A threshold shown next to the user's own data, never a multiplier |

- Going above the limit breaks the rule.
- If the user wants to go above it, that is a user override (core rules section 0): say the risk once, do it, label "user decision, low confidence".

### 3. Check the date

Before use, open the original source again when any of these is true:
- the last check is more than 12 months old;
- the entry will affect a main number;
- the entry says "needs recheck" (check on first use).

Rechecking means opening the original, not someone's summary. If it no longer holds, stop using it and tell the user.

### 4. "Fetch method" entries

They store where and how to get a number, not the number. Fetch the current value every analysis.

### 5. Nothing in Part B may fill a gap

Only three ways out:
- measure it yourself;
- leave it blank and show a sensitivity range;
- only for "no traceable source" items: propose it to the user under the plausible-but-unverified path in core rules 5.6.

Items marked "disproved" can never take the third way.

### 6. The user keeps this list current

- You can't edit Project files.
- When something is worth adding, or an entry no longer holds: write it under "Suggested changes to the evidence list" in the analysis log, and tell the user.
- The user decides whether to update the file.

### 7. Citing an entry is not "borrowing a number from elsewhere"

- Numbers from another brand are still never allowed.
- The user's own measured multipliers must be rechecked before reuse in a new period: has anything changed?

---

## Part A. Claims you may use

### E1. Device and phone-system share by country
- **Type:** fetch method.
- **Where:** StatCounter Global Stats. Two pages per country:
  - mobile operating system share (iOS vs Android);
  - platform share (mobile vs desktop vs tablet).
- **What it measures:** share of web page views, which differs from share of online purchases. Mobile is usually higher for purchases. Say so whenever you use it.
- **Limit:** may be used as a structural weight (splitting exposure by device).
- **Rules:** use the same month for every country, or explain why not. Fetch the current month in the data step. Never reuse an old figure.

### E2. Brand-term conversion is at least 2× non-brand
- **Source:** Google and Compete, "The Evolving Path of Today's Tech B2B Customer" (Sept 2012), on thinkwithgoogle.com.
- **What it measured:** a 2-million-person click panel, US tech B2B, Q2 2011 to Q1 2012. "Conversion" mixed contact forms, signups, downloads and purchases.
- **Limit:** bounds only, and direction. Never the best estimate.
- **Why only bounds:** different country, industry, years and conversion definition.
- **Math note:**
  - The study compares brand ÷ non-brand.
  - Your conversion figure is usually the blended rate (brand plus non-brand together).
  - Brand ÷ blended is always ≤ brand ÷ non-brand.
  - So "up to 2× the blended rate" is a true upper bound, and a cautious one.
- **When to retire it:** the user's own brand vs non-brand conversion (from Google Analytics or Amazon Attribution) is available and actually separates the two groups. Then this becomes background only.
- **Last checked:** 2026-07 (full text).

### E3. Clearer search intent converts better
- **Source:** Du, Su, Zhang, Zheng (2017), *Information Systems Research* 28(4): 711–722. DOI 10.1287/isre.2017.0724. Peer reviewed (checked by other researchers before publication).
- **What it measured:** one advertiser's data. Keywords in three groups: general, own brand, competitor brand. Own-brand terms convert higher.
- **Limit:** direction only. Supports E2 independently.
- **Rule:** never use the paper's coefficients unless a person has opened table 3 and checked them.
- **Last checked:** 2026-07 (journal, DOI and method checked; table not checked word for word).

### E4. Where iOS Link Tracking Protection applies
- **Source:** Apple (press release 2023-06-05; WWDC23 session 10053), plus an independent test by Word to the Wise.
- **Content:**
  - Works only in Mail, Messages and Safari Private Browsing.
  - Strips known click IDs such as gclid and fbclid. UTM parameters are not on its list.
  - Normal Safari browsing is not affected.
  - Parameters added after a redirect usually survive.
- **Limit:** mechanism check only (does this mechanism touch this data at all?).
- **Hard rule:** the mechanism existing says nothing about how much is lost. There is no reliable loss rate (see U7). Never write a percentage.
- **Last checked:** needs recheck.

### E5. How links pass parameters when they open an app
- **Source:** Apple Universal Links and Google App Links developer docs.
- **Content:**
  - Link opens the app automatically: the full URL, parameters included, is passed in.
  - Shopper opens the app by hand: nothing is passed.
  - By design nothing is dropped. Real losses come from failed app opens, in-app browsers and device switching. No official source says how much.
- **Limit:** mechanism check only.
- **Last checked:** needs recheck.

### E6. What Amazon Attribution counts
- **Source:** Amazon Ads official guides, product page, tag docs, DSP reporting guide.
- **Content:**
  - Clicks only. Last click within 14 days.
  - The tracking tags (maas=, ref_=aa_maas, aa_campaignid and so on) must reach the final landing URL intact.
  - Total conversions = promoted product conversions + brand halo (any product under the same brand).
  - New-to-brand = no purchase from the brand in the past 12 months.
  - Whether it matches people by account or by browser is not stated officially. Agency claims contradict each other.
  - How much it misses across devices can't be worked out from the docs. The only way to measure it is the user's own calibration (D1).
- **Limit:** definition only.
- **Last checked:** needs recheck.

### E7. The January 2026 attribution change did not touch Amazon Attribution
- **Source:** Amazon's announcement, quoted by name in PPC Land (2026-01-14).
- **Content:**
  - The change only affected view-based attribution (Sponsored Brands and Sponsored Display impression-billed campaigns, DSP).
  - All click-based attribution stayed the same.
  - Amazon Attribution was explicitly excluded.
- **Limit:** period comparability only.
- **Use:**
  - An Amazon Attribution calibration does not need to be cut at January 2026.
  - If you also analyze view-based ads across that date, use the "Purchases (all views)" field to rebuild the old basis.
- **Last checked:** needs recheck.

### E8. Buy Box: 90% guideline
- **Source:** Amazon Ads beginner guide ("ideally 90% or higher" Buy Box share before advertising).
- **What it is:** an official recommendation. Neither a policy threshold nor a measurement.
- **Limit:** reference line only.
- **Use:** judge whether Buy Box share is low from the user's own data; show this line next to it.
- **Last checked:** 2026-10.

### E9. No Buy Box or no stock: which ads stop
- **Content:**
  - Sponsored Products shows only when you hold the Buy Box.
  - Sponsored Brands and Sponsored Display only need the product to be eligible.
  - When out of stock, Sponsored Products stops and Sponsored Display pauses automatically.
  - **Exception: Sponsored Brands keeps running and spending as long as any product in the ad still has stock.**
- **Limit:** reference line only. Used to decide which days to split out.
- **Use:** Sponsored Brands spend and orders on stockout days are real, not a data error. Don't delete them.
- **Last checked:**
  - Basic rule: 2026-10.
  - The Sponsored Brands exception and the eligibility difference: **needs recheck** (from a research pass, not checked word for word).
  - If the official page is inside Seller Central, that counts as the user's back office: ask first, look only.

### E10. Stock day thresholds: 28, 14, 90
- **Source:** Amazon low-inventory fee definition, restock recommendations, excess inventory help.
- **Content:**
  - Under 28 days of historical supply: low inventory (fee definition).
  - Under 14 days: restock suggestions target it.
  - Over 90 days: excess.
- **Limit:** reference line only.
- **Use:** add a "low stock" note under 28 days. What actually hurts sales is real stockout days.
- **Last checked:** 2026-10.

### E11. "New release" badge looks at the first 90 days
- **Source:** Amazon "New Release" badge help.
- **Content:** based on sales in the first 90 days after listing. The definition differs by category.
- **What it is not:** it is not how long rank takes to settle.
- **Limit:** reference line only.
- **Use:** 90 days is the default new-product window. End it early if the user's own data shows rank and sales have settled.
- **Last checked:** 2026-10.

### E12. Official attribution windows
- **Content:**
  - Sponsored Products: 7 days.
  - Sponsored Brands, Sponsored Display, Amazon Attribution: 14 days.
- **Limit:** reference line only.
- **Use:**
  - Sets the 7 and 14-day evidence windows for indirect effects.
  - Flag the last 14 days of any period as "attribution not fully in yet".
- **Last checked:** 2026-10.

### E13. How Amazon ranks brand-new products (cold start)
- **Sources:** patent US11269898B1 (Google Patents); Han et al. 2022 (CIKM; Amazon Science summary); Gupta et al. 2020 (WWW).
- **Content:**
  - A new product starts ranked using similar products' performance, then shifts step by step to its own clicks and purchases.
  - Han 2022, an online experiment over 50 million queries: new products got +13.53% impressions and +11.14% purchases.
- **Limit:** mechanism check only.
- **Use:** before crediting any new-product surge to ads, rule out cold start.
- **Rule:** the +13.53% and +11.14% are direction only. They come from a sitewide Amazon experiment; applying them to one brand would be borrowing a number.
- **Note:** the patent gives no number of days. A "for example, three days" sometimes quoted from it could not be found. See U14.
- **Last checked:**
  - Patent and Han 2022: 2026-08 (originals opened).
  - Gupta 2020: needs recheck.

### E14. Brand-term search ads: real gain depends on competitors (Simonov, Nosko, Rao 2018)
- **Source:** *Marketing Science* 37(2). Randomized experiments on about 2,500 brands on Bing. Peer reviewed, not Amazon.
- **Content:**
  - No competitor bidding on the brand term: brand ads add only 1–4% extra clicks.
  - The brand stops, a competitor bids: the competitor takes 18–42% of clicks, so defensive bidding pays.
- **Limit:** direction only, plus mechanism check.
- **Use:** decides whether to run the competitor check on brand search results, and whether harvest should show defense value alongside.
- **Rule:** the 1–4% and 18–42% never enter any calculation, and never set bounds for cannibalization.
- **Note:** a "99.5%" figure sometimes attached to these studies is not in the original. Never cite it.
- **Last checked:** needs recheck (listed as peer reviewed in research; figures not checked word for word).

### E15. Brand-term ads on eBay were almost fully replaced by organic (Blake, Nosko, Tadelis 2015)
- **Source:** *Econometrica* 83(1); first as NBER working paper 20171 (2014). eBay experiment, not Amazon.
- **Content:** when brand-term ads were switched off, organic search picked up nearly all the clicks and sales. The paper says "nearly complete" and gives no percentage.
- **Limit:** direction only.
- **Use:** supports "split indirect credit by truly extra orders" and "subtract cannibalization".
- **Note:** "eBay recovered 99.5%" is not in the paper. Never cite it.
- **Last checked:** needs recheck.

### E16. Business Reports field definitions on pages with several sellers
- **Source:** Amazon official account posts on the seller forum; SP-API field definitions.
- **Content:**
  - Sessions and Page Views: every visitor to the product page, whoever holds the Buy Box.
  - Unit Session Percentage (conversion): only your units on top, but all Sessions underneath.
  - Featured Offer (Buy Box) percentage: Page Views underneath, not Sessions.
  - Whether these definitions changed between 2023 and 2026 has no clear answer.
- **Limit:** definition only.
- **Use:**
  - When another seller holds the Buy Box, your conversion looks lower because the bottom includes their traffic. That's a definition effect. It doesn't mean the ads or the listing have a problem.
  - To estimate traffic while you held the Buy Box, multiply Buy Box share by Page Views, not Sessions.
- **Last checked:** needs recheck. Seller Central pages count as back office: ask first, look only.

### E17. Lightning-deal rank lift fades in about 2 weeks (Tang et al. 2026)
- **Source:** *International Journal of Production Economics*.
- **Limit:** direction only.
- **Use:** only to decide whether to suspect a delayed positive effect when leftover is negative (module 4).
- **Rule:** never used as a number of days. Your evidence windows are pre-registered at 7, 14 and 28 days regardless.
- **Last checked:** needs recheck.

### E18. Brand Referral Bonus: which markets
- **Type:** fetch method.
- **Where (public pages only):**
  1. Sell on Amazon US blog: sell.amazon.com/blog/brand-referral-bonus
  2. Amazon Ads guide to Amazon Attribution: advertising.amazon.com/library/guides/basics-of-amazon-attribution (check other language versions too)
  3. Amazon Ads announcement on Brand Referral Bonus in Amazon Attribution reports: check the "available in" line on each language version.
  4. Each country's Sell on Amazon "grow" or "new seller incentives" page.
- **As of 2026-10-12:**
  - Officially stated for the US only: Professional plan, brand registered; bonus "on average about 10%" of qualifying sales; sales from on-site ads don't count.
  - UK, Germany, Japan, Australia pages don't mention it.
  - Those pages list new-brand sales rebates, which are a different program. Don't mix them up.
- **How to write it:**
  - "Official public pages mention the US only."
  - For other markets: "not stated". Never "not allowed".
  - Recheck every analysis.
- **Limit:** mechanism check only (in this market, can the bonus report be read next to Amazon Attribution as an extra harvest cross-check?).
- **Rule:** the 10% is a sitewide average. Never use it as the user's bonus rate.
- **Whether the user actually receives the bonus:** a fact only they know. Ask at Stop 1.

### E19. Amazon Marketing Cloud self-service for sponsored-ads-only advertisers
- **Source:** Amazon Ads AMC product page (advertising.amazon.com/solutions/products/amazon-marketing-cloud).
- **Content:** advertisers who run only sponsored ads can access AMC through self-service.
- **Limit:** mechanism check only (one condition for listing AMC as a harvest tool).
- **Note:** whether AMC can see Amazon Attribution events is a separate question (V2).
- **Last checked:** 2026-10 (the self-service sentence). A "since September 2025" start date is not on that page: needs recheck.

### E20. Post-promotion dips are often hidden (Hendel & Nevo 2003)
- **Content:** the sales drop after a promotion is often masked by positive effects in the same period.
- **Limit:** direction only.
- **Use:** a reminder in the text when leftover is negative. Never changes a calculation.
- **Last checked:** needs recheck.

### E21. Google brand-term ads and Amazon sales (Haus 2025)
- **Content:** geo experiments by the measurement company Haus: Google brand-term ads vs sales on Amazon, pooled −1.9%; one case −2.7%. Industry research with a disclosed method, not peer reviewed.
- **Limit:** direction only.
- **Rule:** the figures never enter any calculation.
- **Last checked:** needs recheck.

### E22. Indirect effects exist: mechanism evidence without numbers
- **Content:**
  - (a) Amazon's help page lists "how often a product is purchased" as a ranking factor. It doesn't mention traffic source. Write that as "not mentioned", never as "denied".
  - (b) Amazon Ads guides say more product page views "can help support organic rank" and that on-site ad traffic "helps lift organic rank". No numbers.
  - (c) An anonymous e-commerce platform experiment (*Management Science*, 2025): on-site ads take some business from organic results.
- **Limit:** mechanism check only.
- **Use:** justifies having "off-site indirect" and "on-site indirect" as parts of the split. Decides categories, never amounts.
- **Last checked:** 2026-10.

### E23. Indirect effects: studies with numbers
- **Content:**
  - (a) Amazon research: moving up one rank position goes with about +0.36% sales. Correlation, not cause, and based on estimated sales.
  - (b) App store working paper: after ads stop, organic downloads fall 20–30%.
- **Limit:** direction only.
- **Rule:** never an indirect multiplier, strength, or any parameter.
- **Last checked:** needs recheck.

---

## Part B. Popular claims with no reliable source

**One sentence:** all checked, none usable. Never fill a gap with any of these.

**Two statuses:**
- **Disproved:** reliable evidence shows it's wrong. Can never be adopted.
- **No traceable source:** no reliable origin, and not proven wrong either. Only the user can adopt it, through the plausible-but-unverified path.

| # | Claim | Why it can't be used | Way out | Status |
|---|---|---|---|---|
| U1 | Benchmarks for bridge page click-through ("X% of visitors click through to Amazon") | No source with a visible method | Measure it in Google Analytics | No traceable source |
| U2 | How much a bridge page filters out low-intent visitors | No measured source | Your own A/B test | No traceable source |
| U3 | Share of parameters that survive when a web link opens an app | No measured source | Measure it once Amazon Attribution is live | No traceable source |
| U4 | Share of e-commerce purchases made more than 14 days after the click | No measured source | Time-lag data in Amazon Marketing Cloud | No traceable source |
| U5 | Share of shoppers who switch devices during big sales | No measured source | Absorbed by your own Amazon Attribution calibration (D1) | No traceable source |
| U6 | Typical e-commerce conversion rates for X (Twitter) ads | No source with a visible method. Generic social benchmarks have been passed off as measured X conversion before | Search term grouping plus your own measured conversion | No traceable source |
| U7 | iOS Link Tracking Protection loss rate (%) | The mechanism is documented (E4); no reliable loss measurement | Measure it, or leave blank and show a sensitivity range | No traceable source |
| U8 | Any "A10 algorithm" weight for external traffic, including "off-site counts 3×" | Sources copy each other. Amazon has never confirmed "A10" or any traffic-source weight. The earliest "3×" found is a 2020 guest marketing post that says "some claim" and admits no hard data | Your own on/off experiment | No traceable source |
| U9 | "Brand terms convert 4–8%, non-brand 1–2%" | Origin can't be traced; what was measured is unknown | Use E2 (bounds only) | No traceable source |
| U10 | Reading qid or ref in Amazon URLs to tell where an order came from | Official purpose is search timestamps and placement tracking. Sellers can't see order-level URLs. Crafting URLs to move rank breaks the rules | Amazon Attribution tags | No traceable source |
| U11 | Clean links (/dp/ASIN) get an algorithm boost | No official basis, no measured test | Clean URL plus Amazon Attribution tag is fine, for consistent reporting only | No traceable source |
| U12 | Social traffic weight 0.8 (vs Google 3.0) | Same family as U8; comes from a document with no source | Not needed: all orders weigh 1:1:1 | No traceable source |
| U13 | "Branded ad clicks are 100% cannibalization" | E14: the real gain depends on whether competitors bid on your brand. With competitors, not bidding loses clicks | Treat cannibalization as an estimate gap with a range that includes low values. With competitors present, never count it all as cannibalization | **Disproved** (E14 not yet rechecked; if E14 fails the recheck, this becomes "no traceable source") |
| U14 | "Amazon switches a new product to its own data around day 5" | No primary or secondary source has any number of days | Use E13 (mechanism) and E11 (90-day reference), and check your own rank and sales | No traceable source |
| U15 | "Each ad order brings 0.2–0.6 organic orders; long-run multiplier 1.2–1.6×; half-life 7–10 days" | **Fabricated citation.** The cited paper is about supermarket price promotions; another journal name was wrong; neither contains these numbers. They look exactly like the parameters an indirect-effects model wants, so they keep coming back. Watch for them | Measure it yourself, or show a sensitivity range | No traceable source (fabricated citation) |
| U16 | "Indirect effects are capped at 5% of off-site direct" | The cited case study has no 5%. It was a single case with no control (about 2 rank positions up), and "2 positions" can't be converted into "5%" | Indirect only splits leftover revenue; caps come from your own data | No traceable source |

---

## Part C. Not yet verified

**One sentence:** these aren't dead ends; they just haven't been checked yet. Until they are, don't treat them as fact.

### V1. Search Query Performance uses a 24-hour window
- **Status:** widely said in the industry. No official public page says so word for word.
- **How to verify:** read the built-in definitions on the Search Query Performance dashboard in Seller Central. Back office: ask first, look only.
- **Until verified:**
  - Label "proxy, low confidence", note "industry claim, not officially verified".
  - Never use it as a hard assumption in a calculation.

### V2. Can Amazon Marketing Cloud see Amazon Attribution clicks?
- **Status:** research results disagree. The official table list doesn't show Amazon Attribution tables.
- **How to verify:** right after AMC is set up, check whether an Amazon Attribution event table exists. Needs login: ask first, look only.
- **Until verified:**
  - Don't assume it.
  - The harvest overlap rate (D2) stays inactive until this is confirmed.

### V3. Amazon Marketing Cloud hides results under "about 100 users"
- **Status:**
  - The official product page says there is an aggregation threshold but gives no number.
  - The "100" comes from agency guides.
  - One third-party source says thresholds come in several levels (from 2 up to 100 users, and 2,000 for custom audiences), with no official source either.
- **How to verify:** open the AMC privacy and aggregation docs in the Amazon Ads advanced tools center in a browser, or read the threshold notes inside AMC after setup.
- **Until verified:**
  - Never decide AMC can or can't work based on "about 100".
  - Write: "There is an aggregation threshold, number not officially confirmed; small markets or single products may be filtered, so combine products or lengthen the period."
  - Filtered rows don't show up. Never read them as 0.

---

## Part D. Slots for the user's own measurements

**One sentence:** these aren't outside numbers. Once the user has them, they are the strongest evidence there is. Record them in the brand file, per market and per channel.

### D1. Amazon Attribution calibration multiplier
- **What:** off-site direct rebuilt from clicks to orders ÷ what Amazon Attribution recorded. Per channel, per market (module 4 section 13).
- **Example:** you calculated 100,000; Amazon Attribution recorded 80,000. The multiplier is 1.25.
- **Active when:** Amazon Attribution is live on those campaigns.
- **Once active:** it is the main source for the tracking gap. Label "measured".
- **Before reuse in a new period:** check that channel mix, bridge page design and market mix haven't changed much.

### D2. Harvest overlap rate
- **What:** of the conversions credited to on-site brand-term ads, the share that had an Amazon Attribution off-site touch earlier in the window.
- **Where from:** purchase path data in Amazon Marketing Cloud, measured per market and channel.
- **Active when:** Amazon Attribution is live, AMC is set up, and V2 confirms the event table exists.
- **Once active:** the top tool in the harvest ladder (module 2). Lower tools become cross-checks.
- **Remeasure when:** tag coverage, bridge page design or brand-term campaign structure changes.
