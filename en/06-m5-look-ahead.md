# Module 5: What's most likely to happen next

> **Written for Claude to follow, and for people to understand.** Follow `01-core-rules.md`; terms are in `glossary.md`.
> **When to use:** after the main results (Stop 3). The user learns not only what happened, but what's most likely to happen next and what each choice leads to.
> **Attitude:** be willing to forecast. No forecast is perfectly right, but an honest range with clear triggers is more useful than silence. Forecasts never mix with measured numbers.
> **How to read:** each section opens with one sentence; most then give an example, followed by the rules. Boxes titled "Details for Claude" can be skipped by people. Claude must follow them.

---

## 1. What it produces

**One sentence:** a base line, a few possible scenarios, a decision tree, and, with margin data, an action table.

**Terms:**
- **Scenario:** one way things could go next, e.g. "a competitor took share for good".
- **Decision tree:** each of the user's options, under each scenario, and where the result lands.
- **If done, execution likelihood, expected gain:** see section 6.

**What to hand over:**
- A base line for the next 13 weeks, one number per week.
- 2 to 4 scenarios, plus "other". Each one is tied to an open question from the analysis.
- For each scenario: what must be true, when the effect ends, a weekly range, how likely it is, and which indicator tells you it's happening.
- A decision tree: the user's options × the scenarios → outcome ranges.
- With margin data, an action table: if done, execution likelihood, expected gain.

**Units first, revenue alongside.** When daily orders are few, one or two big orders make revenue jump. Units are steadier. Which one leads the report depends on the reader; ask if unsure.

---

## 2. Base line: what you'd sell over the next 13 weeks if nothing changes

**One sentence:** take the last 4 clean full weeks as the level, then shape it by last year's seasonal pattern for the same weeks.

**Example:** the last 4 clean full weeks averaged 500 units a week. Last year, week 3 ran at 1.2× normal. So this year's week 3 base line is 500 × 1.2 = 600 units.

**Rules:**
- **Level:** the last 4 clean full weeks. "Clean" follows core rules section 9, e.g. avoid big sales and their buffer weeks, stockouts or Buy Box problems, big ad changes, and known outside events. If the last 4 weeks aren't clean, step back to the nearest clean 4 weeks.
- **Shape:** last year's weekly seasonal index for the same 13 weeks.
- **No last-year data:** extend the level flat, labeled "no seasonal data".
- **Last year's same weeks had a big sale:** remove the promotion days the same way in both years.

**Details for Claude:**
- Default rule for removing promotion days: drop days with units above 1.8× the median of that stretch.
- List the dropped days and confirm at Stop 1 that they really were promotions.
- Label this 1.8× threshold "default, no basis".

---

## 3. Scenarios: the ways things could go next

**One sentence:** each scenario answers one open question from the analysis. Scenarios exclude each other, and "other" catches the rest.

**Example:** sales dropped and the cause is still unclear. Scenario A: "a cheaper competitor took share for good". Scenario B: "interest dipped after a big seasonal event and will come back slowly". Plus "other".

**Rules:**
- Each scenario = base line × one adjustment (traffic, conversion or price, pick one), or × a multiplier from a comparable past event.
- Past-event multipliers **only from the same brand and the same market**, e.g. last year's same promotion. Never borrow another market's or brand's multiplier.
- Write three things for each:
  - the premise: which explanation is true;
  - when the effect ends: an assumption, written down. Never decide mid-way that the effect has ended;
  - the weekly range for the next 13 weeks.
- A month-on-month marginal ROAS with a very wide range (e.g. 2 to 8) can only be the optimistic edge of another scenario, never a scenario of its own.
- **Likelihood:** high, medium or low, labeled "Claude's judgment, low confidence". No percentages. Never mark them all "medium". Commit to a view.
- **Indicator:** each needs one: which number, its current reading, the trigger, which report, when to look.
  - Trigger example: "brand search clicks down another 10% or more two weeks in a row → scenario A".
  - Triggers are settings for this analysis, labeled "default".

---

## 4. Where ranges come from: checking against the past

**One sentence:** pretend to stand on a past date, forecast with the same method, and compare with what actually happened. The size of the errors sets the range.

**Example:** standing on March 1 last year, the forecast for 4 weeks out was 500 units; actual was 460, an error of −8%. Do this from many starting dates, line up all the "4 weeks out" errors, take the middle 90%. That's the week-4 range.

**Rules:**
- Group errors by how far ahead the forecast was (week 1, week 2, and so on). The middle 90% of each group's errors is that week's range. This is a backtest.
- The backtest uses the same clean-period rules, or event weeks will blow up the errors.
- Too few starting points: label "widest range" and say how many there were.

---

## 5. Decision tree: each option under each scenario

**One sentence:** the user's options × the scenarios → outcome ranges, drawn as a tree.

**Example:** options are "keep off-site budget" and "cut it in half"; scenarios are A and B. Each of the four cells gets a range. With margin data, the reader sees at a glance: under A, cutting is better; under B, keeping is better. Without margin data, write only a condition, e.g. "keeping only beats cutting if your margin is above X%".

**Rules:**
- Example options: how much stock, keep or cut off-site budget, which product to push.
- At most 3 options × 3 scenarios. List the rest beside it.
- Options are business decisions. Propose candidates from the findings; the user confirms or edits at Stop 3. In "run to the end" mode, use yours, labeled "assumption".
- **Without margin data:** don't recommend between options. Write a condition: "B only beats A if your margin is above X%" (break-even margin). If the user says "just pick one", tell them there's no recommendation without margin data, and ask them to choose.
- **With margin data:** give each option's margin range under each scenario, and recommend one, with the chance and the method (section 6). The user (or whoever the report names as decision-maker) decides.
- Draw it as a tree in the report.

---

## 6. Action table (with margin data only)

**One sentence:** for each recommended action, write how much it gains if fully done and how likely it is to get done, and multiply the two to rank them.

**Three terms:**
- **If done:** margin gained over the next 13 weeks if the action is fully carried out.
- **Execution likelihood:** the chance it gets done fully, half, or not at all.
- **Expected gain:** if done × execution likelihood, averaged. Used only to rank which action goes first. Not a promise of what will be earned.

**Example (assumes inventory data is available):** "restock product B to 8 weeks of supply" gains 100,000 if done. It needs the warehouse team, so the default is done 60%, half done 30%, not done 10%. Expected gain = 100,000 × 60% + 50,000 × 30% + 0 × 10% = 60,000 + 15,000 + 0 = 75,000. (This tier needs another team; half done is assumed to give half the effect here; in the simulation, how much "half done" achieves is drawn between 30% and 70%. See details.)

**For every action write:**
- what to do, who does it (or who decides);
- if done: most likely value, middle 90% range, chance of gaining anything;
- execution likelihood;
- expected gain;
- how you calculated it, in plain words.

**How "if done" is calculated, six steps:**
1. **Start:** the last 4 clean full weeks. Every uncertain piece gets a range, with a written reason and source label. List every range used in the analysis log. Tables in the report come straight from script output, never typed by hand.
2. **Seasonality:** multiply each forward week by last year's weekly index. Use the same promotion-day rule for both years. Only one year of data: label "derived, low". No last-year data: no seasonality, say so, and add it to the data request list.
3. **Product line vs whole store:** both sides use the same base definition (see details).
4. **Timing:** include restock lead time, the time for Buy Box and ads to ramp back up, and test periods. Effects start the week the action starts. Effects can be negative: a discount that didn't buy volume, extra ad spend that didn't pay back, lost sales during a test.
5. **Comparison:** always state what happens if nothing is done. If an action is already partly done, count only the remaining part; describe the finished part as the current state.
6. **Actions that can't become an amount:** e.g. "stock to current weekly demand" needs inventory data. Give no amount and no expected gain. Write what data would make it calculable.

**The user decides execution likelihood.** It's a business judgment. Propose defaults and, before the report, list them as one question per action:
- needs another team or partner: done 60%, half done 30%, not done 10%;
- the user controls it: done 90%, half done 10%.
- If the user answers, label "user decision". If they say "don't know" or "use your default", label "user decision, low confidence".
- Label all defaults "default, no basis".

**Simulate all actions together. Never calculate each one and add them.**
- Totals come from the joint simulation, never by adding ranges.
- If two actions would count the same sales, say which one gets them.

**Chance of gain:** the share of simulation runs where the result beats doing nothing.
- State the premises held fixed in the simulation. The chance holds only if they hold.
- If the threshold falls outside the simulated range, write "above 95%" or "below 5%", never a fake-precise number.

**Actions with no amount that still need a confidence level: use the score sheet.** The score sheet scores four aspects and converts the total into a rough likelihood. Print it in the report's method section, with a reason for every score. The score sheet never multiplies any amount.

**Never give a chance by gut feeling.**

**When the method changes:** add a step-by-step table. Start from the old method, change one step at a time, and show how much the total moves and in which direction at each step. When the user feels a number is "too high" or "too low", first check which number they're comparing (past or future, revenue or margin, if done or expected gain) before deciding whether to change the method.

**Details for Claude (section 6):**
- Seasonal index draws between two definitions: units without your own promotion volume (lower) and visitors (upper).
- When product line and whole store can't share a definition (e.g. only a 13-week total for child products), draw between the ratio and "no adjustment (1.0)", labeled "derived, low". Markets where last year isn't usable (store changed, too few sales): use other markets' average as a stand-in, draw between "no adjustment" and the stand-in, labeled "external, low".
- For "half done 30%", the share actually achieved is drawn between 30% and 70%.
- Shared draws: all actions share one margin draw; actions in the same market share one seasonality draw; actions done by the same people share one execution draw.
- 20,000 runs, fixed random seed (so every rerun gives the same result). Rerun with 3 seeds; totals must differ by less than 1% of the range width.
- In the step-by-step table, every step uses the same random numbers.
- Score sheet:
  - Evidence: measured 3, derived 2, inferred 1.
  - Mechanism: clear 2, partly clear 1, unclear 0.
  - Control: we control it 2, needs others 1, out of our control 0.
  - Interference: little 2, some 1, a lot 0.
  - Total 8–9 ≈ 85%, 6–7 ≈ 70%, 4–5 ≈ 50%, 3 or less ≈ 30%. Label "default, no basis".

---

## 7. Labels and red lines

**One sentence:** a forecast is a forecast. Never mix it with measured numbers, and never treat it as a recommendation.

**Rules:**
- Forecasts are always labeled "derived" or "assumption". Confidence at most medium (depending on the backtest).
- Forecasts never enter the eight parts of revenue.
- Never write a forecast and a measured number in the same sentence.
- Scenario likelihoods are low confidence. Never in the same sentence as measured numbers.
- A forecast is not a recommendation. Recommendations need margin data (core rules section 7: no margin data, no recommendation to scale up, cut budget, or stop).
- Unseen flows (e.g. orders taken by another seller) stay unseen here too. Never forecast "no loss" for sales you can't see.

---

## 8. Forecasts to check next time

**One sentence:** record every forecast. Next time the same market is analyzed, check the answers first.

**Why it goes in the analysis log:** the user's project can't store a running ledger for you. So the analysis log gets a section "Forecasts to check next time", one row per forecast:

| Date made | What | Range | Method | Scenarios, indicators, triggers | Actions: execution assumed, expected gain, check at weeks 4 / 8 / 13, which report |
|---|---|---|---|---|---|

**How to check next time:** when the user uploads a previous analysis log for the same market, check at Stop 1:
- did the actual land inside the range;
- which scenario played out;
- was each action done, and how much;
- did the "if done" effect land in its range.
Record "done or not, how much" separately from "did the effect land in its range".

**After checking:** use the results only to calibrate range widths and execution defaults (ranges that keep missing get wider). Never turn them into a fixed factor.
