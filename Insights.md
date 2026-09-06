# Insights — CRM Pipeline Intelligence & Sales Forecasting

Data → metric → insight → decision. This is the actual RevOps reasoning behind the numbers in `RevOps_Pipeline.xlsx`, not just the formulas.

## How to think about the forecast (not just the formula)

Two different forecasting methods are used side by side, because they answer different questions:

- **Weighted Pipeline** (`Deal Value × Probability`, summed) — a single blended number. Fast sanity check, but it hides *which* deals are actually driving the number.
- **Forecast Categories** (`Commit` / `Best Case` / `Pipeline`, full deal value) — the method most sales orgs report to leadership, because it separates *"will close"* from *"could close"* instead of blending them into one probability-weighted blur.

Reading the two together: Weighted Pipeline ($211,850) and the Conservative forecast, Closed Won + Commit ($199,500), land close to each other — a healthy sign the weighting roughly agrees with the category-based read. The gap to the Upside forecast (+ Best Case, $301,000) is the real range a RevOps lead should quote: **"somewhere between $199K and $301K, depending on how many Proposal-stage deals convert."**

## Pipeline concentration — a more precise (and more useful) story than "40% is late-stage"

- **67% of open pipeline value** ($249,000 of $373,000) sits in the two late stages, Proposal + Negotiation. That's good news for the current forecast — near-term revenue is well supported.
- But by **deal count**, early-stage (Discovery + Qualified) is actually the larger group: 15 of 31 open deals (48%), worth $124,000 — only **15.6% of weighted pipeline**, because low-stage probability discounts it heavily.
- Read together: **the current quarter looks fine; the next one is the risk.** Late-stage deals are carrying today's forecast, but there isn't yet a strong bench of early-stage deals maturing behind them at the same rate. Discovery/Qualified volume needs to keep pace, or Q3's pipeline will look like today's Q2 gap did.

## Cycle-length risk — and an honest data gap

- Closed-Won deals in this dataset closed in **6.5 days on average**. That's a useful *retrospective* benchmark, but it can't be directly compared to open deals' *planned* cycle length (21.3 days on average) — those are two different things measured two different ways, not evidence that the sales cycle is getting worse.
- The more honest signal: within the **current open pipeline itself**, 9 deals (**$72,500**) sit in the top quartile of planned cycle length (≥25 days). **7 of those 9 are Discovery-stage** — every single Discovery deal in the pipeline is a long-cycle deal. That reinforces the concentration finding above from a different angle.
- **The real gap:** none of this is a substitute for actual stalled-deal detection, which requires a `Last Stage Change Date` field this CRM export doesn't have. Flagging that gap is itself a RevOps deliverable — see Action 3 below.

## Team read

- Carlos carries the largest pipeline ($148,500) and weighted pipeline ($87,750).
- Sidney and Carlos both show a 100% win rate on this dataset.
- **Ana has $0 in closed-won revenue, and owns all 3 of the dataset's lost deals.** That's not a footnote — it's the single most actionable line in the whole analysis, and it's the first thing Action 1 below addresses.

## Actions — Problem → Insight → Action → Owner → Deadline

| # | Problem | Insight | Action | Owner | Deadline |
|---|---|---|---|---|---|
| 1 | Ana: $0 closed-won, owns 100% of lost deals | Conversion gap at the negotiation/close step, not at lead generation — her pipeline volume is comparable to Sidney's | Pipeline review + call shadowing on Ana's active Proposal/Negotiation deals this week | Sales Manager (Sidney) | 5 business days |
| 2 | 48% of open deals (by count) sit in Discovery/Qualified, contributing only 15.6% of weighted pipeline | Early-funnel bottleneck — volume isn't converting into probability-weighted value fast enough to replace what's closing this quarter | Set a stage-aging check-in at 14 days in Discovery/Qualified; review the 7 flagged Discovery deals specifically | RevOps (Sidney) | This week |
| 3 | No `Last Stage Change Date` field — can't measure true stalled-deal risk, only a cycle-length proxy | Missing data is itself a pipeline risk; today's "At Risk" flag is a proxy, not ground truth | Add a `Last Stage Change Date` field to the CRM schema before Week 3 | RevOps (Sidney) | Before next build |
| 4 | Closed Won ($52,000) is only 52% of the $100K monthly target | Commit-stage deals ($147,500 across 8 deals) are large enough to close the gap on their own if they land on schedule | Prioritize follow-up on the 8 Negotiation-stage deals this period; treat them as the primary lever for hitting target, not new pipeline generation | Deal owners (Sidney, Ana, Carlos — per deal) | End of period |
