# 04 — Construction Contractors: Offers That Bring Real Value

Analyst: Opus A · Date: 2026-10-09
Niche: specialty subcontractors and small GCs, roughly $2–50M revenue.
Covers two angles: preconstruction (the bid desk) and finance/back-office (WIP, pay apps, waivers, cash).
Builds on `02-local-services-deep-dive.md` §5 and `03-professional-finance-deep-dive.md` §2.

---

## 0. Read this first: what changed, and evidence rules

**Two findings change both earlier recommendations.**

1. **WIP reporting is being commoditized by the ledger vendors.**
   - Intuit added WIP, over/under billing, cost-to-complete reporting and AIA-style progress billing to Intuit Enterprise Suite (IES) in May 2026. The source is Knowify's competitor review, checked Aug 1, 2026 ([Knowify](https://knowify.com/resources/intuit-enterprise-suite-review/)).
   - An Aug 7, 2026 headline says "QBO-Advanced now includes construction financial capabilities" ([Insightful Accountant](https://blog.insightfulaccountant.com/qbo-advanced-now-includes-construction-financial-capabilities); full text is behind a registration wall). Simpro's Oct 2026 article describes WIP, phase budgets, AIA-style billing and change orders arriving in QBO Advanced at no extra cost ([Simpro](https://www.simprogroup.com/blog/quickbooks-job-costing-contractors), seen via search excerpt; a direct fetch returned 403).
   - JobTread has shipped a WIP report since 2023 ([JobTread](https://www.jobtread.com/product-updates/2023-10-10-dynamic-work-in-progress-wip-report)), and Buildertrend has one too ([Buildertrend](https://buildertrend.com/help-article/work-in-progress-report-faqs/)).
   - **Adaptive** (adaptive.build) sells AI agents for AP coding, billing, WIP and compliance. It raised a $30M Series B in Sept 2026, bringing its total to $57M ([Construction Dive](https://www.constructiondive.com/press-release/20260917-adaptive-raises-30-million-series-b-led-by-tidemark-to-bring-agentic-accou/)), and claims 700+ contractors and a white-label version for CPA firms ([CPA Practice Advisor](https://www.cpapracticeadvisor.com/2025/05/05/adaptive-launches-industry-specific-ai-to-help-accounting-firms-scale-construction-services-without-adding-headcount/159635/)).
   - **This contradicts the earlier claim in 03 §2.3** that no product combines these pieces at small-contractor prices. A plain "WIP dashboard on QuickBooks" SaaS is no longer a gap.

2. **Bid triage for subs is cheap and getting cheaper.**
   - Downtobid lists sub plans at $119/mo (basic bid board) and $299/mo (full bid management) ([G2 listing](https://ai.g2.com/marketplace/tools/downtobid); undated).
   - Autodesk's "Bid Forwarding" already pulls key details from invitations received outside BuildingConnected into Bid Board Pro ([Autodesk](https://construction.autodesk.com/products/buildingconnected/)).
   - My phase-1 "AI Bid Desk" as a $750–1,500/mo product is weaker than I claimed.

**What is still not commoditized** is the human-dependent monthly process around the numbers:
- getting PMs to give honest cost-to-complete forecasts;
- reconciling to the ledger;
- explaining underbillings and fade to a surety;
- chasing waivers across each GC's own forms;
- getting pay apps right the first time.

CPA firms and a surety say that is where WIP goes wrong (§3). **That is where a solo builder's AI-plus-service offer still has room.**

**Evidence rules used throughout:**
- `[indep]` = independent: government, trade association, surety, CPA firm, or job postings.
- `[vendor]` = published by a company selling the fix.
- `(estimate)` = my own number.
- Reddit, ContractorTalk and several review sites were unreachable (blocked, 403, or behind paywalls). No quotes were invented. Where no data exists, I say so.

**AGC precision note (reconciled by coordinator).** The coordinator extracted the open-shop and $50–500M breakouts: estimating personnel is **77% (459 firms)** open-shop and **75% (284 firms)** at $50–500M. Combined with the national and ≤$50M sheets below, all four readings are consistent, and the target segment (≤$50M) is the highest at 80%.
- **National:** Estimating personnel shows **77% (879 firms with openings)**, Accounting personnel **40% (871 firms)** ([AGC national PDF](https://www.agc.org/sites/default/files/users/user21902/2025_Workforce_Survey_National_FINAL_m.pdf)).
- **≤$50M firms:** Estimating shows **80% (393 firms)**, Accounting **49% (393 firms)** ([AGC ≤$50M PDF](https://www.agc.org/sites/default/files/users/user21902/2025_Workforce_Survey_Under50M_V3.pdf)).
- Please reconcile these against the coordinator's breakout figures before quoting a single number externally.

---

## 1. Buyer map

### Who touches the pain

| Role | Feels pain | Decides | Pays | What they care about |
|---|---|---|---|---|
| **Owner / president** | Cash squeeze, bonding limits, fade surprises | **Yes** (under ~$30M, nearly always) | **Yes** | Bonding capacity, cash, "where am I losing money" |
| **Controller / office manager / bookkeeper** | Month-end WIP, pay apps, waivers, AP coding | Influences; can veto (fears replacement or extra work) | No | Fewer late nights, fewer surety questions, not looking bad |
| **Chief estimator / estimator** | Bid volume, spec reading, scope gaps | Decides on bid tools under ~$300/mo | Sometimes (small tools) | Fewer wasted bids, missed exclusions, deadlines |
| **PM / project executive** | Asked for cost-to-complete, pay-app % complete, CO paperwork | No; must comply | No | Least friction; hates forms |
| **Surety bond agent / producer** | Bad WIPs slow underwriting and limit their client's program | No | No, but **the best referral channel** | Clean WIP, timely quarterly/monthly reporting ([Grit](https://gritinsurance.com/bonds-surety/increase-bonding-capacity/work-in-progress-reporting/)) |
| **Outside construction CPA** | Year-end review/audit is slow when monthly WIP is bad | Influences heavily | No; may white-label | Faster year-end, clean contract asset/liability tie-out ([BerryDunn](https://www.berrydunn.com/news-detail/construction-wip-accounting-five-common-mistakes)) |
| **Bank (line of credit)** | Borrowing-base and covenant reporting | No | No | Monthly/quarterly WIP and AR aging |

### Segments

| Segment | Typical stack | Top pain | Who buys | Fit for a solo builder |
|---|---|---|---|---|
| **S1. Bonded specialty subs and small GCs, $5–30M**, bookkeeper plus outside CPA, no full-time controller | QBO Plus/Advanced or QB Desktop Contractor, Excel WIP, maybe Procore (GC) or none | WIP for surety/bank, underbillings, pay apps, cash | Owner (often pointed there by the bond agent or CPA) | **Best: target first** |
| **S2. Unbonded subs, $2–10M**, private work | QBO + Excel; owner estimates | Cash (pay apps, retainage), slow pay | Owner | Real pain, low budget; better served by a $49–300 tool |
| **S3. $30–50M+ with a controller** | Foundation, Sage 100 Contractor, Viewpoint, Procore | PM forecast discipline, AP volume, compliance | Controller/CFO | Has an ERP WIP already; asks for SOC 2; Adaptive and ERPs compete. Later. |
| **S4. Small GCs, $5–30M** | QBO + Procore/Buildertrend | Sub compliance (waivers, COIs) gating payments | Owner/controller | Procore Pay covers Procore GCs ([Procore release notes](https://support.procore.com/products/online/user-guide/company-level/payments/release-notes)); niche for non-Procore GCs |
| **S5. Commercial subs with 1–5 estimators** (overlaps S1/S3) | BuildingConnected, Bid Board Pro, email, PlanHub | Bid volume, spec review | Chief estimator / owner | Feasible, but anchored to $119–420/mo tools |

### Why S1 first
- **Forcing function.** Sureties expect WIP at least quarterly; one broker suggests monthly financials plus WIP within ~20 days of month-end for active programs ([Grit](https://gritinsurance.com/blog/what-surety-underwriters-want-2026)).
- **No in-house controller,** so the work falls on a bookkeeper and the owner.
- **Two trusted intermediaries** (bond agent, CPA) whose incentives align with yours.
- Many are on **QBO Plus or Desktop**, which have no native WIP. The Aug-2026 WIP features are reported for QBO Advanced and IES. Advanced is now about $340/mo per a Sept-2026 reseller page ([Fourlane](https://www.fourlane.com/quickbooks-online-pricing-changes-2026-new-rates-and-fourlane-discounts/)).
- Even on Advanced, someone still has to collect cost-to-complete and explain the numbers.
- **Firm counts by size band: no data.** The Census CBP API needs a key; I did not obtain size-band counts. The pool is large regardless: ~598k specialty-trade establishments per 03 §2.1, citing [BLS NAICS 238](https://www.bls.gov/iag/tgs/iag238.htm).

---

## 2. Workflow maps: where hours and dollars leak

### 2A. Bid cycle (specialty sub)

```
ITB arrives (email / BuildingConnected / PlanHub; duplicates from several GCs)
 → log it (spreadsheet or Bid Board)                         [leak: duplicates, missed deadlines]
 → download plans/specs/addenda                              [leak: hours; wrong addendum]
 → read the trade's spec divisions + front-end (bonding, LDs, insurance, schedule, prevailing wage)
 → bid / no-bid decision (often gut feel)                    [leak: estimator time on unwinnable bids]
 → takeoff (PlanSwift/Accubid/manual)
 → supplier quotes, labor pricing, markup
 → proposal with inclusions/exclusions/alternates           [leak: scope gaps → later margin fade]
 → submit (often to several GCs on the same job)
 → follow-up; award or loss (loss reasons rarely captured)   [leak: no learning loop]
 → handoff to PM (budget = estimate)                         [leak: estimate not structured for job cost]
```

| Quantification | Value | Quality |
|---|---|---|
| Public-work hit rate | ~7–11 bids per award, i.e. ~9–14% ([Bridgit citing ENR](https://gobridgit.com/blog/how-to-bid-as-a-subcontractor/)) | `[indep]`, secondhand |
| Firms tracking their hit ratio | 6% of ~2,000 surveyed ([ENR](https://www.enr.com/articles/23952-bid-hit-ratios-provide-valuable-road-map?v=preview); undated) | `[indep]`, possibly old |
| Estimator time on document review | ~38% "according to ASPE" ([Provision blog](https://provision.com/blog/how-to-review-construction-documents-preconstruction)) | `[vendor]`; original ASPE source not found |
| Hours per bid on spec cross-referencing | 15–25 hrs per bid set ([Provision](https://provision.com/blog/how-to-review-construction-documents-preconstruction)) | `[vendor]` |
| Estimator scarcity and cost | AGC 2025: 77% national / 80% ≤$50M find estimators hard to hire (see §0); BLS median $79,130 for estimators in specialty trades (May 2024) ([BLS](https://www.bls.gov/ooh/business-and-financial/cost-estimators.htm)) | `[indep]` |
| Hours spent triaging ITBs | **No data found** | — |

Job postings confirm the manual admin layer:
- Bid coordinators process and distribute plans, specs and addenda and check bidders' licensing ([Ultimate Staffing](https://careers.ultimatestaffing.com/job\66633\Bid-Coordinator-Estimating-Assistant)). Another listing (Pre Con Industries, seen in a search excerpt; URL not captured) has the coordinator phoning subs to confirm receipt of invitations and tracking responses in Excel.
- Assistant estimators "receive, organise and prepare" bid documents in BuildingConnected ([FactoryFix NJ](https://jobs.factoryfix.com/jobs/assistant-estimator--new-jersey--nj--1725951699--V2)).
- Assistant estimators send addenda and route sub RFIs to estimators ([Suffolk via WeAreDevelopers](https://www.wearedevelopers.com/jobs/ext/6956724/assistant-estimator-data-centers)).
- Most of these are **GC-side** roles, so the sub-side triage burden is less well evidenced.

### 2B. Month-end, pay-app and WIP cycle

```
Daily/weekly: AP bills + receipts → coded to job/cost code         [leak: miscoded or uncoded costs]
Weekly: payroll → job cost (labor burden often missing)
~20th–25th: pay app per job (SOV, % complete by line, stored materials, CO lines,
            retainage, GC-specific waiver packet incl. lower-tier supplier waivers)
                                                                    [leak: errors → rejection → +30 days]
Month-end close (bookkeeper)
 → PMs asked for cost-to-complete / % complete per job             [leak: stale or optimistic forecasts]
 → WIP calc (cost-to-cost): earned revenue, over/under billing, fade vs. last month and vs. bid
 → reconcile WIP to GL (contract assets/liabilities, retainage)     [leak: not reconciled]
 → WIP review meeting (owner + PMs)
 → surety/bank packet (WIP + interim financials), within ~20 days of month-end
Year-end: CPA compilation/review/audit relies on the WIP            [leak: late adjustments, fees]
Throughout: retainage receivable aging; lien notice deadlines; collections
```

| Quantification | Value | Quality |
|---|---|---|
| Sub pay-app burden | 67% of subs spend 11+ hrs/month preparing, submitting and tracking pay apps (Siteline 2026, n=492, May 2026) ([Siteline](https://www.siteline.com/blog/92-percent-of-subcontractors-floated-payroll-last-year-new-siteline-report-finds)) | `[vendor]` |
| Payroll float | 92% of subs floated payroll in the past year; 28% in most months (same) | `[vendor]` |
| Retainage | 43% of subs wait 90+ days for final payment/retainage (same) | `[vendor]` |
| Lien deadlines | 56% of subs missed a critical mechanic's lien deadline in 2 years (same) | `[vendor]` |
| Biggest internal cause of late pay (subs) | Pay apps with errors or omissions (same) | `[vendor]` |
| GC payment admin | 65 hrs/month (Rabbet 2025, n=125) ([Rabbet](https://rabbet.com/reports/construction-payments-2025)); 73 hrs/month (Siteline 2025) ([Siteline](https://www.siteline.com/blog/siteline-report-reveals-deepening-crisis-in-construction-payments-and-offers-a-blueprint-for-faster-cash-flow)) | `[vendor]` |
| Days to get paid | 51–96 days depending on source (03 §2.2; [Billd](https://billd.com/resources/2025-market-report), Siteline) | `[vendor]` |
| Hours to produce a monthly WIP | **No data found.** One 2011 CFMA forum post says WIP review meetings take about 30 minutes per project ([CFMA forum archive](https://chapters.cfma.org/forum_old/thread_monthlywipmeet.html)) | `[indep]`, anecdote, old |
| Why WIP goes wrong | Bad inputs (projected cost, contract value, cost to date, billings), unrecorded change orders, no tie-out to financials, incomplete contract lists ([BerryDunn, Apr 2025](https://www.berrydunn.com/news-detail/construction-wip-accounting-five-common-mistakes)); stale estimates, unapproved COs, inconsistent methods ([Dean Dorton](https://deandorton.com/articles/common-wip-schedule-mistakes/)) | `[indep]` CPA firms |
| Cost of a bad WIP (surety view) | Old Republic Surety found underbillings had inflated one contractor's working capital by nearly $3M; late-stage underbillings that keep growing on losing jobs get disallowed ([NASBP Pipeline, Jun 2025](https://www.nasbp.org/pipeline-newsletter/a-suretys-perspective-of-underbilling-and-its-impact-on-contractor-financials/)) | `[indep]` surety |
| Capacity math | Aggregate bonding commonly ~10–20× working capital ([Pease Bell](https://www.peasebell.com/?p=2809)). Every $100k of disallowed working capital is roughly $1–2M of aggregate capacity (my arithmetic on that rule of thumb) | `[indep]` CPA rule of thumb |

**Owner and staff voice I could retrieve (all short, attributed):**
- A Sage strategist on CFMA's forum: WIP is mostly done with "paper, Excel or PDF" ([CFMA Café, 2022](https://cafe.cfma.org/discussion/machine-readable-wip-reports-1), via 03).
- A sub's CFO on CFMA Connection Café, quoted by Levelset: every GC has its own waiver form and requirements, and the monthly waiver chase across vendors is a major headache. Paraphrased; the short original is "special snowflake requirements" ([Levelset](https://www.levelset.com/blog/tracking-lien-waivers/)).
- QuickBooks Community, 2021–2026: users ask for a WIP workaround in QBO; replies point to spreadsheets and third-party apps ([QB Community](https://quickbooks.intuit.com/community/reports-and-accounting-5/wip-work-in-progress-reporting-solution-for-qbo-35652)).
- Job postings: construction staff accountants are hired to prepare WIP and percentage-of-completion schedules, track over/under billings and retainage, process sub pay apps and lien waivers, and keep COIs on file ([iHireAccounting](https://www.ihireaccounting.com/jobs/view/521982671), [Robert Half via HireHeroes](https://jobs.hireheroesusa.org/jobs/581520874-construction-accountant-at-robert-half), [Institute Data](https://jobs.institutedata.com/job/4867011/construction-accountant/), [Smarter HR](https://jobs.auditfriendly.co/jobs/staff-accountant-construction-smarter-hr-solutions-f92a8498a3ad)). Firms are paying a salaried person for this. The BLS median for bookkeeping/accounting clerks is $49,210 (May 2024) ([BLS](https://www.bls.gov/ooh/office-and-administrative-support/bookkeeping-accounting-and-auditing-clerks.htm)).

---

## 3. Pain validation: independent vs vendor

| Pain | Independent evidence | Vendor-only evidence | Verdict |
|---|---|---|---|
| WIP quality limits bonding | Surety (Old Republic via NASBP), CPA firms (BerryDunn, Dean Dorton, HBK, Baker Tilly, CBIZ), broker (Grit), job postings | LiveFlow, Adaptive, Intuit marketing | **Strong** |
| PM cost-to-complete is the weak input | CPA firms ("input" errors, stale estimates); JLC: accounting can't produce a useful WIP unless production owns cost-to-complete ([JLC](https://www.jlconline.com/business/money/cost-to-complete-an-essential-monthly-metric/)) | — | **Strong**. This is the real bottleneck. |
| Pay-app and waiver admin is heavy | Job postings; CFMA Café quote via Levelset | Siteline (11+ hrs), Rabbet (65 hrs GC), Billd | **Medium-strong** (direction clear, magnitudes vendor-sourced) |
| Slow pay / cash float | — (no independent survey found) | Siteline, Billd, Rabbet all agree on direction | **Medium** |
| Estimators scarce | AGC 2025 (primary), BLS wages | — | **Strong** |
| Estimators waste time on ITB triage and spec reading | Job postings (GC side) | Provision 38%/15–25 hrs, Downtobid inbox claims | **Weak–medium for subs** |
| Hit rates low and untracked | ENR (old), Bridgit-citing-ENR | Autodesk blog | **Medium** |

Podcast evidence: a construction CPA and a bond agent discuss contractors paying tax on "invisible" WIP profit while the surety cuts their line ([Contractor Success Forum](https://contractorsuccessforum.buzzsprout.com/1748499/episodes/18693023-from-confusion-to-clarity-unlocking-the-power-of-wip-reports), via 03). I did not find YouTube transcripts with quantification.

---

## 4. Offer ladder

### Design principle
Sell a **monthly outcome** ("your WIP and surety packet, reconciled and explained, by day 15"). The AI does extraction, chasing, drafting and anomaly-flagging. A human (the builder, then the client's bookkeeper and owner) approves every number. This works on any ledger, and it survives Intuit shipping a WIP report, because the report was never the hard part.

### Entry offers (paid, low-risk)

**E1. WIP and Underbilling Health Check: $750 (≤15 active jobs) / $1,500 (16–40). Delivered in 5 business days.**
- **Inputs:**
  - Read-only QBO access, or a Desktop export (job profitability, AR aging, A/P by job), or Conductor.
  - Job list: contract value, approved and pending COs, original estimated cost, retainage %.
  - PM cost-to-complete for each open job (one short form).
  - Last CPA year-end WIP.
  - The bank/surety reporting requirements.
- **Outputs:**
  - Rebuilt WIP at last month-end (Excel, surety-style layout).
  - Fade analysis on jobs closed in the last 24–36 months. Brokers say >1–2 points of aggregate fade invites deep questions ([Grit](https://gritinsurance.com/blog/what-surety-underwriters-want-2026)).
  - Underbilling aging with "late-stage underbilling" flags (the surety lens).
  - Retainage receivable aging.
  - A 13-week cash snapshot.
  - A 2-page findings memo with the top 5 issues.
- **AI vs human:** AI flags miscoded costs, odd margins, CTC inconsistencies, and drafts the memo. A human verifies every figure. The memo says plainly that this is "management information prepared from your records; not a compilation, review or audit."
- **Why it works:** it proves value with the client's own numbers. Fintruction already uses a free 48-hour audit as its hook (03 §8). **Charge for it,** to filter for seriousness.

**E2. Bid Hit-Rate Audit: $500 (bid side).** Reconstructs 12 months of bid log from the estimating inbox (ITBs, submissions, award/loss emails). Outputs hit rate by GC, project type and size, estimated hours spent on lost bids, and a GC scorecard. AI parses the emails; a human checks the log.

### Core offers

**C1. Monthly WIP and Surety Packet Desk (FLAGSHIP)**
- **Inputs:**
  - QBO via API, or QB Desktop via Conductor or monthly exports.
  - Job master in a shared sheet or simple app: contract, approved/pending COs, budget by cost group, retainage %.
  - PM forecasts collected by an AI "forecast agent." It sends each PM a 3-question email/SMS per job: CTC or % complete by phase, pending CO $, top risk. It accepts free-text replies ("framing 80% done, need another $40k lumber"), parses them into structured deltas, and asks follow-ups when numbers conflict (e.g., CTC drops with no new cost).
  - Prior WIP.
- **Process (target by business day 10–15 after close):**
  1. Pull actuals; the AI suggests job/cost-code fixes for uncoded or miscoded bills, which go to a **review queue**.
  2. Chase PM forecasts.
  3. Compute WIP (cost-to-cost), over/under, fade vs last month and vs original bid.
  4. Reconcile contract assets/liabilities and retainage to the GL.
  5. Draft the variance narrative ("Job 214 faded 4 pts: unapproved CO #7 $38k, labor overrun").
  6. Builder review, then owner/controller approval.
  7. Propose the over/under journal entry; the client's bookkeeper posts it.
- **Outputs:**
  - WIP schedule in Excel (sureties and CPAs live in Excel).
  - PDF surety/bank packet: WIP, fade trend, backlog, underbilling aging with explanations.
  - Job-profit dashboard.
  - Exception list for the monthly WIP meeting.
- **Human-owned:** the PM's estimates (never invented by AI), owner approval, JE posting, CPA year-end.
- **MVP scope:** QBO only; Excel job master; email forecast agent; one packet format; no Desktop until client #3.
- **Stack:**
  - Python workers, Postgres (Supabase).
  - QBO API (Builder tier is free: 500k CorePlus credits/mo; Core calls free) ([Apideck](https://www.apideck.com/blog/quickbooks-api-pricing-and-the-intuit-app-partner-program)).
  - Claude with structured outputs.
  - Postmark/Twilio (10DLC registration for SMS).
  - openpyxl + WeasyPrint for outputs; Retool or a small Next.js admin for the review queue.
- **Time to MVP:** 4–5 weeks (estimate). Most of the work is reconciliation logic and the review queue, not AI.
- **Pricing (estimate):** setup $2,500 (cost-code mapping, job master, 12-month historic WIP rebuild). Monthly **$1,200 (≤15 jobs) / $1,800 (16–40 jobs)**. Founding clients $750/mo for 6 months.
  - **Anchors:** outsourced controller $2.5k–7.5k/mo ([SDO CPA](https://sdocpa.com/outsourced-accounting-cost)); Adaptive software ~$575–1,000/mo (third-party, unverified) ([Zoftwarehub](https://zoftwarehub.com/en-bh/products/adaptive/pricing), [Software Advice](https://www.softwareadvice.com/product/427439-Adaptive/)); QBO Advanced ~$340/mo; LiveFlow ~$500+/mo (unverified).
  - **Position:** a done-for-you monthly WIP close, not software.
- **ROI model (all assumptions explicit, estimate):**

  | Driver | Assumption | Monthly value |
  |---|---|---|
  | Bookkeeper/controller time | 16 hrs/mo on WIP + PM chasing, 70% saved, $33/hr loaded (BLS $23.66 × ~1.4) | ~$370 |
  | Owner time in WIP prep/meetings | 4 hrs/mo saved × $150/hr opportunity value | ~$600 |
  | Underbillings billed sooner | $120k of underbillings, 50% converted to billings 30 days earlier, 8% annual cost of capital (line of credit) | ~$400 |
  | **Subtotal ("hard," recurring)** | | **~$1,370/mo** |
  | Bonding capacity protected (lumpy) | Avoid a $100k working-capital disallowance → ~$1–2M aggregate capacity (10–20× rule) → one more $1.5M job at 8% gross margin = $120k GP/yr | **$10k/mo-equivalent, if it happens** |
  | Fade caught earlier (lumpy) | One CO recovered or overrun stopped earlier per year | **no data; client-specific** |

  **Honest read:** the hours-saved ROI alone (~$1.4k/mo) barely covers a $1,200 fee. **The case rests on bonding capacity and cash**, which are lumpy and hard to prove in 90 days. Pilots must measure them explicitly (§7 kill criteria).
- **Success metrics:**
  - Business days from month-end to approved WIP (baseline vs after).
  - % of PM forecasts received on time.
  - Miscoded cost $ corrected.
  - Underbilling $ aged >60 days.
  - Surety/bank follow-up questions per packet.
  - CPA year-end WIP adjustments (count and $).

**C2. Pay-App, Retainage and Waiver Desk (subs)**
- **Inputs:**
  - Subcontract PDFs and GC billing instructions. The AI extracts each GC's due date, required forms, waiver type and notarization, stored-materials backup, and retainage terms.
  - Schedule of values.
  - PM % complete by line (the same forecast agent as C1).
  - Supplier invoices for lower-tier waivers; prior pay apps.
- **Outputs:**
  - A draft continuation sheet and summary filled into the client's or GC's form. **AIA documents are licensed forms;** fill the client's licensed AIA document or the GC's own template, never a re-creation.
  - A per-GC submission checklist.
  - Auto-chase emails for lower-tier supplier waivers.
  - Retainage ledger and release reminders.
  - Submitted-pay-app aging and follow-up drafts.
  - Lien-notice deadline **flags.** Deadline rules come from the client's attorney or a lien-data provider; no legal advice.
- **Human:** PM confirms %, the office submits through GC portals (Textura, GCPay, Procore); **no bot logins**.
- **Integrations:** QBO progress invoicing, email, file storage.
- **MVP:** 4–6 weeks (estimate).
- **Pricing:** $1,000 setup + $600–1,000/mo, by number of active GC contracts (estimate).
  - **Anchors:** Siteline is quote-only ([Siteline](https://siteline.com/pricing)); lien-waiver point tools $49–799/mo (03 §2.3).
- **ROI (estimate):** 15 hrs/mo of pay-app work × 60% saved × $33 = ~$300. If clean first-time pay apps avoid one 30-day rejection delay per quarter on a $150k app at 8% cost of capital: ~$330/quarter, plus avoided payroll-float borrowing. Biggest upside: retainage collected sooner and no missed lien rights. That upside is real but needs per-client measurement.
- **Metrics:** pay-app rejection count, days submit→paid, retainage aged >90 days, missing-waiver incidents.

**C3. Bid Desk (subs with 1+ dedicated estimator)**
- **Inputs:** estimating inbox (Gmail/M365); a shared folder of downloaded bid docs. The client downloads them, so there is no credential handling.
- **Outputs:**
  - Deduped ITB log with deadlines.
  - **Trade-specific 1-page bid/no-bid brief with page citations:** scope sections, alternates, bonding/insurance, liquidated damages, schedule, prevailing wage, and red-flag clauses.
  - A fit score against the firm's own history (GC hit rate from E2).
  - Weekly digest.
  - Monthly hit-rate dashboard.
- **AI:** long-document extraction with a second citation-verification pass.
- **Human:** estimator decides; **no quantity takeoff** (drawing-vision accuracy is not good enough to sell).
- **MVP:** 3–4 weeks (estimate).
- **Pricing:** $500–900/mo (estimate), or a $400/mo add-on to C1. **Do not price at $1,500**: Downtobid charges $119–299 and Bid Board Pro ~$300–420.
- **ROI:** 4 estimator hrs/week saved × $53/hr loaded (BLS $79,130 ÷ 2,080 × 1.4) = ~$920/mo. One avoided scope-gap loss or one extra win per year dominates, but that is unproven.
- **Metrics:** hours of triage per week, % of ITBs declined within 24 hrs, red flags caught, bids per estimator, hit rate.

### Expansion offers
- **X1. 13-week cash forecast** on C1/C2 data: pay-app schedule × each GC's historic days-to-pay, retainage release dates, AP and payroll. $300–500/mo add-on (estimate).
- **X2. GC sub-compliance gate** for small GCs not on Procore: COI/waiver/W-9 status tied to AP approval. Note crowding: Procore Pay already blocks payment without signed waivers ([Procore](https://support.procore.com/products/online/user-guide/company-level/payments/release-notes)); COI tools cost $3–30 per vendor per year ([Billy](https://billyforinsurance.com/resources/best-coi-tracking-software-construction/), [BCS](https://www.getbcs.com/pricing)).
- **X3. Bond-agent / CPA white-label "WIP prep" service** for their book of contractors. Adaptive already sells a CPA-firm version, so compete on service and price.
- **X4. Backlog and bonding-capacity planner:** joins the WIP backlog with the E2/C3 bid pipeline to show which bids fit remaining capacity. This is where finance and bidding meet.

### Integration notes

| System | Route | Gotchas |
|---|---|---|
| QBO | OAuth API; Builder tier free; Silver $300/mo if you exceed 500k CorePlus credits ([Truto](https://truto.one/blog/how-much-does-the-quickbooks-api-cost-2026-pricing-rate-limits/)) | No native retainage field (QBO/IES per Knowify); Projects only on Plus/Advanced; OAuth scope is account-wide, so commit to read-mostly behavior and log every write |
| QB Desktop | **Conductor $49 per company file/mo** over the Web Connector ([Conductor](https://docs.conductor.is/faq)); or monthly report exports | Web Connector runs only while that Windows PC is on and the user is logged in ([Connex](https://help.connexecommerce.com/hc/what-is-the-quickbooks-web-connector)) |
| Procore (GCs) | REST API for commitments, COs, invoices | Procore Pay already gates on waivers; don't duplicate it |
| Foundation | Formal 7-phase partner onboarding with commercial/security review ([Foundation](https://developerdocs-dev.foundationsoft.com/integration-onboarding)); narrow public REST (AP-centric) | Start with Excel/CSV report exports |
| Sage 100 Contractor | Reads via SQL/ODBC; writes via imports ([Cleverence](https://www.cleverence.com/articles/sage-documentation/about-the-sage-100-contractor-api-4827/)) | Start with exports |
| Email / PDFs | Gmail/M365 APIs; PyMuPDF/pdfplumber; OCR fallback | Scanned waivers and notarized forms need OCR + human review |

### Ranking (1–5 each; score = product; my judgment)

| Offer | Value | Urgency | Solo feasibility | Defensibility | Score |
|---|---|---|---|---|---|
| **C1 WIP and Surety Packet Desk** | 5 | 5 (calendar-forced) | 4 | 3 (service + channel; software commoditizing) | **300** |
| C2 Pay-App / Retainage / Waiver Desk | 4 | 4 (monthly) | 3 (many GC forms/portals) | 3 | **144** |
| X1 13-week cash forecast | 4 | 3 | 4 | 2 | 96 |
| C3 Bid Desk | 3 | 3 | 4 | 2 (Downtobid, Autodesk) | 72 |
| X3 CPA/bond-agent white-label | 4 | 2 | 3 | 3 | 72 |
| X2 GC compliance gate | 3 | 3 | 3 | 2 | 54 |
| E1 Health Check | 3 | 4 | 5 | 2 | entry (60) |

### Bundle or sequence?
**Sequence. Finance first, bidding later.**
- They have different buyers (owner/bookkeeper vs chief estimator), different data (ledger vs inbox/PDFs), and different sales motions. A solo builder splitting focus in month 1 is the likeliest failure mode.
- Bring bidding in at month 3+ as **E2 (hit-rate audit) for existing C1 clients.** Join both in X4, where backlog and bonding capacity tell the estimator which bids to chase. That bundle is differentiated; neither half alone is.
- **This reverses my phase-1 top pick (the Bid Desk).** Reasons: cheap sub bid tools ($119–299), Autodesk's Bid Forwarding, and mostly vendor-only evidence of sub-side triage pain, against calendar-forced, surety-backed finance pain with natural referral channels.

---

## 5. Competition map

| Competitor | What it does for this segment | Price (source) | Threat to |
|---|---|---|---|
| **Intuit QBO Advanced** | Construction financials incl. WIP, AIA-style billing, change orders (Aug 2026, secondary sources); Project Management Agent drafts projects from uploaded contracts ([Intuit](https://quickbooks.intuit.com/global/resources/product-update/quickbooks-project-management-agent/)) | ~$340/mo ([Fourlane](https://www.fourlane.com/quickbooks-online-pricing-changes-2026-new-rates-and-fourlane-discounts/)) | C1 software layer |
| **Intuit Enterprise Suite (Construction)** | WIP, over/under, cost-to-complete reporting; AIA-*style* invoicing; **no native retainage, no G702/G703, no stored materials** per Knowify ([Knowify](https://knowify.com/resources/intuit-enterprise-suite-review/)) | Quote; ~$7.8k–12k+/yr third-party ([ERP Research](https://erpresearch.com/en-us/intuit-enterprise-suite-pricing)) | C1 for $5M+ firms |
| **Adaptive** | AI agents for AP job-costing, billing, WIP, compliance; QBO + Procore; CPA white-label | ~$575–1,000/mo third-party, unverified ([Zoftwarehub](https://zoftwarehub.com/en-bh/products/adaptive/pricing)); $57M raised | **C1, C2, X2, X3: the most direct funded rival** |
| **LiveFlow** | QBO reporting layer with construction WIP in Sheets | Not published; ~$500+/mo third-party ([Spendflo](https://www.spendflo.com/vendors/liveflow)) | C1 reporting |
| **Knowify** | Job management + AIA-style billing + QBO sync | Core $99–149/mo, Advanced $329–399/mo ([ERP Research](https://erpresearch.com/erp-add-ons/construction/knowify/pricing)) | C2 for small subs |
| **JobTread / Buildertrend** | PM tools with built-in WIP reports ([JobTread](https://www.jobtread.com/product-updates/2023-10-10-dynamic-work-in-progress-wip-report)) | JobTread ~$199/mo base (03) | C1 for residential |
| **Siteline** | Sub billing: pay apps, waivers, retainage | Quote only ([Siteline](https://siteline.com/pricing)) | **C2** |
| **Billd** | Material financing and pay-app advances | ~2% purchase fee + weekly/monthly fees; sources conflict ([Billd](https://billd.com/contractor-materials-financing/)) | Cash (complement, not rival) |
| **Procore (+ Pay, Helix)** | GC PM; Pay gates payment on waivers; Agent Builder open beta ([BusinessWire](https://www.businesswire.com/news/home/20251015796723/en/Procore-Advances-the-Future-of-Construction-with-New-AI-Innovations-at-Groundbreak-2025)) | ACV-based; small-firm estimates ~$4.5k–30k/yr ([OneCrew](https://www.getonecrew.com/post/procore-pricing), [CostBench](https://costbench.com/software/construction-management/procore)) | X2 |
| **Foundation / Sage 100 Contractor** | Full construction ERP with WIP | Foundation quote; Sage 100 Contractor ~$115–200/user/mo + $5–25k implementation (third-party) ([ITQlick](https://www.itqlick.com/compare/sage-100-contractor/foundation)) | S3 segment |
| **Lien/COI point tools** (Levelset, Waivr, LienDone, Sublien, TrustLayer, myCOI, Billy, BCS) | Waivers, notices, COIs | $49–799/mo; COI $3–30 per vendor per year (03; Billy; BCS) | C2, X2 |
| **BuildingConnected / Bid Board Pro** | Bid board; Bid Forwarding extracts outside ITBs; TradeTapp AI financial extraction | Bid Board Pro ~$3.6–5k/yr ([Spendbase](https://www.spendbase.co/?p=37350)) | C3 |
| **Downtobid** | AI plan reading, scope notes; sub bid boards | Subs $119 / $299 /mo; GCs $149/mo ([G2](https://ai.g2.com/marketplace/tools/downtobid)) | **C3** |
| **Nomic** | Spec-book search/review for precon teams | Professional $1,000/mo (10 seats), Business $6,000/mo ([Nomic](https://nomic.ai/pricing)) | C3 (upmarket) |
| **Document Crunch** | AI contract and spec risk review for contractors | Quote; "~$300/mo Team" in one directory (unverified) ([fitgap](https://us.fitgap.com/products/034309/document-crunch)) | C3 red-flag clauses |
| **Provision** | AI doc risk review for GCs (contracts/specs/drawings) | Not disclosed; $7M raised ([BetaKit](https://betakit.com/provision-raises-7-million-usd-to-build-ai-copilots-for-pre-construction-estimates/)) | C3 (GC-side) |
| **Trunk Tools (TrunkBid)** | AI bid leveling (GC-side), beta Mar 2026 ([CBO](https://www.constructionbusinessowner.com/trunk-tools-enters-preconstruction-with-launch-of-bid-leveling-agent/)) | Not disclosed | Low for subs |
| **Autodesk Pype AutoSpecs** | Spec → submittal log | Only in Forma for Construction Operations bundle ([Autodesk](https://www.autodesk.com/products/pype/overview)) | Post-award doc workflows |
| **Scopebase** | Listed at $69/user/mo on Capterra in phase 1; not re-verified in this pass | — | Low |
| **Outsourced construction accountants** | Human WIP/controller | $2.5k–7.5k/mo controller-level ([SDO CPA](https://sdocpa.com/outsourced-accounting-cost)) | C1 (and possible partners) |

### Likely in the next ~12 months (my judgment, not sourced roadmaps)
- **Intuit:** construction features in IES leave beta; WIP in QBO Advanced deepens. Retainage and G702/G703 are the obvious gaps Knowify calls out, so expect at least retainage. The PM Agent likely moves toward budget-vs-actual alerts (Insightful Accountant already claims this; unconfirmed). Assume **WIP-as-a-report is free inside QBO Advanced/IES by late 2027.**
- **Autodesk:** more AI in BuildingConnected/Bid Board Pro: Bid Forwarding exists; spec summarization and scope extraction are a short step from AutoSpecs. Assume **ITB triage plus a basic spec summary become built-in.**
- **Procore:** Helix agents and Agent Builder go GA, and Pay compliance keeps adding rules (June 2026 release). That covers GCs on Procore, not subs on QBO.
- **Adaptive:** spends its Series B on AP, billing, compliance, payments and WIP agents and on the CPA channel. **This is the competitor to watch.** Its target is $5M–$1B builders.

### Where a solo builder's edge holds
1. **The monthly WIP *process* as a service:** PM forecasts, reconciliation, surety narrative, meeting prep. Software vendors sell tools; owners of S1 firms want the job done.
2. **Ledger-agnostic:** QBO Plus, QB Desktop and Excel shops, which Intuit's new features and some tools skip.
3. **Relationship channels:** bond agents and construction CPAs in one metro. Funded SaaS goes national and self-serve.
4. **Custom per-firm mapping** of cost codes, GC-specific pay-app rules and surety formats, at small-firm prices.
5. **Speed:** fix a client's specific issue this week.

This edge is about service and margin, not a durable software moat. Price and position it as a **"fractional WIP desk powered by AI,"** not as SaaS.

---

## 6. Risks and de-risking

| Risk | Where it bites | De-risking |
|---|---|---|
| **Accuracy and liability.** A wrong WIP reaches a surety or bank | C1, E1 | Every number traceable to a source line; PM-confirmed estimates logged; owner signs off monthly; engagement letter limiting scope; professional liability (E&O) insurance; never send to the surety yourself (the client or bond agent does) |
| **Looking like CPA attestation** | C1, E1 | Never use "compilation," "review," "audit" or "assurance" for your work (those describe CPA engagements under AICPA SSARS/auditing standards); label outputs "management-prepared information." Check your state board of accountancy's rules on non-CPA titles before marketing. Position the CPA as the year-end attestor and you as their monthly data-prep partner |
| **Data quality** (no cost codes, miscoded bills, PMs ignore forms) | C1, C2 | E1 surfaces it upfront; charge setup to clean the job master; forecast agent with escalation to the owner; show "% forecasts received" on the owner dashboard |
| **AI hallucination in extraction** | C2, C3 | Structured extraction with page citations and a second verification pass; confidence thresholds route to the human review queue; no takeoff quantities |
| **Integration fragility** | Desktop, Foundation, Sage | Exports first; Conductor for Desktop; avoid Foundation's partner program until 5+ Foundation clients |
| **Legal: lien law and AIA forms** | C2 | No legal advice; lien rules from the client's attorney or a licensed data provider; fill licensed AIA or GC forms, never re-create AIA documents |
| **Trust** (outsider in the books; bookkeeper sees a threat) | All | Sell through bond agents and CPAs; position as the bookkeeper's assistant; NDA, a security one-pager, encrypted storage, MFA, least-privilege, audit log |
| **Commoditization** (Intuit, Adaptive, Autodesk) | C1, C3 | Price the service and the outcome (day-10 WIP, surety Q&A handled), not the report. Use native QBO WIP fields when present; feed them, don't fight them |
| **Lumpy ROI** | C1 | Pilot metrics agreed upfront; make a 90-day "time-to-WIP and underbilling $" result the renewal trigger |
| **Founder bandwidth** (service-heavy) | All | Cap at ~10 C1 clients before hiring or productizing; automate the review queue first |

---

## 7. Discovery-call kit

Target 15 calls: 8 owners/controllers (S1), 3 bond agents, 2 construction CPAs, 2 chief estimators. Ask for numbers, not opinions.

**Owners and controllers**
1. Are you bonded? What is your single and aggregate limit, and has your surety ever capped you or asked for more WIP detail? When?
2. How often do you send WIP to the surety or bank, and how many days after month-end does it actually go out?
3. Walk me through last month's WIP: who touched it, in what tool, and roughly how many hours each?
4. How do PMs give you cost-to-complete? How many were late or "same as last month" last time?
5. What did your CPA adjust on the WIP at last year-end? Do you know the dollar amount?
6. What's your current underbilling total, and the oldest underbilled job? Has a surety ever discounted underbillings?
7. How many pay apps a month? How many were rejected or sent back in the last 6 months, and why?
8. How much retainage is outstanding, and how much is older than 90 days?
9. Which ledger and edition (QBO Plus/Advanced, Desktop Contractor, Foundation, Sage)? Any plan to switch in the next 12 months?
10. What do you pay today for bookkeeping, outside accounting and construction software (monthly)?
11. If your WIP and surety packet were done, reconciled and explained by day 10 every month, what would that be worth? Would you pay $1,200/mo? Why or why not?

**Bond agents and CPAs**
12. What share of your contractor clients send WIP late or with errors? What does it cost them in capacity or fees?
13. Would you refer clients to (or white-label) a monthly WIP prep service? What would make you comfortable?

**Estimators**
14. How many ITBs a week? How many do you decline, and how quickly? How many hours a week go to triage and reading front-end specs?
15. Do you know your hit rate by GC? Would a monthly hit-rate and GC scorecard change which GCs you bid for?

**Kill criteria** (after 15 calls plus the first 5 health checks):
- Fewer than **5 of 8** S1 owners/controllers say WIP or surety reporting is a top-3 monthly headache, **or** fewer than **3** quote ≥ $750/mo willingness to pay → drop C1 as the flagship.
- Fewer than **2 of 3** bond agents willing to refer → the channel thesis fails; switch to direct outreach or reconsider.
- More than half of prospects are already on QBO Advanced/IES and happy with the native WIP and PM input → reposition to C2 (pay apps and retainage), or stop.
- Health checks find on average **<$50k underbillings or miscoding issues** per client → value too thin.
- For C3: fewer than 2 of the estimators spend more than 4 hrs/week on triage and spec front-end review → keep C3 as an add-on only.

---

## 8. Recommendation

### Flagship: the **Monthly WIP and Surety Packet Desk** (C1), sold through surety bond agents and construction CPAs to bonded subs and small GCs doing $5–30M on QuickBooks
- Entry offer: the paid **WIP and Underbilling Health Check** (E1).
- Expansion: **Pay-App / Retainage / Waiver Desk** (C2), then the 13-week cash forecast (X1).
- Bidding enters later as the hit-rate audit plus the backlog/bonding planner (E2 → X4).

### One-paragraph pitch
"Your surety judges you on your WIP. Most contractors your size build it in Excel, late, from PM guesses nobody checks. That's how underbillings get discounted and bonding lines get capped. Each month I run your WIP close for you. An AI assistant collects every PM's cost-to-complete by text or email and flags the numbers that don't add up. It reconciles everything to QuickBooks and drafts the explanations your underwriter will ask for. I review every figure, you approve it, and your bond agent gets a clean packet by day 10. I'm not your CPA. I make your CPA's year-end faster and your surety conversations shorter. Start with a one-week Health Check on last month's numbers: if I don't find something worth more than the fee, you don't pay."

The money-back guarantee is a sales choice (estimate), not a requirement.

### 30-day launch plan
**Week 1: Demo and list**
- Build E1 tooling on a QBO sandbox with a fake sub: 10 jobs, COs, a hidden late-stage underbilling, and a 4-point fade. Produce the Excel WIP, the surety packet PDF and the findings memo.
- Write the security one-pager and the engagement-letter scope ("management information; not a compilation, review or audit").
- Build a list in one metro:
  - 25 surety bond producers (NASBP member directory, local agency sites);
  - 20 construction-focused CPAs (CFMA chapter, firm websites);
  - 60 bonded subs and small GCs (state DOT prequalification lists, public bid tabulations, ABC/AGC/ASA member directories).

**Week 2: Channel conversations**
- Meet 8–10 bond agents and CPAs with the sample packet. Ask question 12 and request 2 introductions each.
- Run 10 discovery calls with owners and controllers using §7.
- Join or attend the local CFMA chapter (or AGC/ABC) event.

**Week 3: Paid health checks**
- Deliver 3–5 E1 health checks at $750, waived to $0 only for bond-agent referrals in exchange for a debrief with the agent.
- Record baselines: days-to-WIP, underbilling $, miscoded $, forecast response rate.

**Week 4: Convert and productize**
- Offer C1 founding terms ($1,500 setup, $750/mo for 6 months, case-study rights) to every health-check client. Target 2–3 signed.
- Run the first live month-end with the forecast agent. Hand the bond agent a packet and ask what they would change.
- Write one case study, even if anonymized. Decide using the §7 kill criteria.

---

## 9. Building blocks the distributor offer can reuse
1. **Document extraction pipeline:** email/PDF → structured JSON with field-level confidence and page citations. Here it reads subcontracts, pay-app instructions, waivers and ITBs; there it reads POs and invoices.
2. **QuickBooks connector layer:** QBO OAuth client (Builder tier), Conductor wrapper for Desktop, normalized entities (customers/jobs, items/cost codes, invoices, bills), and a write-audit log.
3. **Human review queue:** approve/edit/reject with reasons, confidence-based routing, and a full audit trail. The same UI serves "miscoded bill," "PO line mismatch" and "spec brief citation check."
4. **Chase agent:** templated plus LLM-drafted follow-ups by email/SMS with escalation rules. Here it chases PM forecasts and supplier waivers; there it chases customer POs and AR.
5. **Exception and anomaly engine:** rules plus LLM explanation (fade, underbilling aging; there, price or quantity mismatches).
6. **Report generator:** Excel (openpyxl) plus PDF packets plus a weekly owner email.
7. **Security kit:** NDA, security one-pager, least-privilege, encryption, engagement-letter templates.
