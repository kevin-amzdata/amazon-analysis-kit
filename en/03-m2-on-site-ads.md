# Module 2: What did on-site ads really bring?

> **Written for Claude to follow, and for people to understand.** Follow `01-core-rules.md`; terms are in `glossary.md`.
> **When to use:** the question touches Amazon ads (Sponsored Products, Sponsored Brands, Sponsored Display), or module 4 (off-site impact) needs the "on-site ads, direct" part.
> **What to look at:** what the ads really brought, good and bad, and what to change. This module doesn't judge whether ROAS is high or low.
> **How to read:** each section opens with one sentence; most then give an example, followed by the rules. Boxes titled "Details for Claude" can be skipped by people. Claude must follow them.

---

## 1. What data you need

**One sentence:** campaign reports, advertised product reports, and Business Reports to reconcile against.

**Must have:**
- Campaign-level ad reports for the period: spend, clicks, impressions, sales, orders, units. Daily or weekly is fine.
- The report must separate three kinds of campaign: protecting your own brand terms, targeting competitor terms, and generic or automatic targeting.
- Advertised product report (by ASIN). Better if it has the "same product" and "other product" columns.
- Business Reports data for every child ASIN (module 1), for actual units and total revenue.

**Nice to have:**
- Search term report: to add up the same search term across campaigns.
- Placement report: top of search, rest of search, product pages.
- Which attribution window each report uses. Sponsored Products usually 7 days; Sponsored Brands and Sponsored Display usually 14. Ask if unsure. It's a fact, never a guess.
- What each campaign was set up for: brand defense, launch, clearance, competitor attack. Only the user or whoever runs the account knows.

---

## 2. Reconcile the accounts first

**One sentence:** ad reports often claim more than really sold. Match them to actual sales first.

**Example:** ad reports say this product sold 1,200 units this month. Business Reports say it sold 1,000 in total. Ad-attributed sales can be at most 1,000 units.

**Rules:**
- If product-level totals and campaign-level totals differ, use the campaign level.
- If ads claim more orders or units than Business Reports show for that product and period, cap ad-attributed sales at the actual number. Over-claiming is common, from different attribution windows or halo orders.
- **Halo orders:** click an ad for A, buy B from the same brand. Decide with the user at Stop 1 whether halo orders count toward the advertised product. Use the same rule in every period you compare.
- Zero on-site spend and zero clicks this period: "on-site ads, direct" is 0, measured, high confidence. Mark the cannibalization and overlap checks "not applicable (no on-site ads this period)". This is a stated decision. Nothing was skipped.
- Ads ran but the report is missing: that's a data gap. Give a range. Never write 0.

---

## 3. Brand ads taking organic sales

**One sentence:** some brand-term ad orders come from people who would have bought anyway. This is **cannibalization**. That part goes back to baseline, not to ads.

**Example:** a shopper searches your brand name on Amazon. Your organic listing is first. They click the brand ad just above it and buy. Without the ad, they'd most likely have clicked the organic listing and bought.

**Rules:**
- How much is truly extra usually can't be measured with the user's data. Treat it as an estimate gap: give a most likely value and a range.
- The range must include low values, i.e. the possibility that most orders would have happened anyway.
- With no on-site search term report and no period when on-site ads were switched off and on, the data can't show whether on-site ads added any orders at all. Then the range must reach "almost all would have bought anyway" (on-site direct close to 0). Narrow the top of the range only with evidence that competitors bid on your brand term. In that case the most likely value is the middle of the range, labeled "assumption: this data can't tell", and on-site indirect follows the indirect rule in module 4 section 8.
- New-to-brand (NTB) share can't answer this. It measures whether the customer is new. It can't tell whether they'd have bought without the ad. Don't use it to size cannibalization.
- If competitors bid on your brand term, brand ads have real defense value. Never count them all as cannibalization. The "branded clicks are all cannibalization" claim has been disproved (see U13 in `08-external-evidence.md`).
- The period used to calculate the baseline, and each of the three comparison periods (main baseline, alternate A, alternate B; core rules section 9), must use exactly the same cannibalization rule as the analysis period. Otherwise leftover revenue inflates.
- Best upgrade: switch brand ads off and on in turns (different weeks or markets) and compare total sales. Add it to the data request list. Whether to run it is the user's call.

**Supporting signals:**
- Search results for your brand name: is your organic listing right under your ad? Are competitors bidding on your brand? The user's own past screenshots are best. A screenshot taken today only describes today.
- Brand search volume falling while brand-ad clicks jump, both beyond normal week-to-week swings.

---

## 4. Overlap with off-site ads, and harvest

**One sentence:** the same order may be counted once on-site and once off-site (overlap), and demand created off-site may be credited on-site (harvest).

Only needed when off-site ads also ran.

### 4.1 Overlap

**Example:** a shopper clicks a Google ad, then clicks your Sponsored Products ad, then buys. That order may be counted in both "off-site direct" and "on-site direct".

**Rules:**
- First check where module 4 got the conversion rate for off-site direct.
- Only from off-site-specific data (bridge page button clicks, off-site tracker conversions): no overlap.
- From whole-store conversions (which already include ad orders): estimate the overlap and subtract it from on-site direct. Off-site direct stays as calculated. Label "estimate", low confidence.
- Can't tell which: assume overlap and note the gap.

### 4.2 Harvest

**One sentence:** a shopper clicks an off-site ad, doesn't buy, later searches your brand on Amazon and buys through your brand ad. The demand came from off-site; the credit went to on-site.

**Example:** one week Google spend doubled, and brand-ad orders that week were 50 above normal. Other weeks show no such pattern. Some of those 50 may be harvest.

**Rules:**
- Harvest needs an off-site signal: an off-site tracker recorded a touch, or off-site spend bursts line up in time with brand-ad order bursts.
- No off-site signal: brand-ad orders count only as cannibalization or real on-site value, never as harvest.
- By default, harvest goes in a side section only. The main table doesn't change. Wording: "If harvest were credited to off-site: on-site direct −X, off-site +X."
- If the user asks to move harvest into off-site's "credited" layer: reduce on-site direct by the same amount and list harvest as part of off-site.
- Harvest never goes into off-site's "core" layer. Core only counts what is rebuilt from clicks to orders.
- Harvest always gets a most likely value and a range, using the deepest method the data allows (four methods in the details below).
- Industry percentages for harvest or incrementality never go into any number. Direction only.

**Details for Claude (ways to estimate harvest, deepest first):**
1. Amazon Marketing Cloud path analysis (if the user has AMC and off-site tracking events appear in it): share of brand-ad conversions that had an off-site touch before.
2. Off-site tracker report and brand-ad report together: harvest can't exceed the smaller of the two order counts.
3. Timing: in weeks when off-site spend clearly jumped, how many brand-ad orders came in above normal. Avoid big promotions (e.g. Prime Day, Black Friday), since they lift brand searches on their own.
4. Widest range: from 0 to "brand-ad sales × share of days off-site ads were running".

---

## 5. What else to check: the "what ads really brought" list

**One sentence:** check all 12 items below, write a conclusion for each, and pair the good with the bad.

**Rules:**
- Every item gets a conclusion. If it can't be seen, write "can't see this time, because ..., need ...".
- Pair the good with the bad.
- What the user already sees in their own dashboard gets one line of background only. Spend the words on what only shows up when reports are put side by side.

| # | Check | How | Good or bad |
|---|---|---|---|
| 1 | Do organic sales drop when ads are cut or paused? | Find weeks when spend dropped sharply or a campaign stopped. Compare non-ad units before and after. Use other markets or products as a comparison. | Organic drops: ads were holding up sales and rank. It doesn't: those ads were taking credit for orders that would have happened anyway. |
| 2 | Is ad traffic eating organic traffic? | Weekly: ad clicks as a share of Sessions, and organic Sessions. Counts only if ad share rises while organic falls, beyond normal swings. | Bad if ads only replace organic traffic and bring no extra traffic. |
| 3 | Is too much spent on irrelevant search terms? | Search term report: share of spend on irrelevant terms vs share of orders they bring. | Bad if spend share is clearly higher than order share. |
| 4 | Do generic and competitor terms pay off once added up? | Add each search term up across all campaigns. Single campaigns often have too few clicks to show the problem. | Bad if the total can't pay for itself. Without margin data, judge by break-even margin. |
| 5 | Is the same search term bought by several of your own campaigns? | Search term report across campaigns. | Bad: you bid against yourself, and the numbers get blurred. |
| 6 | Is money in the wrong placement? | Placement report: ROAS on product pages vs top of search. | Bad if a placement with meaningful spend returns far less than the others. |
| 7 | Are other products' orders inflating one product's ad ROAS? | Advertised product report: share of "other product" sales. | Store totals are fine, but single-product decisions can go wrong. |
| 8 | Does an extra dollar still pay? | Compare neighboring weeks where spend changed (marginal ROAS). If there are no such weeks, say so. If budgets were only raised when things went well, the result is biased upward; say that too. | Average return can look fine while the last dollars lose money. |
| 9 | Is spend running when you don't hold the Buy Box? | Daily Buy Box share × daily spend by ad type. Sponsored Brands and Sponsored Display can run without the Buy Box and send people to a page another seller converts. | An unseen flow (unseen is not 0; core rules 5.4): flag it, don't call it waste. |
| 10 | During a launch, are ads building something? | Weekly units, rank, review count, and new-to-brand share for brand and display ads. If the period is too short, describe only, no conclusion. | High ACoS during launch can be normal. Judge it against the launch purpose. |
| 11 | Did off-site ads change your brand-defense ads? | All three together: off-site high-intent clicks jump; brand-defense conversion falls; brand-defense clicks flat or slightly up. Only needed when off-site search ads ran. | All three hold: off-site reached the high-intent shoppers first. The buying path changed; no business was lost. |
| 12 | Does each campaign's result match its purpose? | Campaign names, the user's notes. | Brand defense, launch, clearance and competitor attack are each judged differently. |

---

## 6. Before recommending a cut

**One sentence:** first find why it was set up, then check the company's limits. Recommend cuts or increases only with margin data.

**Example:** an automatic campaign has 80% ACoS and looks bad. It turns out it was set up to build reviews for a new product, and the launch period isn't over. It can't go straight onto a stop list.

**Rules:**
- Every campaign, keyword or ad type you'd stop or reduce: first find what it was set up for.
- Purpose unknown: write "purpose unknown, confirm with whoever runs the account". Don't put it on a stop list.
- Check the limits from Stop 1 (company ad-spend rules, agency contract scope). If a recommendation conflicts, write where the conflict is and what each choice leads to. The user decides.
- Without margin data: break-even margin only, no budget cuts or increases (core rules section 7).
- Numbers with a structural flag (Buy Box, stock, new product) never support an efficiency conclusion (module 3).
- If the account is run by another team or an agency: write findings as observations about the structure, e.g. "this campaign group spends X on search terms that bring Y orders", never as someone's fault. Suggestions read "suggest confirming with ...".

---

## 7. What to hand over

1. **On-site ads, direct:** amount, share of total revenue, cannibalization deducted (most likely value and range), overlap deducted, labels, script numbers.
2. **Harvest side section** (if off-site ads ran).
3. **The 12-item list, one row each:** conclusion, good or bad, evidence, how sure, what would confirm it.
4. **Recommendations broken down until someone can act:** which campaign, which search term, which product, what to change, which number to watch, when to check again.
