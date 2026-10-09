# 05: Wholesale Distributors (SMB / Mid-Size): What to Sell Them

*Analyst: Opus B · Date: 2026-10-09 · Phase 2 deep dive · Scope: distributors running QuickBooks (Online, Desktop Enterprise), Acumatica, or small NetSuite. Construction is out of scope; another agent covers it.*

---

## 0. TL;DR

- **Beachhead.** Independent **jan-san, packaging and safety-supply distributors** (and similar "general line" industrial supply houses), roughly **$3M–$40M revenue** *(estimate)*, running **QuickBooks Desktop Enterprise, QBO Plus/Advanced or Acumatica**.
  - They are reachable through buying groups (AFFLINK lists 300+ distributor members; Triple S lists 120+) and through ISSA.
  - Avoid MEP (electrical, plumbing, HVAC): it runs on Eclipse, P21 and Infor, and Prokeep and Conexiom are already there. Avoid foodservice too: Choco and Pepper have raised hundreds of millions between them.
- **Flagship offer.** A **PO-to-Order Agent**. It watches the orders@ inbox, reads emailed PDF, Excel and body-text purchase orders, maps customer part numbers and units of measure to the distributor's item master, checks price and stock, and drafts the order in the ERP. A customer service rep (CSR) approves the order from a review queue.
  - **Price:** $3k–6k setup plus $750–1,500/mo *(estimate)*.
  - **Wedge:** a paid **"Order Desk & Cash Leak Audit"** ($750–1,500, credited toward setup). The audit backtests extraction accuracy against the distributor's own order history before they commit.
- **Expansion offers:**
  - A **Supplier Cost-Change & Margin Guard**, made urgent by tariff-driven supplier price increases.
  - An **AR Collections Copilot with a cash dashboard**.
  - Later: a CSR inbox agent, a quote assistant, reorder suggestions and rebate tracking.
- **Evidence quality.** Better than in phase 1, but still thin on hard time-per-order data. The independent anchors:
  - BLS wage data for order clerks.
  - The APQC per-order cost benchmark.
  - Job postings showing reps entering 20–200 orders a day, including emailed orders keyed into QuickBooks.
  - DSG's survey: among distributors already implementing AI, **62% use it for order automation**, the top use case.
  - Intuit and Acumatica community threads.
  - Everything else (touchless rates, % of CSR time) is vendor-sourced and labeled as such.
- **Correction to phase 1.** QuickBooks Online **does** now have sales orders in the UI on the Plus and Advanced tiers, per Intuit staff replies from Dec 2024 and Jun 2025. Whether the **API** exposes them is unverified, so test it in a sandbox on day 1. See §5.3.

---

## 1. Segment and buyer map

### 1.1 Sub-vertical scan

| Sub-vertical | Typical ERP (evidence) | Order-channel mess | Funded competitors already selling AI order entry | Buyer reachability | Fit for a solo builder on the QB/Acumatica tier |
|---|---|---|---|---|---|
| **Electrical / plumbing / HVAC (MEP)** | Eclipse, P21, Infor are "the dominant ERP systems in the MEP distribution space" ([HVACR Trends on Prokeep, Feb 2026](https://hvacrtrends.com/prokeep-distributor-order-automation-ai-quoting/)) | High: text, photo, email from contractors | **Prokeep** (Eclipse/P21/Infor, pitched as affordable "under $25 million"); Conexiom | Good (NAED, ASA, HARDI) | **Poor.** Wrong ERP tier, and a direct competitor already targets small firms |
| **Foodservice** | Mixed; Pepper reports "500+ integrations" ([AgFunderNews, Apr 2026](https://agfundernews.com/inside-peppers-push-to-digitize-foodservices-long-tail-armed-with-50m-and-agentic-ai)) | Very high: voicemail, text, late-night orders | **Pepper** ($50M Series C, announced Feb 20, 2026, 500+ distributors); **Choco** (~$211M–$338M raised; totals conflict across sources) ([Clay dossier](https://www.clay.com/dossier/choco-funding)) | Good (IFDA, regional) | **Poor.** Heavily funded and category-specific |
| **Building materials / lumber** | No verified data on ERP mix | Medium–high | **Proton.ai** order and quote entry; early user is a building-materials distributor ([DSG, Jul 2026](https://distributionstrategy.com/2026/07/proton-ai-launches-ai-platform-to-automate-order-and-quote-entry-for-distributors/)) | Medium | Medium–low |
| **Industrial / MRO, fluid power, power transmission** | Mixed: P21, Infor SX.e and others at mid-market; QuickBooks and Acumatica at the small end (no hard data) | High: emailed PDF POs from manufacturers and plants with formal PO numbers | **Endeavor** (customers incl. ClarkDietrich, Menasha, Viking, Bridgestone; [Yespress](https://yespress.io/endeavor.md)), **Avent** (YC S25, 5 people; [YC](https://www.ycombinator.com/companies/avent)), Proton.ai, WizCommerce, Conexiom | Good (ISA, NFPA, PTDA). Endeavor already works NFPA ([NFPA](https://www.nfpa.com/news/crawl-walk-run-with-ai-from-order-entry-to-quoting-to-pricing)) | **Medium.** Competitors aim at larger accounts, so small QuickBooks shops are open |
| **Jan-san / packaging / safety supply** | Vendors pitch jan-san firms that have "outgrown your QuickBooks Enterprise" ([Advantive-sponsored CMM, 2023](https://cmmonline.com/articles/janitorial-distribution-software-solutions)); QuickBooks-sync ERP Acctivate targets jan-san ([Acctivate](https://acctivate.com/?p=17436)) | High: building service contractors, schools and healthcare send emailed POs and repeat orders | **Pepper** publishes jan-san case studies and sells "Order Agent" ([Pepper blog, Apr 2025](https://www.usepepper.com/post/best-erp-for-jan-san-distribution-2025-solutions-features)); its jan-san ERP list does **not** include QuickBooks | **Very good.** AFFLINK serves "more than 300 distributors… of jansan, packaging, safety, and office products" ([ISSA](https://www.issa.com/industry-news/afflink-partners-with-american-office-products-distributors/)); Triple S has 120+ members ([Cleanfax](https://cleanfax.com/100-years-of-supply-and-demand/)); ISSA has ~10,500 member organizations | **Best.** QuickBooks-heavy small end, repeat-order patterns suit AI matching, and buying groups give concentrated access |
| **Auto parts** | Not researched; no data | n/a | n/a | n/a | Skip (catalog-driven ordering) |

### 1.2 Who feels the pain, who decides, who pays (beachhead: $3M–$40M independent distributor)

| Offer | Feels the pain daily | Champions / influences | Decides | Pays (budget) |
|---|---|---|---|---|
| PO-to-Order Agent | CSRs and inside sales reps re-keying orders; order desk lead | Operations manager / GM | **Owner/President** (at this size, almost always) | Owner; G&A, or justified as "a CSR we don't have to hire" |
| AR Collections Copilot | AR clerk / office manager; owner chasing big accounts | Controller / outside CPA | Owner | Owner (cash-flow framing) |
| Margin Guard | Purchasing manager, owner (pricing) | Sales manager (fears customer pushback) | Owner | Owner (margin framing) |
| CSR inbox / quote assistant | CSRs, inside sales | Sales manager | Owner | Owner |

The pay figures are useful anchors. Order clerks in durable-goods wholesale averaged **$23.11/hr ($48,070/yr)**; in nondurable wholesale (4244/4248) they averaged **$20.25/hr ($42,120/yr)** (BLS OEWS, May 2023: [BLS](https://www.bls.gov/oes/2023/may/oes434151.htm)). A newer BLS release (May 2025) exists, but I couldn't retrieve the wholesale breakdown for it.

### 1.3 Beachhead decision and why

**Pick: independent jan-san, packaging and safety distributors on QuickBooks Enterprise, QBO or Acumatica, reached first through AFFLINK, Triple S and ISSA. Add small industrial/MRO houses on the same ERPs as the second ring.**

1. **ERP tier fits the gap.**
   - Funded order-entry vendors integrate with mid-market ERPs. Prokeep supports Eclipse, P21 and Infor. Conexiom is "compatible with 40 ERP systems" and has "over 600 customers" ([IT Brief, Sep 2026](https://itbrief.co.uk/story/conexiom-launches-ai-native-relay-for-order-automation)). Endeavor's named customers are large manufacturers and distributors.
   - Pepper's own jan-san ERP list omits QuickBooks entirely.
   - QuickBooks Desktop Enterprise is the only Desktop edition Intuit still sells to new customers ([Method](https://www.method.me/blog/quickbooks-desktop-discontinued/)). It's a sticky installed base that funded vendors find awkward to integrate with.
2. **Order volume per rep is real.** Postings show "25 to 50 orders daily" at an industrial distributor ([Randstad, Sep 2026](https://www.randstad.com/jobs/customer-serviceorder-desk_scarborough_47415143/)). Other postings (via search snippets; original pages since expired) show "20+ orders per day" from a "Releases" inbox and reps "processing online orders received via email and entering them into QuickBooks" (Insight Global listings; §3).
3. **Repeat-order patterns.** Jan-san buyers (building service contractors, facilities, schools) reorder consumables, so per-customer cross-reference tables pay off quickly *(reasoned inference, not measured)*.
4. **Reachability.** Buying groups concentrate hundreds of independents and run conferences and vendor programs. One partnership or speaking slot reaches many owners.
5. **Risk acknowledged.** Pepper is already in jan-san. The counter-position is QuickBooks/Acumatica depth, white-glove setup, and an O2C-plus-margin bundle. If Pepper ships a QuickBooks integration and SMB pricing, re-evaluate (see kill criteria, §8).

---

## 2. Workflow maps: where hours and dollars leak

### 2.1 Order-to-cash (O2C)

```
[1] Order arrives ──► [2] Interpret ──► [3] Enter in ERP ──► [4] Acknowledge ──► [5] Pick/pack/ship ──► [6] Invoice ──► [7] Collect
 email PDF/XLS/body   customer, ship-to,  SO / estimate /     confirm price,       pick ticket, backorder  invoice from SO,  statements, dunning,
 fax-to-email, phone  PO#, cust part# →   invoice in QB/       ETA, backorders      handling, POD           freight & fees    remittance match,
 text/photo, portal,  SKU, UOM (case vs   Acumatica/NetSuite                                                                disputes / credits
 EDI                  each), price, stock
```

| Step | Leak | Quantification | Source type |
|---|---|---|---|
| 1–3 Intake and entry | Re-keying time | APQC median **$8.48 per sales order** for the whole "manage sales orders" process (inquiries → accounting; n=2,089) ([APQC](https://www.apqc.org/resources/benchmarking/open-standards-benchmarking/measures/total-cost-perform-process-manage-11)). APQC's 2016 data: median **$24.21**, top performers $5.11, bottom $40.87 ([Esker-hosted APQC PDF](https://cloud.esker.com/fm/others/K03319_Sales%20Order%20Processing_2016_Esker%203.pdf)) | Independent benchmark (definitions differ by year) |
| 1–3 | Share of CSR time spent re-keying | "can consume 20% to 40% of the time from multiple CSR's" ([DSG, 2016](https://distributionstrategy.com/2016/10/the-electronic-postman-always-rings-much-more-than-twice/), in an article promoting Conexiom). MDM: keying emailed orders "can take up to half a day" for CSRs (older article, source unclear; [MDM](https://www.mdm.com/blog/tech-operations/operations/7-steps-to-offset-the-distribution-labor-shortage/)) | Vendor-adjacent; old |
| 1 | How customers order | **~74% of end users** order by email "very frequently or frequently" (DSG, 3,500+ distributor customers, 2016) | Independent survey, but 10 years old |
| 2 | Wrong item or UOM → wrong shipment → return, credit memo, re-ship freight | **No data found** on SMB distributor order-entry error rates. WERC 2018 median order-picking accuracy was 99.30% ([Honeywell summary](https://www.honeywell.com/us/en/news/featured-stories/2020/02/which-metrics-matter-most-to-dc-operations)), but that's picking, not entry | Gap; measure in the audit |
| 4 | Slow acknowledgment and response | Vendor claim: customers expect a reply within an hour, but actual response is "often two business days" ([Workist](https://www.workist.com/en/blog/ai-first-inside-sales-2026-challenges-maturity-model-and-ai-agents-in-practice)) | Vendor |
| 2/6 | Wrong or contract price, unbilled freight and fees | **No independent data found** | Gap |
| 7 | Late payment | US B2B: **43% of invoice value overdue**, 5% written off (Atradius 2025, n=240, skewed to manufacturers and wholesalers; via [secondary blog](https://lonelyentrepreneur.com/founder-days-to-get-paid/); primary not opened). Intuit: 56% of US small businesses are owed money, **$17.5K average overdue**, 47% have invoices more than 30 days late (n=2,487; [Intuit, Mar 2025](https://quickbooks.intuit.com/r/small-business-data/small-business-late-payments-report-2025/)) | Independent / first-party survey |
| 7 | DSO | Credit Research Foundation cross-industry median DSO **36.7 days** (Q2 2025; [CRF](https://www.crfonline.org/tools/national-summary-of-domestic-trade-receivables-results-summary)). A wholesale-specific range of 30–50 days is vendor-compiled ([Monk](https://monk.com/blog/ar-benchmarks-by-industry)) | Mixed |

### 2.2 Procure-to-pay (P2P)

```
[1] Reorder decision ──► [2] PO to supplier ──► [3] Supplier ack / price change ──► [4] Receive ──► [5] Vendor invoice ──► [6] Match ──► [7] Pay ──► [8] Claim rebates
 min/max, spreadsheet     ERP PO                  price letters, price files          packing slip    emailed PDF           2/3-way      terms /     buying-group &
                                                  (tariff-driven)                     vs PO                                              discounts   supplier programs
```

| Step | Leak | Quantification | Source type |
|---|---|---|---|
| 3 | **Cost increases not passed through fast enough** | NAW–MDM 2025 (200+ distributors): ~a third had already seen supplier hikes of 25%+; **62% expected COGS up 10%+**; 67% reported negative financial impact ([MDM summary](https://www.mdm.com/news/research/economic-trends/new-naw-mdm-research-shows-tariffs-growing-impact-on-supply-chain/)). 2026: tariff "yo-yo" volatility makes static price lists hard to hold ([DSG, Jan 2026](https://distributionstrategy.com/2026/01/tariffs-in-2026-force-wholesale-distributors-to-rethink-pricing-sourcing-and-contracts/)) | Independent association survey |
| 3 | Margin erosion from late or poor price updates | "average margin erosion of 1.6%" when updates are late; 6% when implementation is poor ([PHCP Pros, Jul 2025](https://www.phcppros.com/articles/21838-beyond-price-hikes-strategic-approaches-to-managing-rising-tariffs-in-wholesale-distribution); author is CEO of pricing vendor Intuilize) | **Vendor** |
| 5–6 | AP processing cost and exceptions | Ardent 2025: **$12.42 average vs $2.65 best-in-class** per invoice; exceptions 22% vs 9%; cycle time 17.4 vs 3.1 days (secondary summaries; [Tradeshift-hosted](https://tradeshift.com/state-of-epayables-2025-report/)) | Analyst (vendor-sponsored) |
| 8 | Unclaimed rebates | **52%** of distributors believe they don't receive all the rebates they earn; 87% call rebates critical to profitability ([MDM on Enable survey](https://www.mdm.com/news/operations/finance/rebates-half-of-distributors-say-theyre-not-getting-what-theyve-earned/)) | **Vendor survey**; perception, not measured loss |
| 1 | Stockouts and overstock | NAW–MDM: 48% slowed replenishment in response to tariffs. **No SMB stockout-cost data found** | Gap |

**So where are the biggest leaks for a $3M–$40M distributor?**
1. CSR hours on steps 1–3: the most frequent and most visible leak.
2. Margin lost on cost changes: the largest dollars per event, and urgent now.
3. Cash tied up in AR: large balance, but less urgent.

AP matching is real but is being commoditized (§5.2).

---

## 3. Pain validation beyond vendors

Reddit is blocked from this environment. Here is what I could verify instead, split by source type.

### 3.1 Independent or first-party evidence

| Evidence | What it shows | Link |
|---|---|---|
| **BLS OEWS (May 2023)** | Durable-goods wholesalers are the #1 industry employing order clerks (7,730 clerks, $48,070 mean). Nondurable wholesalers 3,320 ($42,120). Professional/commercial equipment wholesalers 3,100 ($46,270) | [BLS](https://www.bls.gov/oes/2023/may/oes434151.htm) |
| **Job posting: industrial distributor (Sep 2026)** | "processing 25 to 50 orders daily"; "via email, phone, and electronic order systems"; CAD $55–65k | [Randstad](https://www.randstad.com/jobs/customer-serviceorder-desk_scarborough_47415143/) |
| **Job postings (2025–2026, via search snippets; originals now expired)** | Insight Global (Cincinnati): "processing online orders received via email and entering them into QuickBooks," est. $16–20/hr. Aston Carter (IL, Jul 2025): QuickBooks order entry, $22–25/hr. Insight Global (GA, Mar 2026): "20+ orders per day" from a releases inbox. A CareerBuilder CSR II posting cites 150–200 orders/day | Insight Global pages returned HTTP 410; treat as snippet-level evidence |
| **DSG survey (Dec 2025, n=233 execs, skews tech-forward)** | 63% piloting or exploring AI; 27% at scale. **Among implementers, order automation is #1 at 62%**, ahead of chatbots (41%) and demand forecasting (28%). Top barriers: skills (33%) and data (24%) | [DSG, Feb 2026](https://distributionstrategy.com/2026/02/distributors-reach-an-ai-inflection-point/) |
| **MDM/NAW study (Apr 2026, 400+ leaders)** | 73% expect value from AI, only 16% have achieved it; ~9 in 10 are pursuing it. Sponsored by Canals, Descartes, Epicor and Revalgo; full report gated | [MDM](https://www.mdm.com/webinar-where-400-distribution-leaders-are-investing-in-ai) |
| **ASA member surveys (Oct 2025, Apr 2026)** | "Manual and repetitive work is the most common issue," followed by data quality and integration | [ASA](https://www.asa.net/News/News/surveys-reveal-gap-between-ai-ambition-and-operational-reality-in-distribution) |
| **Acumatica Community (Apr 2025 → Jul 2026)** | "I work in a furniture business and looking at ways to reduce manual entry of Sales Orders." Replies suggest UnForm and home-built tools, and ask "OCR versus LLM tools like ChatGPT, Claude, Gemini?" | [Acumatica Community](https://community.acumatica.com/develop-integrations-with-web-services-apis-289/ocr-for-automating-the-sales-order-raising-process-i-e-email-pdf-s-30260) |
| **Intuit Community (Jun 2025)** | User says estimates don't work as sales orders because "it does not track the inventory the way I need it." Intuit staff confirm sales orders exist on QBO Plus/Advanced | [Intuit Community](https://quickbooks.intuit.com/community/account-management-7/when-will-sales-orders-be-an-available-option-76581) |
| **Intuit Community (Dec 2024 – Jan 2025)** | Users report layout errors with QBO sales orders; one advises "You should stay with QB Desktop" | [Intuit Community](https://quickbooks.intuit.com/learn-support/en-us/other-questions/quickbooks-online-sales-orders/00/1515566) |
| **NAW–MDM tariff survey (2025)** | Cost-pass-through pressure (§2.2) | [MDM](https://www.mdm.com/news/research/economic-trends/new-naw-mdm-research-shows-tariffs-growing-impact-on-supply-chain/) |
| **Intuit Late Payments 2025; Atradius 2025** | AR pain (§2.1) | linked above |

### 3.2 Vendor claims (directional only)

- Conexiom "80%+ straight-through processing" ([Yespress](https://yespress.io/conexiom)).
- Y Meadows "90% reduction" in manual entry ([Y Meadows](https://ymeadows.com/en/insights/blog/ai-order-entry-for-distributors/)).
- Pepper's inbox tool "80-90%" first-pass accuracy ([Pepper vs Choco](https://www.usepepper.com/compare/pepper-vs-choco)).
- A Choco customer credits it with cutting processing time 75% (Choco materials).
- Endeavor: "as much as 90%" less manual work.
- 20–40% of CSR time spent re-keying (DSG 2016, in a Conexiom-promoting piece).
- Intuilize: 1.6% / 6% margin erosion.
- Enable: 4% of rebates go unclaimed.

### 3.3 Still missing (validate in discovery)

- Minutes per order by format.
- Order-entry error rate and the cost of each error.
- Percentage of orders arriving by email PDF vs body text vs phone at QuickBooks-tier distributors.
- Willingness to pay at this tier.

The paid audit (§4, E0) is designed to produce exactly these numbers for each prospect.

---

## 4. Offer ladder

### Ranking (1–5 each; score = product of the four)

| Offer | Value | Urgency | Feasibility (solo) | Defensibility | Score | Role |
|---|---|---|---|---|---|---|
| **C1 PO-to-Order Agent** | 5 | 4 | 4 | 3 | **240** | Flagship |
| **C3 Supplier Cost-Change & Margin Guard** | 4 | 4 | 4 | 3 | **192** | Core #2 (tariff-timely) |
| **X1 CSR Inbox Agent** (status and acknowledgment replies) | 3 | 3 | 4 | 3 | 108 | Expansion on C1 data |
| **C2 AR Collections Copilot + Cash Dashboard** | 3 | 3 | 5 | 2 | 90 | Core #3 / bundle |
| X2 Quote / RFQ Assistant (with substitutes) | 4 | 3 | 2 | 3 | 72 | Later |
| X4 Rebate Tracker | 3 | 2 | 3 | 3 | 54 | Later |
| X3 Reorder & Purchase Suggestions | 4 | 2 | 3 | 2 | 48 | Later (Netstock etc.) |
| C4 Vendor-invoice 3-way match | 2 | 2 | 4 | 1 | 16 | **Don't lead with it** (commoditized) |

*Scores are my judgment, informed by the evidence above.*

---

### E0: Entry offer: "Order Desk & Cash Leak Audit" (paid diagnostic)

- **Inputs:**
  - Read-only export of the orders@ mailbox (2–4 weeks; or forwarded samples).
  - ERP exports: sales orders and invoices for the same period, item master, customer list, credit memos and returns for 6 months, AR aging, top-20 supplier price-change notices from the past year.
- **Outputs:**
  1. Order mix by channel, format, customer and lines per order.
  2. Estimated CSR hours per week on entry. Based on a short time study (CSR times 20 orders) multiplied by volume.
  3. **Backtest:** run the extraction agent on ~100–200 historical emails and compare against what CSRs actually entered in the ERP. The ERP history is free labeled data. Report field-level accuracy (customer, PO#, SKU, qty, UOM, price).
  4. Error-cost analysis from credit memos tagged "wrong item/qty."
  5. AR snapshot with DSO and an over-60-day list.
  6. A margin-exposure scan: SKUs whose cost rose in the last 12 months while sell price didn't.
  7. A one-page ROI model and proposal.
- **AI vs human:** AI handles extraction, classification and matching. The human (you) handles interviews, the time study and interpretation.
- **Time:** about 5–8 working days per audit once the pipeline exists *(estimate)*.
- **Price:** **$750–$1,500**, credited 100% toward setup if they buy within 30 days *(estimate)*.
  - Anchor: one week of a CSR's loaded cost is roughly $1,000–1,200 at BLS mean wages plus burden *(estimate)*.
- **Why it matters:** it de-risks accuracy (the #1 objection), produces the ROI numbers that don't exist publicly, and qualifies out prospects with low volume.

---

### C1 (Flagship): PO-to-Order Agent

**Inputs**
- A dedicated mailbox (orders@) or forwarding rule, via Gmail API or Microsoft Graph.
- Attachments: PDF (native or scanned), XLSX/CSV, images, and body-text orders. Fax-to-email arrives as PDF.
- ERP master data: customers, ship-tos, items, UOMs, price levels/contract prices, on-hand quantities.
- A **customer cross-reference table** (customer part # ↔ SKU). It's seeded from order history and grows with every correction.

**Outputs**
- A draft order in the ERP:
  - QuickBooks Desktop Enterprise **Sales Order** (via `SalesOrderAdd`).
  - Acumatica **SalesOrder**.
  - NetSuite **salesOrder**.
  - QBO: a sales order if the API supports it, else an **Estimate** that converts to an invoice (§5.3).
- An optional auto-acknowledgment email to the customer (order #, ETA, backorders).
- An exceptions queue with a reason code for each: unknown part, price mismatch, UOM ambiguity, credit hold, out of stock, duplicate PO#.
- A daily dashboard: touchless %, minutes saved, top exception causes, and the customers who most need a format fix.

**What is AI and what stays human**

| AI | Deterministic code | Human (CSR) |
|---|---|---|
| Classify the email (new order, change, status question, quote request, junk) | Duplicate-PO detection, credit-hold check, stock check | Approve every order during the pilot; later approve only flagged ones |
| Extract header and lines from messy layouts | Price validation against the price level / contract | Resolve exceptions; confirm substitutions |
| Map customer part # or description to SKU (cross-ref first, then embedding/fuzzy match against the item master) | UOM conversion rules per customer | Teach the system by correcting it; corrections write back to the cross-ref |
| Draft the acknowledgment / exception email | Write to the ERP through the connector, with idempotency keys | Phone orders stay human, unless a later voice add-on |

**MVP scope (4–5 weeks, estimate)**
- One ERP connector: QuickBooks Desktop Enterprise via Conductor, or Acumatica. Pick the one your first design partner runs.
- Gmail/Outlook ingestion; PDF, XLSX and body-text extraction.
- Cross-ref matching plus a review UI.
- "Shadow mode" first: the agent drafts and the CSR compares against their own entry, so nothing is written to the ERP. Then "approve mode": one-click write.
- Out of MVP: EDI, voice, auto-release without approval, multi-warehouse allocation logic.

**Build stack**
- Next.js (review UI plus dashboard), Postgres with pgvector (Supabase is fine), a job queue / background workers.
- Claude for document understanding and classification, with structured (JSON-schema) outputs.
- Gmail API / Microsoft Graph webhooks.
- ERP connectors:
  - **Conductor** for QuickBooks Desktop: **$49 per company file per month**, unlimited production API use ([Conductor FAQ](https://docs.conductor.is/faq)). SalesOrders are supported ([Conductor docs](https://docs.conductor.is/qbd-api/sales-orders/create)).
  - QBO API: Intuit App Partner Program Builder tier is $0 with 500k read credits per month; writes are free ([Apideck](https://www.apideck.com/blog/quickbooks-api-pricing-and-the-intuit-app-partner-program)).
  - Acumatica contract-based REST: `PUT /entity/Default/<ver>/SalesOrder` ([dev guide](https://help.myob.com.au/advanced/Docs/Published/IntegrationDevelopmentGuide/IntegrationDev_RESTExample_SalesOrder_CreateWithAllocations.html)).
  - NetSuite REST: `POST /salesOrder`. Mind per-account concurrency, which can be as low as about 5–15 slots ([Oracle docs](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_164095787873.html)).
- An evaluation harness: a golden set of historical orders and their ERP ground truth, re-run on every prompt or model change.

**Pricing (estimate)**
- **Setup $3,000–$6,000.** Covers the connector, cross-ref seeding from 12 months of history, onboarding the top 20 customers' formats, and the shadow-mode period.
- **Monthly by volume:**
  - up to ~800 orders/mo: **$750**
  - up to ~2,500 orders/mo: **$1,200**
  - above that: **$1,500 + $0.35/order**
- Month-to-month after a 3-month pilot.
- **Competitor anchors:**
  - Conexiom, Endeavor, Pepper and Y Meadows are quote-only with annual contracts ([ERP Research](https://erpresearch.com/erp-add-ons/distribution/conexiom); [AgFunderNews](https://agfundernews.com/inside-peppers-push-to-digitize-foodservices-long-tail-armed-with-50m-and-agentic-ai)).
  - WizCommerce from about $500/mo (third-party; [Software Advice](https://www.softwareadvice.com/ecommerce/wizcommerce-profile)).
  - Orderwerks portal: $60/user/mo ([Orderwerks](https://orderwerks.com/pricing)).
  - Generic extraction with no ERP logic: Lido from about $29/mo ([Lido help](https://help.lido.app/en/article/pricing-plans-and-page-allowance-15z9f74/)); Nanonets about $0.30/page ([IDP Software](https://idp-software.com/vendors/nanonets/)).

**ROI model (illustrative; every input is an assumption to replace with audit data)**

| Input | Value | Basis |
|---|---|---|
| Emailed/PDF orders per day | 60 | Assumption; job postings show 20–200/day per rep |
| Avg manual handling time | 6 min/order | **Assumption; no independent data**; time it in the audit |
| Loaded CSR cost | $28/hr | BLS mean $23.11/hr (durable wholesale) + ~20% burden *(estimate)* |
| Working days | 250 | |
| **Manual cost/yr** | 60 × 6 min = 6 h/day × $28 × 250 = **$42,000** | |
| Post-automation avg handling | 1.5 min/order (blend of fast approvals and slower exceptions) | Assumption |
| **Labor saved/yr** | 4.5 h/day × $28 × 250 = **$31,500** | |
| Error reduction | 1% of orders × $50/error avoided = **$7,500/yr** | **Assumption; no data**; check credit memos |
| **Total value** | **~$39,000/yr** | |
| Price (yr 1) | $4,500 setup + $750 × 12 = **$13,500** | |
| **Yr-1 ROI** | ~2.9× (payback ~4 months) | |

The bigger story is often **capacity**: absorbing 20–30% order growth without hiring another order clerk (BLS mean $42k–48k plus burden). *Reasoned, not measured.*

**Success metrics**
- Touchless rate: target 60%+ by month 3. *Estimate; vendors claim 80–90%.*
- Field-level accuracy ≥99% on approved orders.
- Median minutes from email receipt to order entered.
- CSR minutes per order (before vs after).
- Credit memos tagged entry error (before vs after).
- Customer acknowledgment time.

---

### C3: Supplier Cost-Change & Margin Guard

- **Problem.** Suppliers send price-increase letters and spreadsheets, often tariff-driven, as PDF or XLSX by email. Updating costs and sell prices across hundreds of SKUs is manual. Some items don't get updated for weeks, so margin quietly erodes.
- **Inputs:** supplier price notices (PDF/XLSX/email body), the item master with current cost and sell prices / price levels, customer contract prices, sales velocity per SKU.
- **Outputs:**
  1. Parsed new costs with effective dates, matched to SKUs.
  2. A margin-impact report: which SKUs and customers fall below target GM%, and the gross-profit dollars at risk per month.
  3. Proposed new sell prices by rule (keep GM% / round to price points / cap the % increase for key accounts).
  4. Approved updates written back to the ERP.
  5. Customer price-change notice drafts with the effective date.
  6. A "stale cost" alert: SKUs whose last received PO cost is above the system cost.
- **AI:** parsing heterogeneous price files, matching supplier part numbers to SKUs, drafting customer letters, summarizing exposure. **Human:** every pricing decision and every customer communication.
- **MVP:** 3–4 weeks *(estimate)*. It reuses C1's extraction, matching and connectors.
- **Pricing:** $1,500–$3,000 setup plus **$400–$800/mo**, or a one-off "tariff repricing sprint" at $2,500–$5,000 *(estimate)*.
  - Competitor anchors: pricing-optimization vendors (Intuilize, Zilliant, Vendavo, INFORM) exist. I found no public SMB pricing, so treat this as unverified.
- **ROI model (illustrative):**
  - Assume $10M revenue at a 25% gross margin, so COGS is $7.5M.
  - Assume 30% of COGS sees a 5% cost increase: about $112.5k/yr of new cost.
  - If pass-through lags 30 days on average, unrecovered cost is about $9.2k per increase event (112.5k × 30/365). With 2–3 events a year, that's **$18k–$28k/yr**, before counting SKUs that never get updated.
  - All inputs are assumptions. The vendor-reported benchmark is 1.6% margin erosion from late updates ([PHCP Pros](https://www.phcppros.com/articles/21838-beyond-price-hikes-strategic-approaches-to-managing-rising-tariffs-in-wholesale-distribution)).
- **Metrics:** days from supplier notice to sell-price update; % of SKUs with stale cost; GM% on affected SKUs (before vs after).

---

### C2: AR Collections Copilot + Cash Dashboard

- **Inputs:** AR aging and open invoices (QBO/QBDT/Acumatica), customer contacts, payment history, the AR inbox (replies, remittances, disputes).
- **Outputs:**
  - Risk-tiered dunning sequences in the owner's voice.
  - AI reading of replies, which classifies them as promise-to-pay, dispute, remittance or "send copy of POD/invoice" and auto-attaches documents.
  - A dispute queue for the AR clerk.
  - A weekly cash forecast based on each customer's actual pay lag.
  - An owner dashboard: DSO, over-60 list, promised vs received.
- **AI:** reply classification, tone-appropriate drafting, extraction of remittance details. **Human:** approves first-touch templates and every dispute resolution; owner calls for top accounts.
- **MVP:** 2–3 weeks on C1's connector *(estimate)*.
- **Pricing:** $1,000 setup plus **$300–$600/mo** *(estimate)*.
  - Anchors: Chaser $259–$1,169/mo ([Toolradar](https://toolradar.com/tools/chaser)); Paidnice from roughly $9–69/mo (listings conflict; [Capterra](https://www.capterra.co.uk/software/254868/paidnice)); Upflow quote-based.
  - QuickBooks' own Payments Agent covers reminders for QBO users ([CPA Practice Advisor](https://www.cpapracticeadvisor.com/2025/06/27/intuit-rolls-out-ai-agents-for-quickbooks/163868/)).
  - So C2 is **not a standalone wedge**. Sell it as a bundle add-on, and lean on Desktop and Acumatica users, where Intuit's QBO agents don't reach.
- **ROI model (illustrative):** $10M revenue → about $27.4k of sales per day. Cutting DSO by 5 days frees about **$137k** of cash; at an 8% cost of capital that's about $11k/yr, plus reduced write-offs. *All assumptions.*
- **Metrics:** DSO, % of AR over 60 days, dispute cycle time, AR clerk hours per week.

---

### C4: Vendor-invoice 3-way match (deprioritized)

The pain is real: Ardent puts average AP processing at $12.42 per invoice vs $2.65 best-in-class. But the space is commoditizing:
- Ramp Bill Pay is free or low-cost at the core, with 3-way match on its Plus tier ([Ramp support](https://support.ramp.com/3-way-match-with-ramp-procurement)).
- BILL is about $45–89/user/mo ([Corpay](https://www.corpay.com/resources/blog/bill-com-pricing)).
- Acumatica has native AP document recognition ([SVA](https://consulting.sva.com/insights/whats-new-in-acumatica-2026-r1-ai-automation-finance-crm-manufacturing-and-distribution-updates)).
- NetSuite has Intelligent Bill Capture ([Houseblend](https://www.houseblend.io/articles/en/netsuite-document-ai-extraction-factures)).

Offer it only as a cheap add-on for invoice-price-variance alerts, which feed C3.

### Expansion offers (after C1 is live)

- **X1 CSR Inbox Agent.**
  - Answers "where's my order / did you get my PO / when will it ship" from ERP data. Drafts replies for CSR approval, and auto-sends for low-risk status replies once trusted.
  - About $300–500/mo *(estimate)*. Builds directly on C1's mailbox integration.
- **X2 Quote / RFQ Assistant.**
  - Turns RFQ emails and spreadsheets into draft quotes with substitutes and margin checks.
  - DSG's COO describes complex quotes taking "up to eight hours" ([DSG, Jul 2025](https://distributionstrategy.com/2025/07/beyond-the-spreadsheet-transforming-order-quote-processes/)).
  - Harder build: needs product knowledge and pricing rules. Proton.ai, Avent and Prokeep target it.
- **X3 Reorder suggestions.** Min/max recalculation and purchase suggestions from sales history. Netstock (quote-based, Acumatica connector; [ERP Research](https://erpresearch.com/erp-add-ons/demand-planning/netstock)) and Inventory Planner exist. A light version is fine for QuickBooks shops.
- **X4 Rebate Tracker.** Parses buying-group and supplier rebate programs and reconciles them against purchases. Enable's survey says 52% believe they're missing rebates (vendor). Relevant because the beachhead *is* buying-group members.

---

## 5. Competition

### 5.1 Order intake / order entry

| Vendor | Target and positioning | Pricing (public?) | Likely to move down-market within ~12 months? |
|---|---|---|---|
| **Conexiom (incl. Relay, launched 2 Sep 2026)** | Manufacturers and distributors; 40 ERPs; 600+ customers; Relay handles email threads, spreadsheets, handwriting, images, texts ([IT Brief](https://itbrief.co.uk/story/conexiom-launches-ai-native-relay-for-order-automation)) | Quote-based; setup fees ([ERP Research](https://erpresearch.com/erp-add-ons/distribution/conexiom)) | Possible through ERP partnerships. A vendor guide claims an Epicor partnership (Jul 2026, **unverified**; [Airdev](https://www.airdev.co/erp/prophet-21/ai)). QuickBooks tier unlikely |
| **Endeavor AI** | Order entry plus voice; large named customers; $7M seed (Oct 2024) ([CB Insights](https://www.cbinsights.com/company/endeavor-6/financials)) | Custom | Medium. Markets through associations (NFPA, ISA) |
| **Avent** (YC S25) | Industrial distributors and manufacturers; quotes and order entry; 5-person team | Not public | Medium. Could chase small industrial shops |
| **Proton.ai** (order and quote entry GA 21 Jul 2026) | Distributors; bundled with its CRM/PIM | Not public | Low–medium (suite sale) |
| **Prokeep** (Feb 2026) | MEP on Eclipse/P21/Infor; "accessible… under $25 million" | Not public | Already small-firm in MEP. Low threat outside MEP unless it adds QuickBooks |
| **Pepper** ($50M Series C, announced Feb 20, 2026) | Foodservice plus **jan-san case studies**; Order Agent; 500+ distributors | Annual contracts, size-based | **High threat in jan-san.** Watch for QuickBooks support |
| **Choco** | Foodservice OrderAgent | Not public | Low outside food |
| **WizCommerce** ($8M Series A, Aug 2025) | B2B wholesale sales app plus AI order entry; heavy QuickBooks content marketing | ~$500/mo (third-party) | **High threat on the QuickBooks tier** |
| **Y Meadows** | Mid-market and enterprise | Usage-based, quote | Low |
| **Orderwerks** | B2B portal syncing to QuickBooks (changes customer behavior) | $60/user/mo | Different approach (portal, not inbox) |
| **ERP marketplace add-ons** | Acumatica: IIG PO Recognition ([Marketplace](https://www.acumatica.com/acumatica-marketplace/information-integration-group-po-recognition-pdf-extract)), Artsyl OrderAction ([Marketplace](https://www.acumatica.com/acumatica-marketplace/artsyl-sales-order-automation/)), UnForm. NetSuite: Anchor Group SO Automation ([Anchor](https://www.anchorgroup.tech/products/netsuite-sales-order-automation-app)), Airbricks OrderPilot | Mostly not public | Already present on Acumatica and NetSuite, mostly OCR/template tools. An LLM-native, service-heavy offer can beat them on messy formats |
| **Generic extraction** (Lido, Parseur, Nanonets) | DIY-ers | From ~$29/mo; Parseur free 20 pages/mo ([Parseur](https://parseur.com/compare-to/parsio-alternative)) | Already cheap, but no ERP matching, price/UOM logic or review workflow |
| **Intuit** | QBO sales orders exist on Plus/Advanced (UI). Intuit Enterprise Suite added sales-order upgrades in 2026 ([Insightful Accountant](https://blog.insightfulaccountant.com/the-erp-update-has-the-intuit-enterprise-suite-spring-2026-rollout)). QBO AI agents focus on bookkeeping, payments and finance | Bundled | **Native AI email-PO intake: not found.** It's the biggest long-run risk on QBO; less so on Desktop |
| **ERP-native AI** | Acumatica 2026 R1: AP recognition and AI Studio; **no native SO capture found**. NetSuite: Bill Capture (AP only). Epicor Prism: cloud-only per a vendor guide | Bundled | Medium over 12–24 months, starting with AP. Order intake later |

### 5.2 Adjacent offers
- **AR:** Chaser, Upflow, Paidnice, QuickBooks Payments Agent.
- **AP:** Ramp, BILL, Stampli, plus native capture in Acumatica and NetSuite.
- **Inventory:** Netstock, Inventory Planner (Sage), Fishbowl.
- **Rebates:** Enable.
- **Pricing:** Intuilize, Zilliant, Vendavo.

### 5.3 Integration reality check (verify on day 1)
- **QBO.**
  - Intuit staff said in Dec 2024 and Jun 2025 that sales orders are available on QBO Plus and Advanced. Users reported layout incompatibilities ([thread](https://quickbooks.intuit.com/learn-support/en-us/other-questions/quickbooks-online-sales-orders/00/1515566)).
  - I could **not** confirm a SalesOrder entity in the QBO Accounting API. Intuit says API entities mirror UI forms ([Intuit](https://developer.intuit.com/app/developer/qbo/docs/learn/explore-the-quickbooks-online-api)).
  - **Fallback:** write an **Estimate**, which is in the API, or a draft Invoice.
- **QuickBooks Desktop Enterprise.** `SalesOrderAdd` is supported by the SDK on Premier and above ([Intuit SDK](https://developer.intuit.com/app/developer/qbdesktop/docs/api-reference/qbdesktop/salesorderadd)) and by Conductor ($49/file/mo).
- **Acumatica.** The REST payload can vary by tenant customizations and endpoint version, so pin versions and test per client ([Acumatica blog](https://www.acumatica.com/blog/acumatica-web-services-rest-api-odata-and-integration-best-practices/)).
- **NetSuite.** Concurrency is shared across all integrations, so serialize writes and back off on limit errors.

### 5.4 Where a solo builder's edge holds, and where it breaks
- **Holds:**
  - QuickBooks Desktop Enterprise and QBO distributors that sales-led vendors deprioritize.
  - Messy, customer-specific formats where hands-on setup of cross-refs and UOM rules is the real work.
  - **Backtesting against the client's own history before go-live** (a trust builder few vendors offer to small accounts).
  - Bundling order, margin and cash in one relationship.
  - Month-to-month terms.
  - Regional or buying-group relationships.
- **Breaks:**
  - Distributors above ~$50M on P21 or Eclipse.
  - Foodservice.
  - Buyers requiring SOC 2.
  - If WizCommerce or Pepper ship a polished, self-serve QuickBooks integration at ≤$500/mo. If that happens, compete on service and on the C3/C2 bundle, or move to the Acumatica tier.

---

## 6. Risks and de-risking

| Risk | Failure mode | Mitigation |
|---|---|---|
| **Extraction accuracy** | Wrong SKU, quantity or UOM (case vs each) | Backtest on 100–200 historical orders before selling. Per-field confidence scores. Cross-ref first, AI second. Quantity anomaly check against the customer's history ("usually orders 4 cases, this says 40"). UOM rules per customer |
| **Wrong order shipped** | Customer gets the wrong goods; credit memo plus freight; trust lost | Shadow mode for 2 weeks, then approve-every-order, then approve-exceptions-only after field accuracy ≥99% for 4 weeks *(threshold is a judgment call)*. Never auto-release orders over a $ threshold or for new customers. Full audit log |
| **Price errors** | Wrong contract price written | Price always comes from the ERP price level / contract; never from the PO text. A PO price that differs from the ERP price becomes an exception |
| **Integration write-back** | QBO API gap; Acumatica customizations; NetSuite concurrency; Desktop machine offline | Day-1 sandbox test per ERP. Estimate fallback on QBO. Conductor for Desktop. Idempotency keys to prevent duplicate orders. Retry queue |
| **Email access / security** | Owner refuses mailbox access | Dedicated orders@ mailbox or forwarding rule only. Least-privilege OAuth scopes. Data stays in their tenant where possible. NDA plus a security one-pager. No SOC 2 at this tier *(judgment)* |
| **Buyer conservatism** | "Our CSRs have done it this way 20 years"; fear of layoffs | Pitch it as capacity and growth ("no new hire next year"). Make CSRs the reviewers and champions. Start with the 3 worst formats only |
| **Solo-builder dependence** | "What if you get hit by a bus?" | Simple, documented architecture. Client owns its data and cross-ref tables (exportable). Code escrow on request |
| **Funded competitors move down** | Pepper or WizCommerce add QuickBooks plus cheap self-serve | Bundle C1, C3 and C2. Go deep on the Desktop/Acumatica tier. Buying-group relationships |
| **LLM / model drift** | Accuracy regression after a model or prompt change | Golden-set regression tests before every deployment. Pin model versions |

---

## 7. Discovery-call kit

**Volume and channels**
1. How many customer orders do you enter on a typical day? How many people touch order entry?
2. What % arrive by email attachment, email body, phone, fax, text/photo, portal or EDI? Can you forward me 20 recent ones?
3. Which 10 customers send the most orders, and do they use their own part numbers?

**Time and errors**
4. How long does an average emailed order take to enter, and a bad one? (Offer to time 10.)
5. In the last 6 months, how many credit memos or returns came from entry mistakes (wrong item, qty, UOM, ship-to)? What does one cost you, including freight?
6. How fast do customers get an order confirmation today? Do you lose orders to slow response?

**System**
7. Which ERP/version (QBDT Enterprise, QBO tier, Acumatica, NetSuite)? Any add-ons (Fishbowl, Acctivate)? Who administers it?
8. Is your item master clean (UOMs, customer price levels, cross-refs)? Where do contract prices live?

**Money and margin**
9. How many supplier price-increase notices did you get in the last 12 months? How long from notice to updating sell prices? Who does it?
10. What's your DSO, and how much AR is over 60 days? Who chases it, and how?

**Buying behavior**
11. Have you looked at or tried any order automation (Conexiom, Pepper, WizCommerce, OCR tools)? What stopped you?
12. If one CSR's entry work disappeared, would you redeploy them (sales, service) or not backfill a vacancy?
13. Who besides you would need to say yes? What would make you say no?
14. Would you pay $750–1,500 for a 1-week audit that shows exact hours and accuracy on *your* orders, credited to setup?
15. If the audit shows payback within 6 months, is $750–1,500/month in budget this quarter?

**Kill criteria (per prospect):** disqualify any prospect with:
- fewer than 25 emailed/PDF orders a day;
- an ERP you can't write to;
- no named owner/decider in the room;
- or an unwillingness to share 20 sample orders.

**Kill criteria (for the niche, after 30–45 days):**
- Fewer than 8 discovery calls from about 100 targeted outreaches.
- Fewer than 2 paid audits.
- Backtest line-level accuracy below 95% after tuning, on 2+ prospects.
- No prospect agrees to ≥$500/mo.
- Pepper or WizCommerce launches a QuickBooks-native, ≤$500/mo self-serve equivalent that prospects already use.

---

## 8. Recommendation

**Flagship: the PO-to-Order Agent for QuickBooks Desktop Enterprise, QBO and Acumatica distributors, sold through a paid audit and expanded with the Margin Guard.**

**One-paragraph pitch (to an owner):**
> "Your CSRs are re-typing orders your customers already typed. I connect to your orders@ inbox and to QuickBooks or Acumatica, read every emailed PO (PDFs, spreadsheets, even the messy ones), match your customers' part numbers and units to your items, check price and stock, and drop a ready-to-approve order in your system. Your team clicks approve instead of keying. Before you commit, I'll run it on 200 of your past orders and show you exactly how accurate it is and how many hours it saves. Then we start in shadow mode, so nothing touches your ERP until you trust it. Most of the setup is building your customer cross-references, which you keep. No new software for your customers, no long contract."

**30-day launch plan**
- **Days 1–7: build and test the core.**
  - Ingestion (Gmail/Graph), extraction with JSON schema, cross-ref plus embedding matcher, review UI.
  - Conductor sandbox (QuickBooks Desktop `SalesOrderAdd`) and a QBO sandbox. Verify the QBO SalesOrder API on day 1; fall back to Estimate.
  - Build a synthetic golden set of 50 POs in varied layouts.
  - Draft the audit report template and the security one-pager.
- **Days 4–10: build the list and start outreach.**
  - Target list of about 100: AFFLINK and Triple S member distributors in 2–3 regions (public member/locator pages), ISSA distributor members, QuickBooks ProAdvisors and Acumatica VARs with distribution clients (as referral partners).
  - Outreach angle: "forward me 20 of your messiest POs; I'll show you what the agent does with them in 48 hours" (free mini-demo). Then offer the paid audit.
- **Days 10–20: discovery and audits.**
  - 10+ discovery calls using §7.
  - Run 2–3 audits (first one discounted or free in exchange for a case study). Include the backtest on their history.
  - Pitch AFFLINK or Triple S on a member webinar ("Tariffs, margin and the order desk: what AI actually does for a $10M distributor"). It doubles as Margin Guard lead-gen.
- **Days 20–30: convert and launch.**
  - Convert 1–2 audits into **founding pilots**: $3,000 setup (audit fee credited) plus $750/mo, 3-month pilot, shadow mode, then approve mode.
  - Measure touchless %, minutes per order and errors weekly.
  - Offer the Margin Guard "tariff repricing sprint" as a second paid project to pilot clients.

---

## 9. Shared building blocks with the construction track

| Block | Distributor use | Construction use (other agent) |
|---|---|---|
| Document extraction (LLM + JSON schema + golden-set eval harness) | Customer POs, supplier price files, vendor invoices | Sub invoices, pay apps (G702/G703), lien waivers, COIs, receipts |
| QuickBooks connectors (QBO OAuth app; Desktop via Conductor at $49/file/mo) | Sales orders/estimates, items, price levels, AR | Job costing, bills, WIP inputs |
| Entity matcher (exact cross-ref → embedding/fuzzy → human) | Customer part # → SKU; supplier part # → SKU | Cost line → job/cost code; vendor → subcontract |
| Human review queue with confidence scores, reason codes and audit log | Order approval, price-change approval | Bill coding approval, pay-gating on compliance |
| Email ingestion and outbound "chaser" agent | Order acks, AR dunning, customer price notices | Sub document chasing, PM cost-to-complete nudges |
| Cash forecast / dashboard module | DSO, weekly cash, margin exposure | 13-week contractor cash forecast, WIP dashboard |
| Paid-audit / backtest playbook | Order desk audit | "WIP Health Check" |

**Practical implication:** build the extraction, connector and review-queue core once, as a reusable internal platform. Both verticals then become configuration plus domain rules on top of it.

---

## Sources (key)
- BLS OEWS order clerks (May 2023): https://www.bls.gov/oes/2023/may/oes434151.htm
- APQC cost per sales order: https://www.apqc.org/resources/benchmarking/open-standards-benchmarking/measures/total-cost-perform-process-manage-11
- APQC 2016 sales order processing (Esker-hosted): https://cloud.esker.com/fm/others/K03319_Sales%20Order%20Processing_2016_Esker%203.pdf
- DSG State of AI in Distribution (Feb 2026): https://distributionstrategy.com/2026/02/distributors-reach-an-ai-inflection-point/
- DSG 2016 ordering channels: https://distributionstrategy.com/2016/10/the-electronic-postman-always-rings-much-more-than-twice/
- MDM/NAW AI study: https://www.mdm.com/webinar-where-400-distribution-leaders-are-investing-in-ai
- ASA surveys: https://www.asa.net/News/News/surveys-reveal-gap-between-ai-ambition-and-operational-reality-in-distribution
- Randstad posting: https://www.randstad.com/jobs/customer-serviceorder-desk_scarborough_47415143/
- Acumatica community thread: https://community.acumatica.com/develop-integrations-with-web-services-apis-289/ocr-for-automating-the-sales-order-raising-process-i-e-email-pdf-s-30260
- Intuit community (sales orders): https://quickbooks.intuit.com/community/account-management-7/when-will-sales-orders-be-an-available-option-76581 ; https://quickbooks.intuit.com/learn-support/en-us/other-questions/quickbooks-online-sales-orders/00/1515566
- NAW–MDM tariff research: https://www.mdm.com/news/research/economic-trends/new-naw-mdm-research-shows-tariffs-growing-impact-on-supply-chain/
- Intuilize margin-erosion claim (PHCP Pros): https://www.phcppros.com/articles/21838-beyond-price-hikes-strategic-approaches-to-managing-rising-tariffs-in-wholesale-distribution
- Intuit Late Payments 2025: https://quickbooks.intuit.com/r/small-business-data/small-business-late-payments-report-2025/
- Enable rebates (MDM): https://www.mdm.com/news/operations/finance/rebates-half-of-distributors-say-theyre-not-getting-what-theyve-earned/
- Ardent ePayables 2025 summary: https://tradeshift.com/state-of-epayables-2025-report/
- Conexiom Relay: https://itbrief.co.uk/story/conexiom-launches-ai-native-relay-for-order-automation
- Prokeep (HVACR Trends): https://hvacrtrends.com/prokeep-distributor-order-automation-ai-quoting/
- Pepper (AgFunderNews): https://agfundernews.com/inside-peppers-push-to-digitize-foodservices-long-tail-armed-with-50m-and-agentic-ai
- Pepper jan-san ERP post: https://www.usepepper.com/post/best-erp-for-jan-san-distribution-2025-solutions-features
- Proton.ai launch: https://distributionstrategy.com/2026/07/proton-ai-launches-ai-platform-to-automate-order-and-quote-entry-for-distributors/
- Avent (YC): https://www.ycombinator.com/companies/avent
- WizCommerce Series A: https://z47.com/news/z47-backed-wizcommerce-raises-8m-series-a-led-by-peak-xv-partners
- Conductor pricing FAQ: https://docs.conductor.is/faq
- Intuit API pricing summary: https://www.apideck.com/blog/quickbooks-api-pricing-and-the-intuit-app-partner-program
- Acumatica 2026 R1 summary: https://consulting.sva.com/insights/whats-new-in-acumatica-2026-r1-ai-automation-finance-crm-manufacturing-and-distribution-updates
- AFFLINK reach (ISSA): https://www.issa.com/industry-news/afflink-partners-with-american-office-products-distributors/
- Chaser pricing: https://toolradar.com/tools/chaser
- Orderwerks pricing: https://orderwerks.com/pricing
- Lido pricing: https://help.lido.app/en/article/pricing-plans-and-page-allowance-15z9f74/
