# Module 3: Structural issues (Buy Box, stock, new products)

> **Written for Claude to follow, and for people to understand.** Follow `01-core-rules.md`; terms are in `glossary.md`.
> **When to use:** in every full analysis. Run it at Stop 2 (Plan), before any main calculation. Structural problems change what every other number means.
> **The most important rule** (core rules section 6, structural issues): calculate everything anyway, add a structural flag, and never draw an efficiency conclusion from a flagged number.
> **How to read:** each section opens with one sentence; most then give an example, followed by the rules. Boxes titled "Details for Claude" can be skipped by people. Claude must follow them.

---

## 1. Why this comes first

**One sentence:** a stockout or a lost Buy Box drops sales. Skip this check and supply problems get blamed on the ads.

**What happens:** when a product is out of stock, or another seller holds the Buy Box, ads stop showing or send shoppers to someone else's offer. Sales fall. An analysis that skips this step blames the ads, the listing, or the market for something the supply side caused.

**Example:** sales of a product fell 60% in a month. Its ad clicks fell too. It looks like "ads stopped working". The Business Report shows Sessions stayed normal, but Buy Box share dropped from 98% to 10%: a distributor took the Buy Box. The ads didn't fail. The orders went to another seller on the same page.

---

## 2. Buy Box

**One sentence:** check daily whether you held the Buy Box, and compare days with and without it.

**Example:** in 30 days you held the Buy Box on 20, with conversion averaging 12% and revenue US$1,500 a day. On the other 10 you didn't: 2% and US$240 a day. This product's daily revenue normally swings about US$300. The gap is far beyond the normal swing, so flag it.

**How to check:** Business Reports by child ASIN: Featured Offer (Buy Box) %. With weekly files, compare weeks first; for any week with a problem, ask the user for that week's daily files to find which days.
- Split the days into "we held the Buy Box" and "we didn't". Compare conversion rate and revenue.
- Flag only if the gap is bigger than this product's normal day-to-day swing.
- Amazon recommends a Buy Box share of 90% or higher before advertising. Show this only as a reference line in the report, not as the threshold.
- If Buy Box share jumps to a new level partway through the period: find the date, and analyze before and after separately.
  - Don't give ads credit or blame for that change.
  - Confidence for any conclusion spanning that date is low.

**What a lost Buy Box does to the numbers:**
- Sessions count every visitor to the listing, no matter who holds the Buy Box. Your conversion rate counts only your sales.
- So your conversion rate always falls when someone else wins the Buy Box. That says nothing about your ads or your listing.
- Buy Box share uses Page Views as its denominator, not Sessions. To estimate "Sessions while we held the Buy Box", don't simply multiply Sessions by Buy Box share. If you do estimate it that way, say it's an approximation.
- Sponsored Products only show when you hold the Buy Box.
- Sponsored Brands and Sponsored Display still show without the Buy Box, and send people to a page where another seller converts them.

**Other sellers or distributors on the same listing:** ask at Stop 1 whether this happens and on which products. If yes:
- Their sales are not in the user's reports. That's an unseen flow (core rules 5.4: unseen is not 0).
- Never treat it as 0. Never use it to call an ad or channel inefficient.
- Write: "part of the demand this ad created was converted by another seller on the same listing; this data can't see how much."
- If the user's company counts distributor sales as its own: say so in the report, and suggest getting the distributor's sales for the next analysis.

**Details for Claude:** find the date where Buy Box share jumps to a new level with a change-point method.

---

## 3. Stock

**One sentence:** find stockout days from the reports first, look at them separately, and estimate lost sales from your own data.

**Example:** a product normally sells 40 units a day and was out of stock for 5 days. Lost sales are about 40 × 5 = 200 units. Check against the same product's days with stock to confirm 40 is a fair level.

**How to find stockouts from the reports** (inventory reports are better, but often missing):
- These three signs together mean a likely stockout:
  - Sessions and units close to 0 for several days in a row;
  - the product disappears from the Business Report;
  - ad impressions for that product drop to 0 across all campaigns.
- Zero ad impressions can also mean someone paused the ads. Both look identical in the report. Only stock records or the user can tell them apart. Label "likely stockout" until confirmed.
- If the Business Report is weekly only, first use daily ad impressions to find suspicious days. If that week's units are also clearly low, ask the user for that week's daily files to confirm.
- Look at the product's impressions across all campaigns, not one campaign. A product often keeps getting impressions through other campaigns after its own campaign is paused.

**What a stockout does to ads:**
- Sponsored Products stop showing.
- Sponsored Display pauses automatically.
- Sponsored Brands keeps running and spending as long as any product in the ad has stock. So spend and orders on stockout days are not data errors. Don't delete them.

**Low stock:** if inventory data shows under 28 days of cover, note "low stock". What actually hurts sales is the real stockout days.

**Lost sales from stockouts:**
- Estimate from this period's own data, e.g. "normal-day sales rate × stockout days", checked against the same product's days with stock.
- Never use a penalty factor from another analysis or an article.
- In module 4 this loss goes to "external events, direct", labeled "stockout".

**After restocking:** rank and sales often don't come back right away. If you judge ads or a listing on the first weeks after a restock, you must say so.

---

## 4. New products

**One sentence:** flag anything listed within 90 days as "new product", and rule out Amazon's automatic new-product lift before crediting ads with its growth.

**Example:** a product listed 40 days ago doubled its sales this month, and off-site ads started in the same month. Amazon gradually shifts new products to their own clicks and sales during this period, and that lifts them with or without ads. So the doubling can't be credited straight to ads.

**Rules:**
- Flag "new product" for anything listed within the last 90 days (Amazon's "New Release" badge looks at the first 90 days).
- Check its own data: if rank and weekly sales are already stable, clear the flag early and say why.
- Amazon ranks new products at first partly on how similar products perform, then shifts to the product's own clicks and sales. This lifts new products on its own, with or without ads.
- Before giving ads credit for a new product's rise, rule this out.
- Use the same product's data from other markets only to check direction, never as numbers.
- There is no published number of days for this shift. The "around day 5" claim has no source (U14 in the external evidence list, `08-external-evidence.md`). Never use it.
- New-product numbers must never be applied to other periods or products.

---

## 5. Spillover between related products

**One sentence:** when one product has a problem, shoppers may buy a sibling instead. This step only finds and flags it.

**Example:** the black version lost the Buy Box on 3/4, and the white version's sales rose 30% that same week. The timing lines up, so flag "possible spillover".

**Rules:**
- A sibling is another color, size or bundle of the same product. When one product's Buy Box, deal or listing breaks, shoppers may move to it.
- Whenever any check above finds a problem, look at related products for unusual growth at the same time.
- If the timing lines up, flag "possible spillover".
- In module 4, evaluate these variants together. The product that received the spillover has off-site spend of 0, so its own off-site ROAS is "not applicable".
- Spillover is only found and flagged here, not sized.

---

## 6. What to hand over

**One sentence:** a structural issues table, one row per flag, saying which conclusions it rules out.

| Product | Market | Flag | Dates | Evidence (which report, which numbers) | Confirmed by user? | Effect on other modules |
|---|---|---|---|---|---|---|

**Rules:**
- "Effect on other modules" says what can't be concluded because of this flag. For example: "no efficiency conclusion for this product's ads from 3/4 to 3/18".
- Also list the flagged days as natural experiments (ads stopped by accident). Module 4 can use them to separate ad effects from other causes.
- In the plan (Stop 2), show the user what you found and where you found it.
- Facts you can read from reports don't need questions. Ask only about facts only the user knows, e.g. "was this paused on purpose?" or "is that seller your distributor?".
