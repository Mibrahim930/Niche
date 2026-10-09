# Phase 1 Overview: Niche Selection (2026-10-09)

Inputs: [01 landscape scan (Sonnet)](01-landscape-scan.md), [02 local services deep dive (Opus A)](02-local-services-deep-dive.md), [03 professional/finance deep dive (Opus B)](03-professional-finance-deep-dive.md).

## Headline
Two independent Opus analysts, working in separate lanes, both landed on **construction specialty subcontractors / contractors**: Opus A from the bidding side, Opus B from the finance side. That convergence is the strongest signal in the research.

## What the evidence says
- **Back office beats front office.** Generic AI receptionists and chatbots are saturated. Jobber, Housecall Pro, Weave and ServiceTitan bundle them, VC-backed players like Avoca are in, and budget tools start at $29–49/mo.
- **Platforms are absorbing AI.** AppFolio shipped AI agents and a Claude connector (June 2026). Intuit is shipping QuickBooks agents. Basis raised $100M at a $1.15B valuation for accounting-firm AI (Feb 2026). Quandri and Exdion plug renewals into the insurance agency systems. Avoid niches whose core software vendor is already doing the job.
- **Small businesses adopt slowly.** The Census survey of US businesses (BTOS) shows only ~17–20% of businesses use AI, and firms with fewer than 20 employees haven't moved. That favors done-for-you implementation plus a tool, not self-serve SaaS.

## Disagreement resolved
The scout ranked accounting firms #1 and insurance agencies #2. Opus B argued both are crowded, and the verified funding and integration news supports Opus B. Accounting firms that serve construction remain valuable as a **sales channel**, not as the target market.

## Leading candidates
| Candidate | Offer | Why | Main risk |
|---|---|---|---|
| Construction subs/GCs: finance ops | Monthly WIP report and job-profit dashboard from QuickBooks, sub compliance and pay-app inbox, 13-week cash forecast | Bonding companies ask for WIP on a schedule; it's done in Excel; subs wait 51–96 days to be paid | Data quality from project managers; QuickBooks Desktop integration |
| Construction subs: preconstruction | AI Bid Desk: bid-invite triage, cited bid/no-bid briefs, hit-rate dashboard | 77% of open-shop firms struggle to hire estimators (AGC 2025); bid hit rates are ~9–14% | A missed spec item costs a job; the builder must learn spec structure |
| Wholesale distributors (QuickBooks-based) | Emailed PO → order-entry agent | Mid-market tools exist, small distributors underserved | Less pain evidence gathered so far |
| Dental (Open Dental) | Unscheduled-treatment recovery | Large dollar value per practice | HIPAA business-associate agreements, gated Dentrix integration, funded rivals |
| Home services (Jobber shops) | Quote follow-up, customer reactivation, marketing ROI dashboard | Owners are easy to reach | Overlaps Jobber's own features, GoHighLevel agencies |

## Corrections made during review
- Scout: removed 5 claims its cited pages didn't support, labeled vendor-sourced numbers, and filled in 5 niches it hadn't searched. Mortgage dropped from #4 to #9.
- AGC estimator stat reconciled from the PDFs: 77% national, 77% open-shop, 75% at $50–500M firms, 80% at ≤$50M firms. An earlier note implying 77% was open-shop-only was too narrow.
- Spot-verified: Basis valuation, AppFolio Claude connector, AGC survey, Billd/Siteline payment-delay figures.

## Known gap
Reddit and most practitioner forums were blocked for all agents, so **there are no first-hand owner quotes**. Pain must be validated in discovery calls before building.

## Trade-offs by niche
| | Construction: finance (WIP) | Construction: bidding | Wholesale distributors | Dental (Open Dental) | Home services (Jobber) |
|---|---|---|---|---|---|
| Buyer | Owner/controller, $2–30M GC or sub on QuickBooks | Chief estimator, $5–50M specialty sub | Owner/ops mgr, 20–200 orders/day on QuickBooks | Practice owner/office manager | Owner, 2–20 trucks |
| Offer | WIP + job-profit dashboard, sub-compliance inbox, 13-wk cash forecast | AI Bid Desk: bid-invite triage, cited bid/no-bid brief, hit-rate dashboard | Emailed PO → order-entry agent | Unscheduled-treatment recovery | Quote/reactivation follow-up + lead-to-cash dashboard |
| Price (est.) | $2.5–4k setup + $600–1,200/mo | $1.5k + $750–1,500/mo | $3–8k + $500–1,500/mo | $1k + $500–800/mo per location | $750–1.5k + $400–600/mo |
| MVP (est.) | 3–4 wks | 3–4 wks | 3–5 wks | 5–6 wks (incl. HIPAA work) | 3–4 wks |
| Biggest pro | Bonding companies require it monthly; done in Excel; best fit for finance skills | Reading long documents is a native AI task; no regulation; one extra win pays the year | Easy-to-measure ROI; small firms underserved | Highest willingness to pay | Easiest to reach; open Jobber API |
| Biggest con | Needs construction-accounting literacy; data quality from project managers; QB Desktop | Missed-spec liability; must learn spec format; Nomic/Scopebase/Autodesk nearby | Funded rivals moving down-market (Conexiom Relay, Endeavor, WizCommerce, Avent); least-validated pain | HIPAA business-associate agreements; gated Dentrix; Weave/NexHealth/RevenueWell | Overlaps Jobber's native features; GoHighLevel agencies; low prices |
| Regulation | Low (not CPA-signed statements) | Very low | Very low | High | Medium (texting rules) |

## Phase 2 update (construction, see 04)
- **Corrects phase 1:** "no product combines WIP, cash forecast and sub-compliance" is wrong. Adaptive (agentic construction accounting; $30M Series B Sept 2026, $57M total, 750+ contractors per its press release) covers AP, billing, WIP and compliance. Intuit's Aug 2026 release put WIP and over/under-billing reporting, AIA-style billing and change orders into QBO Advanced at no extra cost (confirmed in Intuit's release notes).
- **Implication:** WIP *software* is commoditizing. The defensible offer is the done-for-you monthly WIP close (collect PM forecasts, reconcile to the ledger, explain variances to the surety), not a WIP report tool.

## Phase 2 update (distributors, see 05)
- **Beachhead:** independent janitorial/sanitation, packaging and safety-supply distributors (~$3–40M) on QuickBooks Desktop Enterprise, QBO or Acumatica. Reachable through buying groups (AFFLINK 300+ distributors, Triple S 120+) and ISSA.
- **Avoid:** electrical/plumbing/HVAC distribution (Prokeep, Conexiom on Eclipse/P21/Infor) and foodservice (Pepper $50M Series C Feb 2026, Choco).
- **Flagship:** PO-to-Order Agent. Starts in shadow mode, then a rep approves each order, then auto-release once field accuracy passes 99%. Prices always come from the ERP.
- **Corrects phase 1:** QBO *does* have sales orders on Plus/Advanced (UI). API support is unverified, so sandbox-test it on day 1, with Estimates as the fallback.
- **Biggest threat:** Pepper already publishes janitorial-supply case studies and sells an Order Agent (no QuickBooks on its jan-san ERP list yet). WizCommerce and Intuit could also move down-market.

## Where we landed
| | Construction (04) | Distributors (05) |
|---|---|---|
| Flagship | Done-for-you **Monthly WIP & Surety Packet Desk** | **PO-to-Order Agent** |
| Entry offer | WIP Health Check, $750–1,500 | Order Desk & Cash Leak Audit with a backtest on the client's own orders, $750–1,500 (credited) |
| Core price (est.) | $2.5k setup + $1,200–1,800/mo | $3–6k setup + $750–1,500/mo |
| Value case | Bonding capacity protected and cash pulled forward (lumpy; hours saved alone ≈ $1.4k/mo) | ~$39k/yr illustrative (labor + errors), ~2.9× year-1 ROI; capacity to grow without hiring |
| Nature | Service-heavy (needs construction-accounting fluency) | Product-like (repeatable software + setup) |
| Main threat | Intuit QBO Advanced native WIP (Aug 2026); Adaptive ($57M raised) | Pepper (jan-san), WizCommerce, Intuit |
| Channel | Bond agents, construction CPAs | Buying groups (AFFLINK, Triple S), ISSA |

**Coordinator's read:** distributors is now the stronger *lead* track for an AI builder: the value is measurable, the product repeats across clients, and the buyers are concentrated in buying groups. Construction is a viable second track, but it is mostly an accounting-service business now that the WIP software is commoditizing. Both share one core to build once: email/PDF extraction with an accuracy test set, QuickBooks connectors (QBO + Conductor for Desktop), a human review queue with an audit log, chase agents and a cash dashboard.

**Before building:** run the discovery kits (§ in 04 and 05) with ~10 owners per niche. All prices and ROI are estimates, and no first-hand owner interviews exist yet.
