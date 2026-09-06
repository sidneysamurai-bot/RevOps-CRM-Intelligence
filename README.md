# Week 2 — CRM Pipeline Intelligence & Sales Forecasting

Week 1 built the CRM foundation: five linked tabs and a dashboard of live formulas. Week 2 asks a harder question — not *"can you build a spreadsheet,"* but *"can you tell a Sales VP what to do next."*

## Business problem

A 3-person sales team (Sidney, Ana, Carlos) is tracking toward a $100,000 monthly revenue target. Leadership needs five questions answered, in this order, because each depends on the one before it:

1. What is in our pipeline?
2. Where are deals getting stuck?
3. Which opportunities are most likely to close?
4. How much revenue can we realistically expect?
5. What should Sales do next?

## Solution

`RevOps_Pipeline.xlsx` extends the Week 1 workbook with:
- **Forecast Category** and **Cycle Risk Flag** columns on the Opportunities tab (live formulas, not manual tagging)
- A `Forecast_Reference` tab documenting exactly how those categories and flags are defined — the methodology is inspectable, not a black box
- An upgraded Dashboard: Revenue (Target/Actual/Forecast), Pipeline (Total/Weighted/Coverage), Sales Performance (Win Rate/Avg Deal Size/Sales Cycle), and Risk (At-Risk Deals/Revenue/Missing Data)

`Insights.md` is where the numbers turn into decisions — the data → insight → decision reasoning, and a Problem → Insight → Action → Owner → Deadline table.

`Dashboard.png` is a static snapshot of the executive dashboard for anyone browsing the repo without opening Excel.

## KPI snapshot

| Metric | Value | Target |
|---|---|---|
| Total Pipeline (open) | $373,000 | $300,000 |
| Weighted Pipeline | $211,850 | $100,000 |
| Closed Won | $52,000 | $100,000 |
| Forecast — Conservative (Won + Commit) | $199,500 | $100,000 |
| Forecast — Upside (+ Best Case) | $301,000 | — |
| Win Rate | 66.7% | 25% |
| Sales Cycle (avg, Won deals) | 6.5 days | — |
| At-Risk Deals (long-cycle proxy) | 9 deals / $72,500 | — |

## Headline insights

- Near-term revenue looks solid — 67% of open pipeline value is already in late-stage (Proposal/Negotiation) — but early-stage volume (48% of deal count, only 15.6% of weighted value) isn't replacing it fast enough for the following period.
- 7 of 9 long-cycle "at-risk" deals are Discovery-stage — the concentration and cycle-risk findings point at the same bottleneck from two different angles.
- The team's win-rate imbalance (Ana: 0%, Sidney/Carlos: 100%) is a bigger lever on target attainment than any pipeline-volume fix.
- True stalled-deal detection needs a `Last Stage Change Date` field the current CRM export doesn't have — flagged as a data-quality action, not glossed over.

Full reasoning in [`Insights.md`](./Insights.md).

## Next in the series

Week 3 moves from pipeline forecasting to **Lead & Customer Segmentation**, followed by **Sales Process Optimization** and a **RevOps Executive System** — building toward a portfolio aimed at international RevOps roles.
