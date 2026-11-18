# Amazon Analysis Kit for Claude

A set of rules that turns a Claude Project into a careful Amazon data analyst. You upload your own reports; Claude works out what your ads really brought, why revenue changed, and what to do next.

[繁體中文說明](README.zh-TW.md)

---

## The problem it solves

Amazon Attribution is supposed to tell you what your off-site ads (Google, Meta, TikTok, influencers) sold on Amazon. In practice it often undercounts, and many sellers can't use it at all.

This kit doesn't depend on it. Claude rebuilds the off-site effect from reports you already have: ad clicks, Business Reports, on-site ad reports. If you do have Amazon Attribution, Claude uses your own numbers to measure how much it undercounts.

It covers the rest of your Amazon data too: on-site ads, Buy Box, stock, new products, and the next 13 weeks.

---

## For practitioners: what's different

- **Revenue is split into eight parts that must add up to the cent.** Baseline, on-site direct and indirect, off-site direct and indirect, external events direct and indirect, unexplained. Nothing is left floating.
- **Off-site direct is rebuilt from clicks to orders,** never backed out of whatever revenue is left over. It can't be inflated to fill a gap.
- **Indirect effects need evidence:** timing and size (did organic orders rise after direct orders rose, and more so when they rose more), with comparison groups and a check for trends that started earlier.
- **No channel weights.** Every extra order counts the same. The "Google traffic counts 3× for ranking" type of claim has no traceable source, and the kit explains why.
- **Every number comes from code, with a most likely value, a 90% range and a label** (measured, derived, external, assumption, user decision). "Can't be calculated" is not an allowed answer.
- **A list of popular claims with no reliable source,** checked against papers, patents and official docs, so Claude never uses them to fill gaps.
- **No margin data, no "cut" or "scale up" advice.** Claude gives the break-even margin instead.

**Tested against a known answer, twice.** I made up reports with a planted Google effect: US$16.8k in sales, ROAS 2.3, about 0.48 extra Sessions per click, and no indirect effect.
- **First run:** the total was close (US$18.0k), but the split was wrong: about a third went to "indirect", and on-site ads got credit for sales planted as non-incremental. I changed the rules.
- **Second run, same data, new rules:** Google direct US$15.8k (90% range US$5.0k to 24.5k), ROAS 2.2, 0.48 extra Sessions per click, indirect 0. All within about 6% of the planted values.
- **Limits:** this is synthetic data, and it shares the kit's assumption that ad visitors convert like everyone else. Without a period when on-site ads were switched off and on, the kit can't tell how much on-site ads really add; it says so and gives a 0 to 100% range.

The files are written in plain language on purpose. The technical detail Claude needs sits in boxes marked "Details for Claude".

---

## What you get

A full analysis runs in four stops. Claude stops after each one and waits for you.

1. **Fact check:** Claude reads your reports, lists what it found (stockouts, Buy Box loss, promotions), and asks only what reports can't show.
2. **Plan:** what it will calculate, which methods, which periods it compares against.
3. **Results:** the main numbers with ranges, and what passed or failed the checks.
4. **Deep dive and report:** findings broken down to "who does what", good news and bad, then a final report.

At every stop Claude tells you what it did, what it decided for you, and what errors it fixed. At the end you get a downloadable analysis log, so every number can be traced and rebuilt.

---

## Quick start

1. Create a Claude Project.
2. Upload `01` to `09` from **one** language folder (`en/` or `zh-TW/`), plus `glossary.md`.
3. Paste the instructions block from `00-project-instructions.md` into the Project's instructions.

Then upload your reports and type:
`Start analysis: US, Sept 1–30, did Google ads add sales beyond what Amazon Attribution shows?`

Not sure which reports to pull? See `09-report-checklist.md`.

---

## What's in the box

| File | What it is |
|---|---|
| `00-project-instructions.md` | Setup steps and the block to paste into the Project |
| `01-core-rules.md` | Rules for every analysis |
| `02` to `06` | Modules: revenue change, on-site ads, Buy Box / stock / new products, off-site impact, next 13 weeks |
| `07-deep-dive-and-report.md` | Stop 4 and the final report |
| `08-external-evidence.md` | Outside numbers already checked, and claims with no reliable source |
| `09-report-checklist.md` | Which reports to pull, plus a safe way to let Claude set them up in your browser |
| `glossary.md` | Every term in English and Traditional Chinese |

English and Traditional Chinese versions say the same thing, section for section.

---

## Before you start

- **Amazon only.** Your own website, Walmart and retail stores are out of scope.
- **Code execution must be on.** Claude computes every number in code.
- **It uses a lot of your plan.** In testing, Stop 1 alone took a few minutes. Analyze one market and one question at a time.
- **You pull the reports yourself.** The kit tells you which ones. It never asks for passwords or logs in for you.
- **Why Claude:** in my own use, Claude handled this kind of strict, multi-step analysis better than other assistants. The rules are plain text, so you can try them elsewhere, but they were built and tested on Claude.
- **Estimates, not guarantees.** Every number comes with a range and a confidence label. Decisions are yours.

Not affiliated with Amazon or Anthropic.

---

## Author

Kevin Cheng (Cheng Kai Wen, 鄭凱文), Amazon performance marketer.
- X: [@kevin_amzdata](https://x.com/kevin_amzdata)
- Threads: [@kevin.amzdata](https://www.threads.com/@kevin.amzdata)

---

## License

[CC BY 4.0](LICENSE). Use it, change it, use it commercially. Just credit the source and say what you changed.
