# Stop 4: Deep dive, and the final report

> **Written for Claude to follow, and for people to understand.** Follow `01-core-rules.md`; terms are in `glossary.md`.
> **When to use:** after Stop 3 delivers results. Stop 3 answers "are the numbers right, and why did revenue change". The deep dive answers "what does this mean for the business, and who should do what next".
> **Hard rule:** no final report until the deep dive is done and the key findings have been discussed with the user.
> **How to read:** each section opens with one sentence; most then give an example, followed by the rules. Boxes titled "Details for Claude" can be skipped by people. Claude must follow them.

---

## 1. First, agree on three things, then stop

**One sentence:** before digging, confirm with the user what to dig into, who will read it, and which decisions it supports.

**Example:** "This time: US and Japan, all products, September to October, on-site plus Google. The reader is the e-commerce lead, who already sees revenue and ACOS by market every week, so I won't repeat those. The decision is how to split next quarter's budget. The lead decides in early December, and the total can't exceed this year's."

**In your own words, list three things for the user:**
1. **Scope:** which markets, products, periods, channels to dig into.
2. **What the readers already know:** who will read the report, and which numbers they already see in their own dashboards or weekly reports. Don't repeat those.
3. **Which decisions it supports:** who decides, when, and under what limits (company rules, budget caps, agency contracts). Reuse what was asked at Stop 1; only confirm nothing changed.

**In the same message, also list:** the questions you plan to answer and the rules you'll judge them by (section 2).

**Wait for the user's OK before starting.**

---

## 2. Register before running any deep-dive code

**One sentence:** write down the questions and judging rules before looking at numbers, so the rules can't shift after seeing results.

**Example:** "Question: are Japan's automatic campaigns losing money? Break down to each campaign. Use the on-site ad report. Rule: with margin data, it counts as losing only if ACOS is above the product's margin and clicks are at least 100; without margin data, report the break-even margin only and don't call it a loss. Compare with the median of other markets."

**Register for each area:**
- The question, how deep to break it down, which report.
- Judging rules: what counts as "a problem" or "worth doing", sample minimums, what to compare against.

**Rules:**
- Write them in the analysis log with a timestamp.
- Changed after seeing results: write what it was, what it is now, and why, and lower that finding's confidence one level (core rules 5.8: write it down before running code).

**Details for Claude:** every script prints its run time. The first run must come after the registration time.

---

## 3. Seven areas to cover

**One sentence:** write something for all seven areas. If one doesn't apply, write one line saying why.

1. **On-site ads:** campaigns, search terms, targeting, brand defense (module 2).
2. **Off-site ads:** each channel, landing pages, unseen flows (module 4). Unseen flows are sales your data can't see, such as orders won by another seller on your listing.
3. **What ads really brought:** side effects and spillovers between on-site and off-site, good and bad. The focus is what ads actually brought. This area doesn't judge whether ROAS is high or low.
   - For example: did off-site lift organic sales? Did on-site ads take clicks from your own organic listing?
   - Go through module 2's checklist item by item.
   - Reuse module 4's indirect numbers. Don't recalculate them.
4. **Business:** revenue, margin, stock and stockouts, price, Buy Box, other sellers on your listings.
5. **Markets:** differences between markets, seasonality, competitors, promotions.
6. **Patterns worth copying:** which market or product did something right, and can it be moved elsewhere?
7. **Outside research:** is there something only outside data can settle? Propose it; the user decides (module 1, step 6: the outside research rules).

---

## 4. Eight checks for every finding

**One sentence:** every finding answers eight questions before it goes into the key findings discussion.

**Example:** finding: "Japan's September revenue fell 15%, mainly from 12 stockout days." The eight checks:
- Can readers already see stockout days? No, so it can go in.
- Cause: during the stockout Sponsored Products stopped and organic rank fell; evidence level measured.
- Other explanation: seasonality? Same period last year didn't fall, so ruled out.
- Sample: the stockout is one event (12 days in a row), so fewer than 5 events; but the in-stock days used to estimate lost sales have over 300 Sessions (Business Reports, Sessions field), which meets the minimum. Enough.
- The rest follow the list below.

**Rules:**
- Write a small table per finding in the analysis log.
- In the chat, give only the conclusions.

**The eight checks:**
1. **Already visible?** If the readers' dashboards or weekly reports already show it, keep one line of background. The conclusion is only what they can't see.
2. **Cause:** one sentence on why it happens, with evidence level (measured, derived, external, assumption).
3. **Other explanation:** at least one alternative. Write why it's ruled out, or why it can't be yet.
4. **Sample and definition:** at least 5 events, 300 Sessions, or 100 clicks.
   - Below that, still give the most likely direction and mark confidence low.
   - Say which report and which field.
5. **How to repeat it:** who does it, when, which number to watch, what threshold, what to do when it's hit.
6. **Amount and comparison:** give the amount and what it's compared with.
   - Default comparison: the median of the same brand's other markets.
   - Using something else needs a reason.
7. **One-line rebuttal test:** if someone rebuts it in one line, e.g. "that's just the promotion", does it still stand? If not, lower confidence or rewrite.
8. **Contradictions:** does it conflict with known data, other parts of the report, or the user's earlier decisions? Sort that out before writing.

---

## 5. Break it down until someone can act

**One sentence:** every row must point to something a person can change.

**Example:** "Automatic campaigns in these two markets lose money" is too coarse. Write: "Japan automatic campaign A loses 12,000 a month and was started to find new search terms; US automatic campaign B loses 8,000 a month and was set up for a product launch."

**Rules:**
- Don't stop at category totals. Name which campaigns, how much each loses, and what each was for.
- Stop when every row names something a person can change (a campaign, a product, a setting).
- If the data only goes one level up, write "data goes to level X; breaking down further needs report Y" and add it to the data wish list.

---

## 6. Dig into anything unusually large

**One sentence:** when a number differs a lot, break it down until you can see what it's made of.

**Example:** unexplained went from 20,000 last period to 100,000. Breaking it down shows 80,000 sits in one product in one week, the week another seller took the Buy Box.

**Rules:**
- "Differs a lot" means compared with last period, other markets, or expectations.
- If you can't break it down, write how far you got and what data is missing.
- Never just report the number and move on.

---

## 7. Before recommending a stop or a cut

**One sentence:** first find out why it was started, then check it against the user's rules.

**Example:** a brand-term campaign has a high ACOS. Checking shows it's brand defense, because a competitor bids on your brand term. That can't go straight onto a stop list.

**Rules:**
- Find out why each campaign, keyword, or channel was started, e.g. brand defense, launch, clearance, agency strategy.
- If the purpose is unknown: write "purpose unknown, confirm with the owner first". Don't put it on a stop list.
- Unseen flows are not zero. Never call something inefficient because you can't see where its sales landed (core rules 5.4: a 0 needs evidence).
- Check every recommendation against the user's stated rules and limits.
- If one conflicts: write the conflict and what each choice leads to. The user decides.
- Don't change the rule yourself, and don't ignore it.

---

## 8. Key findings discussion, then stop

**One sentence:** before the final report, go through every finding with the user. Business first, ads second.

**Example:** the top finding might be "Japan was out of stock 12 days, about 300,000 in lost sales", and only second "Google brand-term credited ROAS 3.1".

**List all areas:**
- Business status (revenue, margin, vs normal)
- Products (which lines held up, which shrank)
- Stock
- Price and promotions
- Buy Box and other sellers
- On-site ads
- Off-site ads
- What ads really brought
- Markets and outside events
- Patterns worth copying
- Outside research

**Rules:**
- For each area, the good news and the bad news. If one kind is missing, write "none found this time". Don't force it.
- **Business first, ads second.** Order by effect on revenue or margin. The top five go first.
- Each finding has: the number (with scope), how we know, how sure, possible action.
- If the cause can't be separated, give the most likely direction (core rules section 8: conclusions never stop at "can't tell").
- Record the user's response to each finding: agree, add facts, disagree, dig more.
- Disagreement follows core rules section 10 (when something goes wrong: stop, locate the step, deliver one revised version).

---

## 9. The final report

**One sentence:** one report. Use the format the user asks for. If none, a document with the structure below.

### 9.1 Structure

- **Header:** what was analyzed, date, and "each section ends with how to answer follow-up questions; the full process is in the analysis log".
- **Scope (before section 1):**
  - Periods (past, and the next 13 weeks, written separately)
  - Markets
  - Which revenue is counted: only your own sales; other sellers on your listing and out-of-scope markets aren't
  - Currency and tax
  - Which on-site ad types, which off-site campaigns
  - Which weeks define "normal"
  - Margin definition
  - Where the chances come from
1. **Conclusion and actions:** one-sentence conclusion, current state, the problem, what to do (with margin data, module 5's action table), the three most important things.
2. **Business status:** vs normal, where the change came from, which product line moved most, how big ads are in the picture.
3. **Profit after ad cost by product** (without margin data: break-even margin instead, the margin needed not to lose money).
4. **Patterns worth copying**, with the most likely reason and how to verify it.
5. **Money that can be won back:** stockouts, Buy Box, ads that don't pay at any reasonable margin.
6. **Decisions to make**, with the decision tree.
7. **Action list, and how to check whether each one worked.**
8. **Numbers to watch each week**, only ones the reader can act on.
9. **The answer to the original question.**
10. **Off-site ads.** Leave out if module 4 wasn't used; write "off-site not assessed this time".
11. **Next 13 weeks:** scenarios and triggers, with the tree.
12. **Data wish list**, ordered by how many conclusions each item would firm up.
13. **Method and limits:**
    - How chances were calculated (including any score sheet)
    - Which checks were run
    - How sure each section is
    - **Errors that changed a conclusion** (before, after, why). Smaller fixes are in the analysis log.
14. **Terms.**
- **Appendix:** every data table (eight parts, off-site ROAS, products, ad types, stockouts, Buy Box, new products, prices, decision option ranges), each with scope and units.
- **Revision history.**

### 9.2 "If asked" at the end of every section

**One sentence:** think ahead about what readers will ask.

**Example:** "Q: Where does the 2.4 off-site ROAS come from? A: this is the credited ROAS. Off-site direct = Google clicks × bridge page pass-through × Business Reports conversion × order value, plus the off-site indirect allocated from leftover revenue. Ruled out: promotion weeks. Not ruled out yet: a competitor raised prices in the same period; most likely this pushes the return up a little."

**Each question has five parts:** the likely question, a one-sentence answer, how we know, what was ruled out, what wasn't (with the most likely direction).

Only questions readers would really ask. Don't pad the count.

### 9.3 Writing rules

Core rules section 12 (write so anyone can follow) applies in full. Also:
- **Benchmark:** a top consulting firm's analysis report. Conclusion first, one message per section, every number with source and scope, charts before tables.
- **Every heading is a conclusion.** E.g. "Japan sold 15% less in September, mainly from 12 stockout days", never "Japan September performance".
- **Every number states its scope:** every total, spend, revenue, share and ROAS. When a number's scope differs from the default in the Scope section, say how in the same sentence.
- **Bad news is stated plainly** (stockouts, lost sales, losses).
  - Neutral wording: subject + direction + number + compared with what.
  - No dramatic words ("plunged", "collapsed", "only").
  - Intensity words ("sharply", "most") only when the same sentence has a number.
- **If other teams or an agency will read it:** write problems as structure and channels, never as a team's fault. Suggestions read "suggest confirming with ...".
- **Only current conclusions in the body.** A replaced conclusion is removed from the body and kept only in the revision history and in "errors that changed a conclusion".
- **Every number in the report comes from script output.** A new number or a new recommendation first goes through a script and the self-check, then into the report.

### 9.4 Before handing it over

- **Scope check:** every number has its scope; compared numbers have the same scope.
- **Every inference (most likely direction):**
  - has supporting evidence in the report;
  - doesn't turn correlation into cause;
  - isn't stated more confidently than "medium";
  - matches the action list.
- **Structure check:** the assumptions list is at the top (run-to-end mode). Every "section N" reference points to a numbered heading. Every section in 9.1 is either present or has one line saying why it's left out.
- **No mixed ratios:** never divide two numbers of different kinds (e.g. lost sales ÷ ad spend) to make a striking comparison (core rules 5.9).
- **30-second test:** could someone who wasn't involved say the main point and next step within 30 seconds? If not, rewrite.
- **Hand over together:** the report and the analysis log go out together (core rules section 11: the downloadable analysis log).
