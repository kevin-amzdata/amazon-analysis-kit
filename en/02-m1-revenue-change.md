# Module 1: Why revenue changed

> **Written for Claude to follow, and for people to understand.** Follow `01-core-rules.md`; terms are in `glossary.md`.
> **When to use:** the question is "why did sales go up or down". Most analyses start here.
> **This module only reads reports and explains.** It never changes any number in the eight-part revenue split (module 4).
> **How to read:** each section opens with one sentence; most then give an example, followed by the rules.

---

## 1. What this module answers

**One sentence:** module 4 answers "where did each dollar come from". This module answers "why did the total change".

**Fixed method:** break the change down with arithmetic first, then list candidate explanations. Never jump straight to a cause.

**Example:** the same drop in total revenue can hide three different problems:
- Product A lost 70% of its traffic: a traffic problem.
- Product B kept its traffic, but its conversion rate halved: a conversion problem.
- Product C fell with its whole category: a market problem.

Mixed together, all three are invisible.

---

## 2. What data you need

**One sentence:** Business Reports by child ASIN, plus the chosen comparison periods.

**Must have:**
- Business Reports by child ASIN, for the analysis period and the comparison periods, by week or by day. Fields: Sessions, Page Views, units, ordered product sales, Unit Session Percentage, Featured Offer (Buy Box) %.
- The comparison periods chosen under core rules section 9 (how to pick comparison periods).

**Nice to have:**
- The same data for the whole store, not only the products in scope. Used to tell "this product's problem" from "the whole store's problem".
- Ad reports (module 2). Used to see whether traffic changes line up with ad changes.
- Last year's same period.

**When data is missing:** say what's missing, add it to the data request list, and continue at a lower precision level.

---

## 3. Step 1: Classify the overall change

**One sentence:** look at total Sessions, units and conversion over the period, and put the change into one of four types.

| Type | Traffic | Units | Conversion | What it means |
|---|---|---|---|---|
| Hitting the ceiling | Enough or flat | Don't respond to more traffic | Slowly falling | Traffic isn't the problem. Conversion is the limit |
| Traffic collapse | Drops sharply | Drop with it | May even rise | The top of the funnel disappeared |
| Competitor erosion | Flat | Fall | Fall | People still come. Someone else converts them |
| Healthy growth | Rises | Rise | Rises | Real demand is growing |

**The key test:** do units respond to traffic? That separates "hitting the ceiling" from the other three.

**Example:** Sessions rose 30%, units rose only 2%, conversion slowly fell. This looks like hitting the ceiling: traffic is coming in, and conversion is where it's stuck. (Whether to change budget is written in Step 7 under the "business judgment" rules.)

---

## 4. Step 2: Break down every product (required)

**One sentence:** split each product's revenue change into four factors: traffic, conversion, average order value, Buy Box share.

**Example:** a product's Sessions fell from 10,000 to 8,000. Conversion, order value and Buy Box share didn't change. Revenue fell 20%, all of it from traffic. A traffic problem.

**Rules:**
- Do it for every product and every comparison.
- Four factors: traffic (Sessions) × conversion rate × average order value × Buy Box share.
- Use measured Business Reports numbers. Label "measured".
- This is an accounting calculation. After doing it once, check it with a second, separately written calculation. The four factors multiplied must give back the revenue change exactly. A separate script checks this.
- Put each product in one class: traffic problem, conversion problem, price problem, structural problem (Buy Box, stock; see module 3), or healthy.

**Check the Buy Box before calling it a conversion problem:**
- Sessions count every visitor to the listing, no matter who holds the Buy Box.
- Your conversion rate counts only units you sold yourself, but divides them by all Sessions.
- So when another seller holds the Buy Box, your conversion rate drops, for reasons unrelated to your ads or your listing.
- Check Buy Box share before calling anything a conversion problem.

**Compare with the whole store:**
- If whole-store data is available, put products outside the scope in the same table.
- If everything moved together, it's a store or market problem, not a single-product problem.
- If whole-store data is missing, say so. Don't guess.

---

## 5. Step 3: Compare with other periods (required)

**One sentence:** compare against each of the three comparison periods, registered in advance.

**Rules:**
- Compare against the main baseline, Alternate A and Alternate B (how to pick them: core rules section 9). Register all three before running any comparison code.
- Compare only products sold in every period being compared. List new and discontinued products separately.
- If a product can't be compared (new, relisted, changed ASIN), say which and why. That statement counts as a valid result.
- If a change sits inside the normal fluctuation range, write "too small to tell apart from normal ups and downs".

---

## 6. Step 4: Check whether totals hide differences (required)

**One sentence:** a combined number can hide products moving in opposite directions.

**Example:** products A and B have similar Sessions and the same starting conversion rate. Store-wide conversion is flat; broken down, A rose 30% and B fell 30%. The total looks fine, but both products changed a lot, and each needs its own explanation.

**Rules:**
- Break down every combined number: store-wide conversion, averages across products, totals across markets.
- If products split in direction or differ a lot, flag "the total hides differences" and show each product's own result.

**With several markets:**
- The same product doing badly in many markets points to the product itself (fit, price, reviews), not to ads.
- Markets moving in different directions rule out a single global cause.
- Always analyze each market separately. Never add markets together first and then split.

---

## 7. Step 5: Check which products the landing page shows (required when off-site ads exist)

**One sentence:** if an off-site landing page shows products you don't track, that channel's off-site numbers are only "at least this much".

**Example:** a Google ad leads to a page with 5 products. You track 3. Sales of the other 2 are invisible to you, so this channel's number is a lower bound.

**Rules:**
- Compare what each off-site channel's landing page actually shows with the list of products you track.
- If the page shows products you don't track, write "at least this much", never a precise number.
- Clicks that end on another seller's offer or a page you can't see are an "unseen flow" (core rules 5.4: unseen is not 0). Never treat them as 0. Never use them to say the channel is inefficient.

---

## 8. Step 6: Outside context

**One sentence:** do outside research only when the breakdown points to the category or the market, and the user's own data can't tell the explanations apart.

**Rules:**
- Propose it to the user first. Whether to do it is their call.
- If web access is on, search. Remove brand and product names from search terms; describe the category instead.
- Trace every claim to an original source: official page, patent, paper, primary data. Many articles copying one blog count as one source.
- Each research question ends as one of three: confirmed, disproved, no reliable source found. "No reliable source found" is a complete answer. Never fill it in yourself.
- Note when you saw anything on a live web page. What you see today is not a fact about the analysis period.
- Research only decides the category, e.g. "this drop belongs to an external event". The amount always comes from the user's own data.
- Map every research result to specific products: "explained by outside factor" or "not explained by outside factor". Research that doesn't land on a product isn't finished.
- Calculate period-over-period and year-over-year changes yourself. Never take a search result's word for "sales are down this year".

---

## 9. Step 7: Pull it together (required)

**One sentence:** write a short "cause map": the same total change, several different problems underneath.

**Example:** "Total revenue −15% (measured), made of three things: product A's Sessions fell, about 80% of the drop (measured), pointing to a rank drop (inference, low confidence); product B didn't hold the Buy Box for two weeks (measured, structural flag); product C followed its category into a slow season (confirmed by outside research)."

**Cause map rules:**
- For each product: a one-sentence conclusion, the main evidence, what outside research added.
- Never deliver tables without this text.

**Then write what it means for action:** label it "business judgment" and keep it apart from the analysis.
- Where to push, where to stop or reduce, where to get data before acting.
- Channels with unseen flows never get "stop" or "reduce". Write "get data that can see that part, then decide".
- Without margin data: direction only, no amounts, no budget cuts or increases (core rules section 7: recommendations need margin data).
- Numbers keep their original labels. Being in a recommendation doesn't make them more reliable.

---

## 10. Format for every finding

**One sentence:** every finding has three parts. Missing any part means it isn't finished.

1. **Symptom:** the arithmetic result, with the number. Label "measured".
2. **Candidate explanations:** at least two competing ones. If there is only one, say why the others are ruled out.
3. **Data needed to tell them apart, and whether you have it:** have it, or missing. Missing data goes on the data request list as: what's missing → which number it affects → what precision level it would reach.

**Without that data:**
- Never write "because". Write "points to ..., needs ... to confirm".
- Still give the most likely direction, how sure, and what would confirm it (core rules section 8: a conclusion never stops at "can't tell").

**Example:** "Product A Sessions −70% (symptom, measured). Candidates: organic rank fell, or last year's same period had more ad spend. To tell them apart: rank history and last year's ad impressions (missing; added to the data request list). Most likely rank fell, because this year's ad impressions are flat while Sessions dropped (inference, low confidence)."

---

## 11. When to dig deeper on your own

**One sentence:** if the data you have can tell the explanations apart, dig deeper without asking.

**Rules:**
- Stop and ask only when you need new data or outside research.
- Before digging into a layer, write why it's worth it, e.g. it accounts for most of the change. Don't dig just because something looks odd.
- Stop when the result is something a person can act on, or when the data runs out.
- In the chat, give one summary paragraph. Details go in the analysis log; expand when the user asks.
- Findings outside ads (listing, price, stock) go into the report too.
- If the report will be shared with other teams, write them as observations about structure and channels, never as blame on a team.
