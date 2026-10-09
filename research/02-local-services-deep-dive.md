# 02 — Local & Service-Based SMBs: Deep Dive (Opus A)

Date: 2026-10-09 · Lane: local and service-based SMBs (trades, medical/dental, auto, salons/fitness, restaurants, construction subs, cleaning).

## How to read this report

- **Evidence quality warning.** Reddit could not be fetched or indexed from this environment (reddit.com and old.reddit.com both blocked; `site:reddit.com` searches returned nothing). Several forums (Jobber Community, Mike Holt, Capterra) returned HTTP 403 on direct fetch. Owner quotes below come from search-engine excerpts of those pages. Each one is labelled and linked so you can check it. **No Reddit quotes are included; I found no Reddit data, and I did not make any up.**
- Most market statistics in this space come from **vendors selling the fix**. I mark them `[vendor]`. Independent or primary sources (BLS, ADA, AGC, FCC, CAQH, incumbent docs) are marked `[primary]`.
- Time-to-MVP and pricing recommendations are **my estimates**. Competitor price points are cited.

---

## 1. Shortlist (8 niches) and triage

| # | Niche | Felt pain (evidence) | Saturation for AI | Regulatory / integration friction | Verdict |
|---|---|---|---|---|---|
| 1 | **Home-service trades (HVAC/plumbing/electrical/landscaping, 2–20 trucks)** | Missed calls (CallRail 2025: 14% missed in home services; Invoca: a person answered only 52% of calls) ([summary](https://www.usecarly.com/blog/missed-call-statistics/), [ainora](https://ainora.lt/blog/hvac-service-call-statistics-2026)); unsold estimates; thin margins (median HVAC net 5.8% per ACCA 2024, as cited by [PipelineOn](https://pipelineon.com/blog/how-to-price-home-service-jobs-profitably/)) | **Very high** for phone AI | TCPA/10DLC for SMS/voice; ServiceTitan API gated, HCP API is MAX-plan only, Jobber API open | **Deep dive (A)**, but avoid the receptionist |
| 2 | **Dental practices (1–5 locations)** | ADA: 55.3% of dentists list insurance issues and 54.2% list staffing among their top-3 2026 challenges ([via Stealth Agents summary of ADA HPI](https://stealthagents.com/research/dental-insurance-verification-workload-statistics-2026)); unscheduled treatment | High (Pearl, Overjet, VideaHealth, Weave, Arini, NexHealth) | **HIPAA/BAA**; Dentrix gated behind HS1 API Exchange | **Deep dive (B)** |
| 3 | **Commercial specialty subcontractors (electrical, mechanical, drywall, glazing, etc., $5–50M)** | AGC 2025: 77% of firms hiring estimators say the roles are hard to fill ([Construction Executive](https://constructionexec.com/article/the-5-problem-what-separates-winning-bidders-from-everyone-else/)); bid-invite inbox overload | **Low–moderate** (tools mostly target GCs) | None comparable to HIPAA/TCPA; inputs are email + PDFs | **Deep dive (C), my top pick** |
| 4 | **Independent auto repair** | Declined-service leakage, phones during busy bays ([Numa](https://www.numa.com/blog/declined-service-gap-editorial) [vendor]) | Moderate–high (Podium, Numa, AgentZap, Marchex) | Tekmetric API partner-gated with a 2–3 week review; Shopmonkey API more open ([Supergood](https://supergood.ai/api-report-card/tekmetric)) | **Short deep dive (D)** |
| 5 | Roofing / storm restoration (insurance supplements) | Supplements reportedly recover 20–40% on top of the first estimate ([PipelineOn citing IA Solutions](https://pipelineon.com/blog/roofing-pricing-guide/) [vendor]) | Moderate | **High legal risk**: unlicensed public adjusting (TX Supreme Court June 2024; Iowa consent orders) ([Insurance Journal](https://www.insurancejournal.com/news/southeast/2024/06/11/778845.htm), [Corridor Business](https://corridorbusiness.com/roofing-company-reaches-consent-order-with-iowa-insurance-division-over-alleged-unlicensed-public-adjusting-practices/)); needs Xactimate expertise | Avoid as a first niche |
| 6 | Restaurants (invoice → food-cost) | Fits a finance-tool builder | Entrenched: MarginEdge ~$300–350/mo/location ([PricingSaaS](https://pricingsaas.com/companies/marginedge)), xtraCHEF by Toast from $149 ([Capterra](https://capterra.com/p/165935/xtraCHEF/)) | Low regulatory risk, but thin margins and high churn | Pass |
| 7 | Med spas / aesthetics | Lead response, consult no-shows (20–30% claimed, unsourced) ([vendor blogs](https://medspagrowthcompany.com/guides/med-spa-lead-follow-up-speed-to-lead)) | **Very high**: GoHighLevel agencies everywhere | HIPAA-adjacent; TCPA | Pass |
| 8 | Vet / physical therapy | PT plan-of-care dropout widely reported (e.g., 7 in 10 don't complete authorized visits per [Medbridge](https://www.medbridge.com/blog/patient-retention-in-physical-therapy-why-it-matters-and-how-to-improve-it)); vet scribes | AI scribes crowded (ScribVet $97/user/mo, [Capterra](https://www.capterra.com/p/10027580/ScribVet/)) | HIPAA for PT; EMR integrations | Pass for now; PT retention is a reasonable backup |

---

## 2. Cross-cutting facts that change the playbook

1. **Generic AI receptionists are now a built-in feature of the incumbent software.** Jobber made "Receptionist" generally available in 2025 and reported 200k+ conversations handled ([CustomerThink](https://customerthink.com/?p=1070404)). It is reported as a $99/mo add-on on Grow and included in Plus ([Stork](https://www.stork.ai/en/jobber-ai-receptionist-2), third-party). Housecall Pro sells "CSR AI" as a quote-only add-on ([Beside](https://www.beside.com/blog/housecall-pro-ai-phone-answering)). Avoca, a ServiceTitan-certified AI front office, reportedly raised $125M at a $1B valuation ([ai2.work](https://ai2.work/blog/avoca-hits-1b-valuation-with-125m-raise-to-bring-ai-to-home-services)). Sameday AI lists $249/$499 tiers ([Stork compare](https://www.stork.ai/compare/sameday-ai-vs-avoca-ai)). Consumer AI receptionists start at $29–49/mo. **A solo builder cannot win a feature-for-feature fight here.**
2. **Owners' real experience with AI phone agents is mixed.** One tree-service owner on Jobber Community, as excerpted by search, called Jobber's AI receptionist "at best average; and often annoying" and said "We turned it off after trying it quite a bit." Other owners in the same threads said callers hung up once they heard it was AI, and most used it only after hours ([Jobber Community thread](https://community.getjobber.com/discussions/operations-forum/what-do-customers-think-about-jobbers-ai-receptionist/9584); direct fetch was blocked, so quotes come from the search excerpt).
3. **AI follows the native software.** ServiceTitan's Dec-2025 survey of 1,000+ contractors found 46% using or experimenting with AI, and 59% of AI users adopt the AI already built into their software ([ServiceTitan press](https://www.servicetitan.com/press/ai-in-the-skilled-trades-report-2025)). Housecall Pro's June-2025 survey of 400+ contractors found ~40% actively using AI, mostly for admin work ([Contractor Mag](https://www.contractormag.com/technology/article/55294441/more-than-70-of-home-service-pros-use-ai-to-cut-admin-work-but-not-field-jobs)). **Implication:** sell what the native tools don't do, or sell implementation of what they do.
4. **Outbound AI calls and texts carry legal requirements.** The FCC's Feb-2024 declaratory ruling puts AI-generated voices under the TCPA "artificial or prerecorded voice" rules, so prior express consent is needed, and written consent for marketing ([Hunton](https://huntonak.com/privacy-and-information-security-law/fcc-issues-declaratory-ruling-that-tcpa-applies-to-ai-generated-voice-calls)). Unregistered A2P 10DLC SMS is blocked by US carriers as of Feb 2025 ([Textbolt](https://textbolt.com/blog/10dlc-compliance/), [Twilio](https://pages.twilio.com/10DLC-HelpArticles-WW)). Every follow-up or reactivation offer needs 10DLC registration and consent hygiene built in.
5. **HIPAA is workable but adds overhead.** OpenAI offers BAAs on API orgs with Modified Retention ([OpenAI Help](https://help.openai.com/en/articles/20001069-hipaa-eligible-products-and-functionality)). Anthropic offers HIPAA-ready API orgs via a BAA through sales ([Anthropic docs](https://platform.claude.com/docs/build-with-claude/api-and-data-retention)). You also need BAAs with Twilio and your host, plus audit logging. Those are your responsibility.

---

## 3. Deep dive A — Home-service trades (Jobber / Housecall Pro tier, 2–20 trucks)

### Actively felt problems (with evidence)
- **Missed and unanswered calls.** CallRail 2025: home services miss 14% of calls. Invoca's 2026 benchmark: a person answered 52% of home-services calls ([summarized here](https://www.usecarly.com/blog/missed-call-statistics/), [ainora](https://ainora.lt/blog/hvac-service-call-statistics-2026)). Real, but this is the crowded play (see §2).
- **Unsold estimates and ghosting.** On the Mike Holt electrical forum, one electrician reported roughly 30% of estimates become paying jobs, and others recommended pre-qualifying budget before free estimates ([thread](https://forums.mikeholt.com/threads/estimate-follow-up.3748/latest), search excerpt). Jobber Community owners describe hand-run cadences such as "follow up the next day… add them to my follow-up list" ([thread](https://community.getjobber.com/discussions/operations-forum/why-do-clients-disappear-after-asking-for-a-quote/14304), search excerpt). Vendor claims: contractors stop at 1.8 touches ([PipelineOn](https://pipelineon.com/blog/drip-campaigns-after-estimate/) [vendor]); Hatch case study of $260K recovered from open estimates for one HVAC company ([Hatch](https://www.usehatchapp.com/case-studies/rescue-air) [vendor]).
- **Maintenance-agreement churn.** Renewal estimates range from 65–75% average ([Oxmaint](https://oxmaint.com/industries/hvac/recurring-revenue-tracking-hvac-service-businesses) [vendor]) down to 30–50% annual churn in MeasureQuick's interviews ([MeasureQuick](https://measurequick.com/maintenance-the-leaky-bucket/) [vendor]). The only named census is the 2016 ACCA study ([Webtonic](https://www.webtonic.io/blog/hvac-lifecycle-and-retention-marketing-statistics/)).
- **Thin margins and weak job costing.** Median HVAC net 5.8% vs top quartile 13.2% (ACCA 2024 via [PipelineOn](https://pipelineon.com/blog/how-to-price-home-service-jobs-profitably/)). Intuit survey: 50% of contractors omitted general conditions from estimates ([PM Mag](https://www.pmmag.com/articles/86408-contractors-risking-business-success-by-undercharging), undated).
- **Incumbent cost and lock-in at the top end.** ServiceTitan third-party estimates run ~$245–500/tech/mo, with $5k–50k+ implementation and multi-year contracts ([OneCrew](https://www.getonecrew.com/post/servicetitan-pricing), [CostBench](https://costbench.com/software/field-service-management/servicetitan/)). A G2 small-business reviewer called it the priciest FSM, "double to eight times" competitors, and overkill for shops needing only dispatch (paraphrased from [G2 excerpt](https://g2.com/products/servicetitan/reviews/servicetitan-review-8907029)). A Capterra reviewer complained of being locked into a two-year contract ([Capterra p.7](https://capterra.com/p/150053/ServiceTitan/reviews/?page=7)).

### What they use and pay
- FSM: Jobber (Connect/Grow/Plus; Plus reported at $599/mo), Housecall Pro ($59/$149/$299 annual base, per [ContractorToolStack](https://contractortoolstack.com/software/housecall-pro/pricing/)), ServiceTitan (see above).
- Answering: live services $200–1,500/mo; AI receptionists $29–499/mo; Avoca reportedly $1–3k/mo ([Macha](https://www.getmacha.com/blog/avoca-ai-pricing-explained), third-party).

### Where incumbents leave gaps
- **Jobber already ships quote follow-ups (Connect+) and job costing (Grow+)** ([Jobber help](https://help.getjobber.com/en/articles/automations/), [Community](https://community.getjobber.com/discussions/service-based-skilled-trades/what-do-solo-handyman-businesses-use-to-automate-quote-follow-ups-and-track-mate/14373)). It claims a 57% lift in quotes won (company figure). Selling "quote follow-up" to a Jobber Grow user is selling something they already own.
- Real gaps: (1) **owners who own the features but never configured them**; (2) **cross-system truth**: ad spend (Google LSA, Angi) → calls → booked → sold → cash collected, which FSMs report poorly across tools; (3) **personalized, context-aware follow-up**: an AI writes from the tech's notes and photos instead of a template; (4) **dormant-customer and agreement reactivation** with segmentation.
- Integration: **Jobber GraphQL API is open with OAuth** ([Jobber dev](https://developer.getjobber.com/docs/using_jobbers_api/api_queries_and_mutations/)). **Housecall Pro's API and webhooks are MAX-plan only** ([HCP pricing FAQ](https://housecallpro.com/pricing/)). **ServiceTitan APIs require developer registration, and the marketplace requires an application-based paid partner program** ([ST App Marketplace guide](https://www.servicetitan.com/legal/app-marketplace-program-guide)).

### Offers
**A1. "Revenue Recovery Desk" for Jobber shops (AI estimate and reactivation engine + weekly owner report)**
- What: pulls open quotes, past clients, and lapsed visits from Jobber; an LLM drafts personalized SMS/email follow-ups from quote line items and job notes. The owner approves in a one-tap queue (Slack/SMS) for the first 30 days, then it runs autonomously. Includes a weekly "money left on the table" report.
- AI: drafting, objection classification of replies (price / timing / went elsewhere), routing hot replies to the owner.
- Stack: Jobber GraphQL + webhooks → Postgres/Supabase → LLM → Twilio (10DLC registered) / Postmark → Next.js dashboard. MVP ~3–4 weeks (estimate).
- Price: $750–1,500 setup + $400–600/mo, or a performance kicker. Anchors: Hatch, Sameday, and Podium charge $249–599/mo for adjacent tools (above). **ROI math (illustrative, not data):** 40 open quotes/mo × $1,200 avg × 10 extra points of close rate = ~$4,800/mo incremental revenue.
- Measured value: quotes recovered ($), reactivated agreements, response rate.
- Skeptic note: overlaps Jobber's native follow-ups. Differentiate on personalization, reactivation, and reporting, or this won't sell.

**A2. "Lead-to-Cash Dashboard" (finance-builder sweet spot)**
- What: one dashboard joining call tracking (CallRail), ad spend (Google Ads/LSA), FSM jobs/invoices, and QuickBooks. Shows cost per booked job, close rate by tech/CSR, and cash collected per channel. A monthly AI-written CFO-style memo explains what changed.
- Stack: API pulls + dbt-lite SQL + Metabase/Next.js + LLM narrative. MVP ~4 weeks.
- Price: $1,500 setup + $300–500/mo. Owners already pay ad agencies; this audits them.
- Skeptic note: lower urgency than "phones ringing". Best sold as a bundle with A1 or to shops spending $5k+/mo on ads.

**A3. Done-for-you FSM + AI implementation** (configure Jobber/HCP automations, AI receptionist after-hours only, pricebook cleanup): $2–5k project. Low defensibility, but it is a good wedge for A1/A2.

**Verdict on A:** big market and easy to reach, but the most crowded and partly commoditized by Jobber, HCP, and ServiceTitan themselves. Agency competition (GoHighLevel resellers) is intense.

---

## 4. Deep dive B — Dental practices (Open Dental first)

### Actively felt problems
- **Insurance work.** CAQH Index (2024, via aggregator): manual dental eligibility check ~12 min vs ~4 min fully electronic, with 1.2B dental verifications in 2023 ([Stealth Agents summary](https://stealthagents.com/research/dental-insurance-verification-workload-statistics-2026)). Weave survey (2022): 55% of offices spend 6+ hours/week verifying eligibility ([BusinessWire](https://www.businesswire.com/news/home/20220712005493/en)). ADA HPI: 55.3% name insurance among their top-3 2026 challenges.
- **Staffing.** 54.2% name staffing as a top-3 2026 challenge (ADA, same source). Dental receptionist mean wage was $20.41/hr in May 2023 ([BLS](https://www.bls.gov/oes/2023/may/oes434171.htm)).
- **Unscheduled treatment.** Henry Schein One benchmark: average case acceptance 46% vs 83% for top 10%, with "$1 to $1.5 million" of annual revenue left in unscheduled treatment for an average practice ([HS1](https://www.henryscheinone.com/insights/blogs/average-providers-are-losing-hundreds-of-thousands-in-unscheduled-treatment/) [vendor-benchmark]).
- Owner-voice note: I found **no retrievable Reddit or Dentaltown posts**. Job postings repeatedly require "PPO breakdowns and eligibility checks" ([CareerBuilder example](https://www.careerbuilder.com/job-details/front-desk-coordinator-naba-dental-memorial-area-houston-houston-tx--076a93be-eb18-42c0-a2d5-b0ced28ec29d)), which is indirect evidence that this is hard-to-staff work.

### What they pay today
- Outsourced verification: $6.50–8.25 per verification, $12.50 rush ([DentalBilling/eAssist](https://dentalbilling.com/pricing-dental-insurance-verification/)); eAssist tiers $250 (1–30/mo), $650 (31–75), $825 (76–100), plus $299 setup; Verifixed $5.99–11.99 ([AACA](https://www.aacaligners.com/member-deals/verifixed-llc)); offshore VAs $5–10/hr ([HelpSquad](https://helpsquad.com/healthcare/insurance-verification/)).
- AI receptionists: dental-specific $300–900/mo/location ([comparison](https://sagnikbhattacharya.com/blog/ai-receptionist-cost-dental-practice-2026)); Arini listed from $499 ([Capterra](https://www.capterra.com/p/10036210/Arini/)); Weave Pro from $199, with AI receptionist as a separate add-on ([Quo](https://www.quo.com/blog/weave-pricing/)).
- AI verification vendors are already well funded: VideaHealth AutoVerify (Jan 2026), Planet DDS AutoEligibility (Nov 2025), Pearl, Overjet, RevenueWell ([BusinessWire](https://www.businesswire.com/news/home/20260114241532/en), [BusinessWire](https://www.businesswire.com/news/home/20251118656411/en/Planet-DDS-Unveils-AutoEligibility-Bringing-Real-Time-Eligibility-Data-Directly-into-Denticon)).

### Integration reality
- **Open Dental:** developer key from Vendor Relations, per-office customer key, reported write tiers of ~$15–35/mo/location (unconfirmed on OD's site), and a local eConnector is required ([Supergood](https://supergood.ai/api-report-card/open-dental), [apis.io](https://apis.io/plans/opendental/opendental-plans-pricing/)). **Feasible for a solo builder.**
- **Dentrix/Eaglesoft:** Henry Schein One API Exchange requires vendor approval, a security review, and reportedly SOC 2 Type II. A third party claims ~$5k read + $5k write plus royalty (unverified) ([HS1 vendors page](https://www.henryscheinone.com/dental-solutions/api-exchange/api-exchange-vendors/), [Supergood](https://supergood.ai/api-report-card/dentrix)). **Not realistic as a starting point.**
- **Shortcut:** NexHealth Synchronizer unified API covering Dentrix, Open Dental, Eaglesoft and 12+ more. It advertises $0.10/call with 10k free calls/mo and a BAA ([Synchronizer pricing](https://synchronizer.nexhealth.com/pricing)).

### Offers
**B1. "Unscheduled Treatment Recovery" for Open Dental practices**
- What: nightly pull of treatment-planned but unscheduled procedures. An LLM writes patient-specific (plain-language) outreach referencing the procedure, estimated patient portion, and financing options. The front desk gets a ranked call list ("highest $ × likelihood") and a dashboard of $ recovered.
- Stack: Open Dental API (or NexHealth Synchronizer) → HIPAA-ready LLM org with BAA → Twilio with BAA → dashboard. MVP ~5–6 weeks including compliance work (estimate).
- Price: $1,000 setup + $500–800/mo per location, or 5–8% of recovered production. **ROI math:** if HS1's benchmark holds even partially, recovering 2% of $1M unscheduled is $20k/yr, which covers ~$6–9k/yr in fees ~2–3×.
- Competition: Weave, RevenueWell, Dental Intelligence, and NexHealth all do recall/treatment reminders. Differentiate with dollar-ranked worklists and AI-personalized messaging.

**B2. Hybrid "AI + human" verification service** (AI pulls portal/clearinghouse data and drafts the breakdown; an offshore VA QA's it)
- Price per verification at $5–7 (below eAssist/Verifixed), with gross margin from automation.
- Skeptic note: payer-portal automation hits MFA and ToS walls, and funded AI vendors are attacking this directly. **This is a service business, not a product moat.**

**B3. Dental AI receptionist:** **don't.** Weave, Arini, NexHealth, and others are entrenched, and they integrate with PMS systems you can't.

**Verdict on B:** strongest willingness-to-pay and ROI math in the lane. HIPAA overhead, the PMS gatekeeping, and VC-funded competitors make it a second-best start for a solo builder. B1 on Open Dental is the viable wedge.

---

## 5. Deep dive C — Commercial specialty subcontractors (TOP PICK)

Target: commercial electrical, mechanical/plumbing, fire protection, drywall/framing, glazing, roofing (commercial), and concrete subs with 1–5 estimators, ~$5–50M revenue, bidding GC work.

### Actively felt problems
- **Estimators are scarce and expensive.** AGC 2025 workforce survey (open-shop breakout; the $50–500M-firm breakout shows 75%): 77% of firms hiring estimating personnel said the positions were hard to fill ([Construction Executive](https://constructionexec.com/article/the-5-problem-what-separates-winning-bidders-from-everyone-else/)). BLS median cost-estimator wage was $77,070, and $79,130 in specialty trade contractors (May 2024) ([BLS OOH](https://www.bls.gov/ooh/business-and-financial/cost-estimators.htm)) `[primary]`.
- **Most bidding effort is wasted.** Public-work subs file ~7–11 bids per award, roughly a 9–14% hit rate ([Bridgit citing ENR](https://gobridgit.com/blog/how-to-bid-as-a-subcontractor/)). Only 6% of 2,000 surveyed contractors knew and tracked their hit ratio ([ENR](https://www.enr.com/articles/23952-bid-hit-ratios-provide-valuable-road-map?v=preview), undated). Most subs don't track it ([Autodesk](https://www.autodesk.com/blogs/construction/subcontractors-win-work)).
- **Inbox overload.** Subs describe irrelevant ITBs, duplicates, and out-of-state projects, with GCs "spam[ming] through bidding platforms" ([Downtobid](https://downtobid.com/blog/how-estimating-emails-kill-specialty-subs) [vendor]). A ContractorTalk thread compares BidMail vs ShareFile for managing bids ([ContractorTalk](https://www.contractortalk.com/threads/subcontractor-bid-preference-bidmail.178561/)). Autodesk reports US bidding rose 5% in 2024 ([Autodesk](https://www.autodesk.com/blogs/construction/subcontractors-win-work)).
- No quantified "hours spent triaging ITBs" figure was found. **No data found**; validate in discovery calls.

### What they use and pay
- BuildingConnected Bid Board Pro: ~$3,600–5,000/yr per company for 3–10 estimators ([Spendbase](https://www.spendbase.co/?p=37350), third-party); Capterra lists BuildingConnected from $3,600/yr ([Capterra](https://capterra.com/p/156791/BuildingConnected/)).
- Takeoff/estimating: PlanSwift, Accubid, Trimble, and similar. AI-spec tools are emerging: Nomic (custom, 500–2,000-page spec books) ([Nomic](https://www.nomic.ai/ai-for/preconstruction/specifications)), Scopebase $69/user/mo ([Capterra](https://www.capterra.com/p/10044818/Scopebase-ai/)), Downtobid (GC-side invites; subs free) ([Downtobid compare](https://downtobid.com/compare)).

### Where incumbents leave gaps
- Bid Board Pro organizes invites but doesn't **read the specs and tell you whether to bid**. GC-side AI (Downtobid) helps GCs send invites, not subs decide. Spec-reading AI exists mostly at enterprise or custom pricing. **The gap is a sub-sized, done-for-you "bid desk": triage + spec brief + win/loss analytics.**
- This is an LLM-native task: long-document reading, extraction, classification, and summarization with page citations. It is also B2B: **no HIPAA, no TCPA**, and no gated incumbent API needed (inputs are email + PDFs + planroom links).

### Offers
**C1. "AI Bid Desk" (flagship)**
- What it does: (1) watches the estimating inbox and BuildingConnected/PlanHub notification emails; (2) dedupes ITBs and extracts project, GC, due date, location, and trade packages; (3) pulls the relevant spec divisions (e.g., Div 26 for electrical) and produces a **1-page bid/no-bid brief with page citations**: scope inclusions/exclusions, alternates, bonding/insurance, liquidated damages, schedule, prevailing wage, and red-flag clauses; (4) scores fit against the sub's own rules (size, distance, GC history, margin history); (5) posts to a bid board dashboard.
- AI: PDF parsing + LLM extraction over spec books (text, not drawings); structured JSON schema; citation verification pass; GC-history scoring.
- Stack: Gmail/M365 API → object storage → PDF text extraction (pdfplumber/unstructured; OCR fallback) → Claude/GPT with long context → Postgres → Next.js board + Slack/Teams digest. MVP ~3–4 weeks for triage + brief (estimate).
- Price: $1,500 setup + $750–1,500/mo (by bid volume). **Justification:** comparable to 1–2 days/month of an estimator at ~$77–79k/yr median (≈$37–38/hr base, before burden). Bid Board Pro alone is ~$300–420/mo. **ROI math (illustrative):** at a ~10% hit rate, one extra won $250k job/yr at 10% margin is $25k of profit, more than the annual fee.
- Measured value: hours of triage saved per estimator per week; % of ITBs declined early; spec red flags caught; bids-per-estimator; hit rate over time.

**C2. "Win/Loss & Hit-Rate Analytics" (finance and dashboard strength)**
- Bid log auto-built from C1 plus award emails. Shows hit rate by GC, project type, size, and estimator; bid-day pricing vs award spread; and backlog/pipeline forecasting for the owner and bonding agent. An AI-written monthly memo covers which GCs to stop bidding.
- Price: included in C1 Pro tier, or $300–500/mo standalone. Low build risk.

**C3. Post-award document workflow** (submittal log auto-generated from spec sections, RFI drafting, change-order narrative drafts from field notes). Price $500–1,000/mo. Phase 2; Procore/Autodesk partially cover it for larger subs.

### Risks and skeptic notes for C
- **Accuracy liability:** a missed spec requirement can cost a job. Mitigate with page-cited outputs, "estimator verifies" positioning, and no takeoff/quantity claims. Drawing-based quantity takeoff by vision models is not reliable enough to sell; avoid it.
- **Domain learning curve:** the builder must learn CSI MasterFormat divisions and GC bid etiquette. Partner with one friendly estimator as a design partner.
- **Access:** planroom downloads sit behind logins. The MVP can rely on the sub's own downloads into a shared folder (no credential handling by you).
- **Market evidence is thinner on owner voice** (no forum quotes retrieved quantifying hours). The AGC shortage data and hit-rate data are solid; the triage-hours claim must be validated in discovery.
- Competition is emerging (Nomic, Scopebase, BuildingConnected AI features), but none is clearly positioned as a done-for-you sub-sized desk at this price point. Autodesk could add this; speed and service are the moat.

---

## 6. Short deep dive D — Independent auto repair

- Pain: declined services and phones during busy hours. Numa models 200 declined tickets/mo × 20% recovery × $450 RO = $18k/mo, but it is dealer-focused and the 20% is an uncited assumption ([Numa](https://www.numa.com/blog/declined-service-gap-editorial) [vendor]). Podium claims service centers miss 40% of calls (unsourced) ([Podium](https://automotive.podium.com/solutions/service)). Counterpoint: Shopmonkey's phone vendor notes that its customers "want a person on the phone, fast" ([Dialpad](https://www.dialpad.com/fr/customers/shopmonkey-rebuilt-support-from-the-ground-up-and-dialpad-made-every-call-count/)).
- Integration: Tekmetric partner-gated with a 2–3 week review; Shopmonkey REST API reportedly per-shop and more open ([Supergood Tekmetric](https://supergood.ai/api-report-card/tekmetric), [Supergood Shopmonkey](https://supergood.ai/api-report-card/shopmonkey)).
- Offer: **Declined-Work Recall** for Shopmonkey shops. Pull declined DVI items, then send an AI-personalized text with photo and price at 30/60/90 days. $500 setup + $300–400/mo. MVP ~3 weeks.
- Verdict: decent, but crowded by Podium/Numa/Marchex and dealer-oriented tools. A secondary niche.

---

## 7. Saturated or risky plays to avoid

- **Generic AI receptionist / chatbot** in any of these verticals: now native in Jobber/HCP/Weave, VC-backed (Avoca, Arini), $29–49/mo low end, and owners report hang-ups. Only defensible if bundled in a vertical workflow (e.g., after-hours triage that writes into Jobber plus a dispatcher escalation policy), never as the core product.
- **Roofing insurance supplements:** unlicensed-public-adjusting exposure (TX, IA, CO, AZ cases above) and Xactimate expertise required.
- **Med spa lead follow-up:** GoHighLevel agency saturation.
- **Dental verification as pure software:** funded AI vendors plus payer-portal ToS/MFA friction.
- **Restaurant invoice/food-cost:** MarginEdge/xtraCHEF entrenched; restaurant churn.

---

## 8. Top recommendation: AI Bid Desk for commercial specialty subcontractors

Why it ranks first in this lane:
1. **Verified, expensive bottleneck:** 77% of firms say estimator roles are hard to fill (AGC 2025), at a ~$79k median wage in specialty trades (BLS).
2. **Most effort is wasted and untracked:** ~9–14% public-bid hit rates; only 6% track hit ratio. Triage plus analytics directly addresses both.
3. **LLM-native work** (long spec documents → structured, cited briefs) that a solo builder can make reliable without vision-based takeoff.
4. **Low regulatory and integration friction:** no HIPAA, no TCPA/10DLC, no gated PMS/FSM API.
5. **Less saturated** than trades phones or dental front office, and it plays to the builder's dashboard and finance strengths (C2 analytics).
6. **Price headroom:** subs already pay ~$3.6–5k/yr for Bid Board Pro, and one extra won job dwarfs a $9–18k/yr fee.

Runner-up: **Dental B1 (Unscheduled Treatment Recovery on Open Dental)**. It has the best ROI math but carries HIPAA and competitive overhead. Third: **Home-services A1+A2 for Jobber shops**, which is easy to reach but crowded.

### First 30 days: landing the first 3 clients

**Week 1: Learn and build the demo asset**
- Pick one trade (electrical is the largest; Division 26 specs are well structured) and one metro.
- Download 5–10 public bid packages (public owner/agency bids, e.g., state DOT, school districts, municipal planrooms). Generate sample bid/no-bid briefs with page citations. This becomes the demo.
- Build MVP v0: folder drop → spec extraction → 1-page brief (PDF/Notion) + Airtable/Postgres bid log.

**Week 2: Outreach (target 40 conversations' worth of touches)**
- List 60–100 commercial electrical/mechanical subs in the metro from local ABC/AGC/NECA/MCAA chapter member directories and state contractor license lookups.
- Message the **chief estimator** (LinkedIn + email) with a concrete hook: "I ran your trade's spec section from [recent public bid in your city] through my tool; here's the 1-page brief. Was anything missed?" Attach the real brief.
- Attend one local ABC/AGC chapter event or estimator meetup.

**Week 3: Free pilots (paid conversion criteria set upfront)**
- Offer a 2-week pilot to 5 subs: they forward ITBs; you return briefs within 4 business hours. You stay human-in-the-loop on every brief (review and QA yourself), which also builds your domain knowledge.
- Agree on success metrics before starting: hours saved/week, ITBs declined early, and red flags caught. Price is pre-agreed: $1,500 setup waived for pilots and $750/mo founding rate, locked for 12 months.

**Week 4: Convert and productize**
- Convert 3 of 5 pilots to paid (founding rate). Ask each for one GC-side or peer-sub referral.
- Add C2 (hit-rate dashboard) as the retention hook: backfill their last 12 months of bids from email history.
- Write one case study with real numbers (hours saved, bids declined, red flags). That becomes the outreach asset for months 2–3 and the basis for raising price to $1,000–1,500/mo.

**Kill criteria (be honest by day 30):** if fewer than 2 of 5 pilots say the brief saved them more than 2 hours/week or caught a material issue, pivot to Dental B1 (Open Dental) using the same "pilot then convert" playbook.

---

## Appendix — Key sources
- CallRail/Invoca/411 Locals missed-call summaries: https://www.usecarly.com/blog/missed-call-statistics/ ; https://ainora.lt/blog/hvac-service-call-statistics-2026
- ServiceTitan pricing estimates: https://www.getonecrew.com/post/servicetitan-pricing ; https://costbench.com/software/field-service-management/servicetitan/
- ServiceTitan AI report (Dec 2025): https://www.servicetitan.com/press/ai-in-the-skilled-trades-report-2025
- Housecall Pro AI report (Jun 2025): https://www.contractormag.com/technology/article/55294441/more-than-70-of-home-service-pros-use-ai-to-cut-admin-work-but-not-field-jobs
- Jobber Receptionist: https://customerthink.com/?p=1070404 ; https://www.stork.ai/en/jobber-ai-receptionist-2 ; owner feedback: https://community.getjobber.com/discussions/operations-forum/what-do-customers-think-about-jobbers-ai-receptionist/9584
- Jobber quote follow-ups / API: https://help.getjobber.com/en/articles/automations/ ; https://developer.getjobber.com/docs/using_jobbers_api/api_queries_and_mutations/
- HCP API MAX-only: https://housecallpro.com/pricing/
- ServiceTitan marketplace: https://www.servicetitan.com/legal/app-marketplace-program-guide
- Avoca: https://ai2.work/blog/avoca-hits-1b-valuation-with-125m-raise-to-bring-ai-to-home-services ; https://www.getmacha.com/blog/avoca-ai-pricing-explained
- FCC AI voice TCPA ruling: https://huntonak.com/privacy-and-information-security-law/fcc-issues-declaratory-ruling-that-tcpa-applies-to-ai-generated-voice-calls
- 10DLC: https://textbolt.com/blog/10dlc-compliance/
- HIPAA/BAA: https://help.openai.com/en/articles/20001069-hipaa-eligible-products-and-functionality ; https://platform.claude.com/docs/build-with-claude/api-and-data-retention
- Dental: https://www.businesswire.com/news/home/20220712005493/en ; https://www.henryscheinone.com/insights/blogs/average-providers-are-losing-hundreds-of-thousands-in-unscheduled-treatment/ ; https://dentalbilling.com/pricing-dental-insurance-verification/ ; https://supergood.ai/api-report-card/open-dental ; https://www.henryscheinone.com/dental-solutions/api-exchange/api-exchange-vendors/ ; https://synchronizer.nexhealth.com/pricing
- Construction: https://constructionexec.com/article/the-5-problem-what-separates-winning-bidders-from-everyone-else/ ; https://www.bls.gov/ooh/business-and-financial/cost-estimators.htm ; https://gobridgit.com/blog/how-to-bid-as-a-subcontractor/ ; https://www.enr.com/articles/23952-bid-hit-ratios-provide-valuable-road-map?v=preview ; https://www.spendbase.co/?p=37350 ; https://downtobid.com/blog/how-estimating-emails-kill-specialty-subs
- Roofing UPA: https://www.insurancejournal.com/news/southeast/2024/06/11/778845.htm ; https://www.americanbar.org/groups/litigation/resources/newsletters/construction/limitations-on-contractors-advocating-insurance/
- Auto: https://www.numa.com/blog/declined-service-gap-editorial ; https://supergood.ai/api-report-card/tekmetric
