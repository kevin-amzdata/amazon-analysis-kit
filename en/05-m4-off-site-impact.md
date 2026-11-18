# Module 4: How much did off-site ads really sell?

> **Written for Claude to follow, and for people to understand.** Follow `01-core-rules.md`; terms are in `glossary.md`.
> **When to use:** the user wants to know what off-site ads (Google, Meta, TikTok, X, influencers, email, affiliates) did for their Amazon sales.
> **Why it's needed:** Amazon Attribution (Amazon's tracking tool for off-site ads) often undercounts, and many sellers can't use it at all. This module doesn't rely on it. It works out the off-site effect on its own. If Amazon Attribution is installed, use it to check the answer (section 13).
> **How to read:** each section opens with one sentence; most then give an example, followed by the rules. Boxes titled "Details for Claude" can be skipped by people. Claude must follow them.

---

## 1. The whole method: split total revenue into eight parts

**One sentence:** split total revenue into eight parts. The eight parts must add up to total revenue exactly, to the cent.

**The eight parts:**

| Part | Plain meaning |
|---|---|
| Baseline sales | What you'd sell anyway, without this push |
| On-site ads, direct | Bought after clicking an Amazon ad, minus people who would have bought anyway |
| Off-site ads, direct | Clicked an off-site ad and went all the way to an order |
| External events, direct | Caused by something other than ads: big sales, a viral post, a stockout (a stockout is negative) |
| On-site indirect, off-site indirect, external indirect | Extra organic orders that followed the three sources above, split back to those sources |
| Unexplained | What no evidence can explain |

**Order:**
1. Calculate the three visible parts first: baseline, on-site direct, off-site direct.
2. Total revenue minus those three = "leftover revenue".
3. From leftover revenue, take out what known outside events caused (external direct).
4. Only the part with evidence becomes indirect.
5. Whatever remains goes to unexplained.

Every part gets a "most likely value" and a "range".

**Full example (made-up numbers):** one product, one market, 30 days. Total revenue 1,000,000. Off-site spend 50,000.

| Step | What | Result |
|---|---|---|
| 1 | Baseline: off-site was paused for three weeks last month. Week 1 still had leftover effect from earlier ads, so skip it; use the daily non-ad sales from the last two weeks | 550,000 |
| 2 | On-site direct: ad reports say 260,000, minus 60,000 from people who would have bought anyway | 200,000 (2,000 orders) |
| 3 | Off-site direct: per channel, "clicks × bridge page pass-through × conversion × average order value" | 100,000 (1,000 orders) |
| 4 | Leftover: 1,000,000 − 550,000 − 200,000 − 100,000 | 150,000 |
| 5 | External direct: one week had a game event; compared with a market that got no extra off-site spend | 60,000 (600 orders) |
| 6 | Indirect total: after direct orders rose, organic orders rose within 14 days, and more direct meant more organic; the existing upward trend is already removed | Most likely 80,000 (range 30,000 to 90,000) |
| 7 | Split by extra direct orders, each order equal: off-site 1,000, on-site 2,000, external 600, total 3,600 | Off-site indirect 22,222; on-site indirect 44,444; external indirect 13,334 (the last takes the rounding so the three sum to exactly 80,000) |
| 8 | Unexplained: 150,000 − 60,000 − 80,000 | 10,000 |

Sum: 550,000 + 200,000 + 100,000 + 60,000 + 22,222 + 44,444 + 13,334 + 10,000 = 1,000,000.

**Off-site ROAS:**
- Core 2.0: off-site direct only. 100,000 ÷ 50,000.
- Credited 2.44: direct plus indirect. **This is the main number.** (100,000 + 22,222) ÷ 50,000.
- Ceiling 2.64: also gives off-site all of unexplained. (122,222 + 10,000) ÷ 50,000.

The report must say clearly: this ROAS is "the extra effect on top of normal advertising". It does not mean "without off-site, only the baseline would be left".

---

## 2. What data you need

**One sentence:** daily sales, daily ad data, and a period to compare against.

**Must have:**
- Business Reports data for every child ASIN (each color or size has its own product code), one file per week is enough, daily is better: the analysis period, the comparison period, and the 4 weeks before the analysis period.
- On-site ad reports (module 2).
- Daily clicks, impressions and spend for every off-site channel and campaign, plus each campaign's landing page. Search channels (such as Google Search ads) also need the search terms report.
- Whole-store sales for the same dates (to remove seasonality and as a comparison).

**Nice to have:**
- Web analytics for the bridge page (your own page between the off-site ad and Amazon): visitors, clicks out to Amazon.
- A period of 3+ weeks with off-site fully paused.
- Last year's same period.
- Margin data (core rules section 7: no margin data, no recommendation to scale up, cut budget, or stop).
- Amazon Attribution reports, if installed (section 13).

**Ask the user at Stop 1 (only they know):**
- Which channels ran.
- For each channel and market: links straight to Amazon, goes through a bridge page, or both.
- Each channel's currency, and whether tax is included.
- Whether any campaign sends people somewhere the user can't see sales (another seller, a distributor's listing, a brand storefront).
- Whether Amazon Attribution is installed.

---

## 3. Order of work

1. Baseline (section 4)
2. On-site direct (module 2)
3. Off-site direct per channel (section 5)
4. Leftover revenue (section 6)
5. External direct (section 7)
6. Indirect total and how it's split (sections 8, 9)
7. Unexplained (section 11)
8. Sum check and range simulation (section 11)
9. Off-site ROAS (section 12)

**Before calculating:** for every number you'll estimate, pick the methods and rank them first, second, and so on. Write them into the plan. The main number uses the first one. Switching methods after seeing results is not allowed (core rules 5.7).

---

## 4. Baseline: what you'd sell anyway, without this push

**One sentence:** what you'd sell with your normal ads and the people who find you on their own. The long-run effect built up by steady past advertising is included here too.

**Example:** off-site was paused for three weeks last month. In week 1, earlier ads were still wearing off, so it doesn't count. In the last two weeks, daily non-ad sales averaged about 18,333. Times 30 days is about 550,000, the baseline in the section 1 example.

**Rules:**
- The period used to calculate the baseline (e.g. the pause), and each of the three comparison periods (main baseline, alternate A, alternate B; core rules section 9), must use the same method as the analysis period, including how "would have bought anyway" is subtracted.
- Write which method you used, and why you didn't use a better one.

**How to find it, best to worst:**
1. **Find a period with zero off-site spend.** Baseline = daily non-ad sales in that period, scaled to this analysis period.
   - Skip the first week after the pause (default 1 week). Earlier ads are still wearing off. In markets that were ever paused for 3+ full weeks, you may estimate it from the data, up to 4 weeks (see details below).
   - Too early: leftover effect is still mixed in, so off-site looks worse than it is. Too late: the long-run effect is fading too, so off-site looks better than it is. Write both biases.
   - Always check three things: is the daily level steady; did it hit a promotion or event; how far is it from the midpoint of the analysis period. If a check fails, still calculate. Fix what you can (e.g. remove the trend). If you can't, widen the range and lower confidence.
2. **Convert Best Seller Rank to sales.** Only with the right category, a reliable rank-to-sales relationship, and after calibrating with this product's own data in this market. Low confidence.
3. **If neither works, use how spend went up and down.** Compare each week's off-site spend with its non-ad sales, and work back to "sales when off-site spend is 0". Low confidence.

**Baseline of 0:** only when you can prove there are no organic sales, e.g. a brand-new product with no non-ad sales yet. A mature product at 0 means every sale is credited to ads. Not allowed.

**Seasonality:** adjust only when really needed.

**Details for Claude:**
- Leftover buffer default: 1 week. If this market was ever paused for 3+ full weeks in a row, estimate it from the data: when non-ad sales stop falling and return to their normal range. Max 4 weeks. Use the earliest stable full weeks after the buffer.
- Method 3 is the spend-variation method: weekly non-ad sales against this week's plus previous weeks' off-site spend; take the level at "spend = 0".
  - Weeks where spend was changed because of how business was going must be listed and excluded before looking at sales.
  - If spend relates as strongly to the previous week's sales as to the next week's, spend is chasing demand. Label low confidence.
  - Use only the "spend = 0" level. Never use the slope (extra sales per extra unit of spend).
  - Precision level: widest range. Write the bias direction: baseline too low → off-site ROAS too high.
  - Range: from 0 to the upper limit set by the sum rule.
- Seasonal adjustment: median change of the whole store over the same weeks, excluding new products. Category decline is estimated from this period's own data.

---

## 5. Off-site direct: clicked an off-site ad and went all the way to an order

**One sentence:** per channel: clicks × bridge page pass-through × conversion rate × average order value.

**Example:** Google Search ads got 1,000 clicks. 60% of bridge page visitors clicked through to Amazon. On Amazon, 10% ordered. Each order is 1,000. Off-site direct = 1,000 × 60% × 10% × 1,000 = 60,000 (60 orders).

**Rules:**
- This is the only main source for off-site numbers. Always ≥ 0.
- Never work off-site direct backwards from leftover revenue. It is not capped by leftover, and it is not pushed down because total revenue fell.

### 5.1 Where each of the four numbers comes from

**Clicks:** Google hides some search terms. Add them back.
- Example: campaign total clicks 1,200, search terms report shows 1,000 → multiplier 1.2. Multiply every group by 1.2.

**Route:**
- Straight to Amazon: start with pass-through 1. All bridge page rules are "not applicable".
  - But before calculating, always check how much Sessions of the landing page's whole variation family rose when off-site clicks rose. Register the comparison periods first (e.g. the days around a pause) and give a range. If each click adds clearly less than 1 extra Session (e.g. only 0.4), use that ratio instead, labeled "derived". Write the gap, and list the possible reasons without choosing one (clicks that never loaded, repeat visits counted once, people who would have come anyway). Never state one reason as fact, and never put it in a heading. Don't wait until the sum exceeds total revenue to find out.
- Through a bridge page: find pass-through in the order in 5.3.
- Both: calculate the two parts separately, then add them.

**Five search groups** (only for search channels that have a search terms report): brand, specific, mid, generic, irrelevant. Social and display channels aren't grouped; use that channel's own measured conversion.

**Average order value:** same market, same period, actual value after discounts. Never from another market.

### 5.2 Conversion rate

- The main number always comes from this period's own data: the product's conversion in Business Reports, or grouped conversion from web analytics if available.
- Any "higher intent converts better" premium (e.g. "brand searchers buy more", "specific searchers buy more"), for any group, can't go into the main number without the user's own data behind it.
- The brand group may get a wider range: low end 1× the average conversion, high end up to 2× (a checked outside study; see E2 in `08-external-evidence.md`). This sets the range only. The main number doesn't change.
- When a group has few clicks, pull its conversion toward the channel average. The fewer the clicks, the closer to the average. Never use a small group's raw number directly.
- If you use the whole-store conversion (which includes on-site ad orders), tell module 2 to estimate the on-site/off-site overlap.

### 5.3 Bridge page pass-through

**One sentence:** of the people who reach the bridge page, how many click through to Amazon.

**Find it in this order:**
1. Bridge page web analytics: visitors and clicks out to Amazon (measured).
2. A "click to Amazon" button conversion set up in the ad platform (measured or derived).
3. Work it back from how much Amazon Sessions rose when off-site clicks rose (derived).
4. Borrow from the same bridge page on other dates in this analysis (borrowed within this analysis).
5. None of these: an assumption, range 0 to 1, low confidence, first item on the data request list.

**Three more rules:**
- Never use a popular "typical pass-through rate". None has a reliable source.
- If unpaid traffic (influencers, press, organic posts) also goes through the same bridge page, the analytics mix in other visitors. Label "contaminated" and lower confidence.
- A bridge page filters out casual browsers, so people who click through are more likely to buy. That doesn't mean many people click through. Don't infer one from the other.

### 5.4 When data is missing: dropping a level

**One sentence:** start with the most accurate method. Drop a level only when it really can't be done. Each drop needs the four steps in core rules 5.3: write what's missing; lower confidence and widen the range; write which data would bring it back up; label which level you used.

1. **Measured:** search terms report, measured pass-through, measured conversion. Full five-group calculation.
2. **Derived:** no search terms report, but ad groups are already split by intent (brand group, problem-keyword group, mixed group): calculate by ad group. If there are no such groups either, use one fixed average conversion for the whole period.
3. **Borrowed within this analysis:** for days when a tracker was off, fill from the same tracker's other dates. Give a range. Low confidence.
4. **Bounds only:** only an outside source's high or low value.
5. **Widest range:** from 0 to "total revenue − baseline − on-site direct − other channels", split across channels by share of clicks.

### 5.5 Could anything be missed? (tracking gap check)

**One sentence:** ask first: is every number recorded on a server? If yes, nothing is missed. Write one line of reasoning and stop.

**Example:** clicks come from the Google Ads account; conversion and order value come from Business Reports. All server-side. A shopper on an iPhone, jumping between apps, or ordering on a laptop instead still shows up in Business Reports. Nothing is missed. Bridge page data counts only if it's server-side too; if it's browser-recorded, measure how much it misses (section 13).

- Most cases end here. The tracking gap multiplier is 1.
- Only browser-recorded data (such as Amazon Attribution) can miss sales. If you use it, measure how much it misses (section 13).
- Never multiply together the various popular "loss rates".

### 5.6 A tracker reads 0

**One sentence:** first confirm the tool was actually recording then (core rules 5.4).

- If it wasn't recording: give off-site direct a range from 0 to an upper limit. Write "not observed in this period (tracker not working)".
- Never write "no sales", and never give a range that is only 0.

### 5.7 The only time off-site direct may be revised down

Baseline + on-site direct + off-site direct is more than total revenue. Then find which input is too high (conversion, pass-through or order value). If you can't find the cause, never just shrink some ratio.

### 5.8 Variations

The ad sends people to color A, and they buy color B: assess A and B together. B has no off-site spend of its own, so its off-site ROAS is "not applicable".
- For off-site direct, use Sessions and orders for the whole variation family, not just the landing variation. Looking at A alone mislabels shoppers who switched to B as indirect.

**Details for Claude (section 5):**
- Hidden search term multiplier = campaign total clicks ÷ clicks with visible search terms. Clicks = visible clicks × multiplier. Off-site direct = sum over groups of (clicks × pass-through × conversion × order value).
- Brand group: upper limit at most 2× the blended conversion (the average of brand and non-brand together), lower limit 1×. You may add a "scenario value", by default the 75th percentile of this uneven range (line up 100 possible values; take the 75th), labeled external, low confidence, outside the sum and outside conclusion sentences. Wording: "conservative estimate X; if the brand-term premium holds, up to Y". The main number and the sum check always use the main value.
- Pulling toward the average (shrinkage) has no click threshold. Apply it to every group.
- Level 2 fixed average conversion with no groups = (sum of "total revenue − baseline" over tracked periods) ÷ (sum of clicks reaching Amazon over the same periods), applied month by month. Over the whole period it matches exactly. That's built into the method and is normal.
- Level 5: if there's no click share, split by spend share; if none, split evenly. Write which.
- Upper limit when a tracker reads 0 = the smaller of "the borrowed estimate's upper limit" and "total revenue − baseline − on-site direct".

---

## 6. Leftover revenue

**One sentence:** total revenue − baseline − on-site direct − off-site direct (all channels, main values).

**It has only two uses:**
1. Making the eight parts add up.
2. Capping the three indirect parts together.

How big leftover is can never be used to calculate any off-site number, and never proves off-site works.

---

## 7. External direct: what things other than ads caused

**One sentence:** first take known outside causes out of leftover revenue. Each one gets an amount and a range.

**Events to check:**
- Big sales, lightning deals, price changes, page changes
- Games, sports events or holidays related to the category
- Influencers, press, viral posts (unpaid traffic)
- Competitor moves
- Stockouts, losing the Buy Box (negative)
- Growth from a new product launch itself (module 3)
- Demand pulled forward or pushed back around big sales

**Example:** during a game event week you added off-site spend in the US but not in the UK. The UK also sold 20% more that week. So that 20% looks more like the event than off-site.

**Rules:**
- Outside research only decides whether something belongs here. The amount always comes from the user's own data, e.g. comparing with a market or product that had the same event but no extra off-site spend.
- Rising search interest measures searchers, not the user's sales. Never multiply revenue by it.
- If you write 0 here, write "checked, found nothing", and what you checked.
- Anything moved here can't be pulled back into indirect.

---

## 8. Indirect effects: only with evidence

**One sentence:** after direct orders rose, did organic orders rise after them? If yes, and bigger rises were followed by bigger rises, that's evidence.

**Example:** in week 2, off-site direct rose by 200 orders. In the next 14 days, organic orders were 150 above normal. In week 5, off-site rose by 400; in the next 14 days, organic was 280 above normal. Bigger rises, bigger follow-ups. That's evidence.

**Not evidence:** "organic sales were higher than they should be". "Should be" is the baseline itself. Whenever leftover is positive, that sentence is true, so it proves nothing.

**Rules:**
- Before looking at numbers, register three windows: 7, 14 and 28 days. The main number uses 14. Report all three. Never pick.
- **Check the timing first:** if organic sales were already rising before direct orders rose, something else is pushing. Only the part above the earlier trend counts.
- **Find comparisons:** budget running out, ads being disapproved, stockouts, different products or markets starting at different times are all natural experiments. Also find markets that had the same event without extra off-site spend. List these before looking at any result.
- **Rank and conversion are support only.** Never evidence on their own.
- Checks decide confidence, they don't block the calculation (core rules 5.11). If clearly disproved: measure the bias, subtract it, then widen the range.
- **Indirect is the exception to "unclear means use it".** If the timing-and-size relation can't be told apart from zero (its 90% range includes 0), the money stays in unexplained. Indirect's most likely value is 0, labeled "not shown by this data", with the top of its range at the cap. Credited ROAS then equals core ROAS; the ceiling ROAS shows what it would be if the indirect effect is real. Never write "no indirect effect".
- Effects showing up this period from last period's ads are listed separately as "carried over from earlier", not counted in this period's ROAS.

**Cap:** the three indirect parts together can't exceed "leftover − external direct". If that is 0 or negative, indirect is 0, and the reason goes into the unexplained note. Check this in every simulation run.

**Details for Claude (section 8):**
- Cut the period into days or weeks. After each source's extra direct orders rose (off-site direct orders, on-site direct orders after cannibalization, external direct orders), did organic units above baseline rise within the window; did more direct mean more organic.
- Timing check: extend the trend from before the push. Only the part above that line counts.
- Rank: compare with the comparison group, not whether rank itself rose or fell. "Would have dropped more but didn't" also counts as help. Worse than the comparison group by more than about twice its normal swing counts as disproved.
- Split conversion change into "quality" (ad and non-ad traffic each converting differently) and "mix" (share of ad traffic changed). A higher ad share mechanically lifts conversion, so the "mix" part is never evidence.
- The cap is the positive part of "leftover − external direct", whether external direct is positive or negative.

---

## 9. Splitting indirect across the three sources

**One sentence:** split by each source's extra direct orders. Every order counts the same.

**Example:** see step 7 in section 1. Off-site 1,000, on-site 2,000, external 600: the 80,000 indirect is split 1,000 : 2,000 : 600.

**Rules:**
- The split follows "truly extra orders", not whatever the ad platform credited:
  - off-site: off-site direct orders;
  - on-site: on-site direct orders after removing "would have bought anyway";
  - external: orders from external direct.
- Baseline orders take no share.
- **Every order weighs the same (1:1:1). No channel gets a multiplier.** Claims like "Google traffic counts 3× for ranking" or "off-site traffic gets extra algorithm weight" have no reliable source (see U8 in `08-external-evidence.md`). The only basis for different weights is the user's own experiment, e.g. switching off-site ads on and off in turns, or comparing regions with and without them. Until then, equal weight.
- The split only divides. It never creates extra money.
- If off-site direct is 0 orders this period, off-site indirect is 0 too. Write that the formula produced it.

---

## 10. When leftover revenue is negative

**One sentence:** first check for calculation errors, then whether off-site hurt sales. Only if neither, attach a label.

**Check in order:**
1. **Three common errors:**
   - baseline (the three checks in section 4, seasonality);
   - "would have bought anyway": same method in both periods?
   - on-site and off-site counting the same order twice.
   Fix and recalculate if wrong.
2. **Is off-site direct too high?** (section 5.7)
3. **Did off-site actually hurt organic sales?** All three must hold: irrelevant search term clicks surged while conversion collapsed; rank fell afterward; stockouts, Buy Box and competitors are ruled out. Actually check and write the result. Never assume it. Even if true, off-site direct plus off-site indirect can't go below 0.
4. **If none of these, use three questions to choose a label.** They only choose a label. They never create or change a number.
   - Was demand used up early? A sales peak 1–4 weeks before the analysis period (big sale, discount), about the same size as this drop → label "demand pulled forward", goes to external direct. No data for the prior 4 weeks → write "can't tell", go to the next question. Don't guess.
   - Did the base level shift down? Rule out in order: competitors (they peaked, you hadn't before), stockouts, seasonality (needs last year's data). These go to external direct. If all are ruled out → unexplained, labeled "unclassified".
   - Right after a big sale? First suspect a delayed effect. In the unexplained note write "possibly a delayed effect (diagnosis only)". This label can never be evidence of any indirect effect.

**Reminder:** before big sales, people often wait, so sales dip first. Negative leftover then is an outside cause by default. Never use it to say off-site doesn't work.

---

## 11. Unexplained, the sum check, and ranges

**Unexplained:** holds only two things: swings no evidence can explain, and parts that were disproved and still don't hold after fixing.
- Always write its three components: indirect that didn't hold up; estimation error in baseline and other estimates; outside causes truly unknown.
- Add: how much unexplained changes if the baseline is 5% or 10% too high or too low.
- It is labeled "not off-site" and only counts toward the ceiling ROAS.

**Sum check:** the eight parts add up to total revenue exactly, to the cent. Also check:
- indirect doesn't exceed the cap;
- external and unexplained aren't in the core or credited ROAS;
- scenario values and harvest (by default) aren't in the sum;
- the actual non-ad orders fall inside the 90% range of the estimated non-ad orders.

**Ranges:** every part gets a middle 90% range (under the current assumptions, about a 90% chance the true number falls inside). Ranges come from a computer simulation: vary the uncertain numbers at random, recalculate thousands to tens of thousands of times, and see where results land.

**Details for Claude (simulation):**
- Fixed: measured numbers (total revenue, on-site campaign totals, measured order value, measured pass-through).
- Varied: estimated conversion by group, borrowed or assumed pass-through, estimated order value, cannibalization share, overlap, baseline error, harvest, and every other estimate.
- Each distribution is centered on the main table's most likely value. With the user's own data, use its spread. Without it, high/medium/low confidence use ±10% / ±25% / ±40%, labeled "default, no basis", and report whether conclusions change when ranges widen or narrow.
- Every run is a full scenario: draw inputs → off-site direct → leftover → external → indirect within the cap → eight parts summing to total revenue → ROAS. Any run that breaks the sum or the cap means the code is wrong.
- Drop physically impossible draws (e.g. a ratio above 1) and report how many.
- Fix the random seed (so every rerun gives the same result). Check every 2,000 runs; stop when simulation error is under 1% of the range width; max 50,000 runs.
- Report the middle 90% range for every number, and which uncertain input widens the off-site range most. That input is the first item on the data request list.
- The simulation only carries uncertainty forward. Never tune it to hit a target.

---

## 12. Off-site ROAS

**Three layers:**
- **Core** = off-site direct ÷ off-site spend.
- **Credited (main number)** = (off-site direct + off-site indirect) ÷ off-site spend.
- **Ceiling** = (off-site direct + off-site indirect + all unexplained) ÷ off-site spend.

**Reading them together:**

| Core | Credited | Meaning | Check |
|---|---|---|---|
| Low | High | Weak direct orders, strong indirect | Bridge page drop-off, search term quality |
| High | About the same | Direct works, no visible indirect | |
| Low | Low | Something is fundamentally wrong | |
| High | High | Healthy | |

The ceiling is reference only.

**Rules:**
- All three are always ≥ 0. If off-site spend is 0, write "not applicable".
- **Same days on top and bottom.** The main ROAS always uses all off-site spend in the analysis period, including spend on stockout or lost-Buy-Box days, and the headline uses this version. A version that leaves out flagged days may be shown next to it, labeled "if there had been no stockout"; its revenue and spend must cover the same days.
- Every layer gets a **break-even margin** (the margin needed not to lose money = spend ÷ the revenue it brought). Without margin data, the answer is this sentence: "it pays off if your margin is above X%".
- If there's a previous period, give the **marginal ROAS**. Below 1 always loses money.
- Harvest (someone clicks off-site, doesn't buy, later searches your brand and buys through a brand ad) goes in a side section by default (module 2). If the user wants it included: subtract the same amount from on-site direct and include it in credited and ceiling. Never in core.
- **Campaigns that send people where the user can't see sales** (another seller, a distributor's listing, a brand storefront): by default their spend is left out of the user's own ROAS denominator, listed as "not applicable" with the spend shown. Ask the user at Stop 1 whether to use another rule. Never call them inefficient (core rules 5.4: unseen is not 0).
- Anything with a structural flag (Buy Box, stockout, new product): calculate and list it, but no efficiency conclusion.

**Details for Claude:** say "clearly diminishing" only when the marginal ROAS's entire 90% range sits below the overall ROAS's range.

---

## 13. When Amazon Attribution is installed

**One sentence:** compare your own off-site direct with it, and measure how many times it undercounts.

**Example:** you calculated off-site direct at 100,000. Amazon Attribution recorded only 80,000. Calibration multiplier = 100,000 ÷ 80,000 = 1.25. It undercounted by about a fifth.

**Why it undercounts:** it only counts clicks, only the last click within 14 days, and the tracking tag must survive to the final Amazon URL. iPhone link privacy protection, switching between apps, changing devices, buying after 14 days, and not being signed in all make it miss sales, and from outside you can't tell how much each cause accounts for.

**Rules:**
- Don't estimate each cause. Measure the total: calibration multiplier = off-site direct rebuilt from clicks to orders ÷ sales recorded by Amazon Attribution. Per channel, per market.
- Calibrate only with promoted product conversions. "All conversions − promoted product" is the halo order signal (click A, buy B from the same brand). Record it, but keep it out of calibration.
- With a bridge page: add the tracking tag at the step where the bridge page sends people to Amazon, and make sure it's in the final URL. The bridge page must not auto-redirect to Amazon (Google's landing page rules don't allow it). A real page that people click through is fine.
- Calibrate outside big sales first. Measure big sales separately.
- Later periods must reuse the multiplier, as long as channels, bridge pages and market mix haven't changed.

---

## 14. What to hand over

1. **The eight parts:** amount, share of total revenue, most likely value and 90% range, labels, script number.
2. **Off-site ROAS per channel:** spend, off-site direct, off-site indirect, core / credited / ceiling, break-even margin, structural flags.
3. **Five-group detail for every search channel:** clicks, conversion (after pulling toward the average), order value, which groups were pulled, how the brand group range was set, and why.
4. **The unexplained note:** three components, and the change if baseline is 5% or 10% too high or too low.
5. **Side section:** scenario values, harvest, effects carried over from earlier. Not in the sum, not in conclusion sentences.
6. **Data request list:** sorted by how much each item would narrow the off-site range. Usually at the top:
   - bridge page web analytics with a "click to Amazon" event;
   - a test switching off-site ads on and off, staggered by product or market;
   - daily rank data.
