# 01 - Landscape Scan: AI Niches for a Solo Builder (as of 2026-10-09)

Method note: ~16 web searches. Almost all niche-level "pain" numbers come from VENDORS selling the fix (missed-call rates, ROI claims). I flag these as vendor claims. Where I found no number I say so. Scores are my judgment, not measured data.
Score key (1-5): Pain / WTP (willingness to pay) / Reach (ease of reaching buyers) / Build (solo feasibility) / Comp (5 = little competition) / Reg (5 = low regulatory risk).

## Cross-cutting facts
- Census BTOS: overall US business AI use ~17-20% (Dec 2025-May 2026); firms with <20 employees did not change significantly; <20% of firms with <=4 employees use AI. https://census.gov/library/stories/2026/05/ai-use-businesses.html  -> small-business demand is real but adoption is early; buyers need hand-holding (good for a services/implementation model).
- Accounting: Intuit 2026 survey (725 US pros): 88% use AI for a client service; but Financial Cents survey (486, Jul-Aug 2026): 20% of AI-using respondents report clear measurable ROI; no written AI policy is 87% in the body text (the cover says 90%). Intuit also finds the average firm uses 10 apps and only 41% say tools are fully integrated. https://www.accountingtoday.com/partnerinsights/article/intuit/intuits-2026-accountant-technology-survey-ai-fragmentation-and-the-future-of-the-profession ; https://financial-cents.com/?p=39931 (both fetched and verified)
- Pattern: "AI receptionist / missed-call recovery" is marketed to EVERY vertical (home services, dental, vet, auto, restaurants, salons, schools, venues). It is the most saturated pitch. The less-saturated, still-paid angle is back-office workflow automation tied to a system of record.

---
## 1. Home services / trades (HVAC, plumbing, electrical, roofing)
1. Workflows: missed/after-hours calls and slow lead response; quote/estimate follow-up; dispatch + invoicing/collections admin.
2. Opportunity: lead capture + speed-to-lead + quote follow-up automation; reactivation campaigns; reporting dashboard (call -> booked -> revenue). Voice agent only as a component.
3. Evidence (all vendor claims, directional): ServiceTitan says contractors miss ~27% of inbound calls (attributed to Invoca), ~78% of voicemail callers leave no message (no source given), and loses $45k-$120k/yr per HVAC company ('data across 1,200+ contractors', no source named) - verified on page. The '42 min average lead response' figure is NOT on the ServiceTitan page; removed as unverified. 85% no-callback (CallRail) is vendor-relayed, not verified. https://www.servicetitan.com/blog/ai-virtual-agents-in-hvac ; https://thoughtly.com/blog/ai-agents-hvac-contractors-lead-capture-dispatch . ServiceTitan itself sells AI voice agents -> incumbent threat.
4. Scores: Pain 4 / WTP 4 / Reach 3 / Build 4 / Comp 2 / Reg 5.
Verdict: real pain, but AI-answering is saturated and ServiceTitan/Housecall Pro/Jobber are bundling it. Differentiate with ops automation, not the phone.

## 2. Dental practices
1. Missed calls/new-patient capture; insurance eligibility verification; claims/recall follow-up.
2. Opportunity: insurance verification automation, recall/reactivation workflows, treatment-plan follow-up. Voice = crowded.
3. Evidence: manual eligibility check costs $10-11 and ~11 min (CAQH 2023, cited by RaftLabs); (RaftLabs page, vendor-adjacent; the $2.1B/yr dental figure I cited earlier is NOT on that page and is unverified - removed). https://raftlabs.com/blog/insurance-verification-automation-dental . Missed-call loss $100k-$150k/yr is JustCall (vendor) modelling; ~30% miss rate (Becker's sponsored). https://justcall.io/blog/?p=40778 ; https://www.beckersdental.com/ai-teledentistry/ai-in-dental-operations-how-practices-are-reducing-missed-calls-and-improving-chair-utilization/ . Off-the-shelf verification tools: ~$150-$249/mo per location listed (RaftLabs; its FAQ gives $150-$700). Automated check $0.50-$2.00 (vendor claim). Missed-call loss figures are (vendor claim).
4. Scores: Pain 4 / WTP 4 / Reach 3 / Build 3 / Comp 2 / Reg 2 (HIPAA, PMS integration access e.g. Dentrix/Eaglesoft).
Verdict: money is real; HIPAA + PMS integrations + many funded vendors (Overjet etc.) make it hard for a solo.

## 3. Medical/specialty practices & billing (RCM, prior auth, denials)
1. Prior auth; denial rework/appeals; patient intake/scheduling.
2. Opportunity: denial-appeal letter drafting, prior-auth packet prep, A/R follow-up for small billing companies.
3. Evidence: reworking a denied claim costs ~$47-64 (HFMA, cited in 2026 analysis); CAQH $12.88 per manual prior auth (vendor-cited). 61% of physicians fear payer AI increases PA denials (AMA survey of 1,000 physicians; verified on page). Other cost figures are (vendor claim)/secondary. https://www.ama-assn.org/practice-management/prior-authorization/how-ai-leading-more-prior-authorization-denials ; https://www.getmagical.com/blog/rcm-trends ; https://www.sprypt.com/blog/what-does-a-single-denied-claim-actually-cost
4. Scores: Pain 5 / WTP 4 / Reach 2 / Build 3 / Comp 1 (well-funded RCM AI: Magical, Solum, etc.) / Reg 1 (HIPAA, BAAs).
Verdict: biggest pain, hardest compliance; sell to small billing companies (not practices) if at all.

## 4. Veterinary clinics
1. Medical-record documentation; phones/refills; scheduling.
2. Opportunity: scribes and front-desk AI. Both crowded.
3. Evidence: Scribenote raised $8.2M seed (a16z, Sept 2024) and says "dozens" of AI scribes have entered; Digitail raised $23M Jan 2026. https://itbrief.com.au/story/ai-scribe-scribenote-raises-usd-8-2m-to-ease-vet-burnout ; https://www.vettimes.com/news/vets/international/digitail-announces-us23m-investment-funding . "86% severe stress" burnout stat is low-quality (vendor-cited).
4. Scores: Pain 4 / WTP 3 / Reach 3 / Build 3 / Comp 2 / Reg 4.
Verdict: funded competitors own the obvious wedge. Skip unless you find a non-clinical gap (e.g., corporate-group reporting).

## 5. Legal (solo/small firms)
1. Client intake & lead conversion; document drafting/review; billing/time capture.
2. Opportunity: intake + conflict check + follow-up automation, retainer/e-sign flows, referral CRM.
3. Evidence: Clio's 2026 solo/small-firm report: 71% of solos and 75% of small firms use AI; 57%/55% have no AI policy; separate 8am 2026 survey (1,300+ legal pros): 43% have no formal AI policy and no plans (verified on NC Bar page). https://ncbar.org/nc-lawyer/2026-05/by-the-numbers-what-surveys-show-about-law-firm-ai-adoption . A Canadian Lawyer piece describes solo/small-firm AI use as minimal ('barely dipped their toes'), utilization 27% solo / 32% small vs ~50% mid-size. https://canadianlawyermag.com/news/general/solos-and-small-firms-lag-with-ai-adoption-clio-report/392441 . CORRECTION: my earlier '72%/67% use AI, only 8%/4% widely adopted' figures (Clio 2025) came from a search summary; the Clio page returned 403 and Canadian Lawyer does not repeat them, so they are unverified and removed.
4. Scores: Pain 3 / WTP 4 / Reach 3 / Build 4 / Comp 2 (Smith.ai, Lawmatics, Clio Duo, Harvey at the top) / Reg 3 (ethics rules, confidentiality, UPL if client-facing).
Verdict: high WTP (billable hours), but lawyers are risk-averse and slow buyers; narrow practice-area intake (PI, immigration, family) could work.

## 6. Accounting / bookkeeping firms
1. Chasing clients for missing documents; data entry/categorization; month-end reconciliation + review.
2. Opportunity: document-chase and intake automation, reconciliation exception dashboards, client-onboarding workflows, custom finance tools (your strength).
3. Evidence: Intuit 2026 survey - top client-service AI uses: data entry 54%, forecasting 51%; fragmentation of tools is a stated pain. https://www.accountingtoday.com/partnerinsights/article/intuit/intuits-2026-accountant-technology-survey-ai-fragmentation-and-the-future-of-the-profession . Firms most want AI to chase clients for documents (vendor survey summary). Graduate pipeline at 20-year low is from a vendor blog (https://www.zeni.ai/blog/accounting-trends), not re-verified (vendor claim). Many tools already exist (Karbon, Financial Cents, Dext, Juno, etc.). 
4. Scores: Pain 4 / WTP 4 / Reach 4 (CPA communities, QBO ProAdvisor networks) / Build 5 / Comp 3 / Reg 3 (data security; not licensed advice if you stay in tooling).
Verdict: best builder fit (finance tools), integrations (QBO/Xero APIs) are open. Risk: lots of point solutions; win via implementation + custom glue for small firms.

## 7. Real estate brokerages/agents
1. Lead follow-up/speed-to-lead; transaction coordination (contract-to-close paperwork); listing content.
2. Opportunity: transaction coordinator automation, lead nurturing workflows, CMA/listing packet generators.
3. Evidence: I did not run a dedicated search; no sourced number. Judgment only.
4. Scores: Pain 3 / WTP 3 / Reach 4 / Build 4 / Comp 1 (Follow Up Boss, kvCORE, Lofty, many AI ISA tools) / Reg 4.
Verdict: crowded and agents are notoriously cheap/churny. Transaction coordination is the better sub-niche.

## 8. Property management (small/mid portfolios, 50-1,000 doors)
1. Maintenance triage and vendor dispatch; leasing inquiries; owner reporting/accounting reconciliation.
2. Opportunity: owner-statement and reporting automation, maintenance-triage workflows on top of AppFolio/Buildium, delinquency follow-up.
3. Evidence: Verified on LeadSimple page: only that vacancy-fill speed is the 'defining metric in 2026' (LeadSimple exec quote, vendor). The Entrata '100+ agents', AppFolio '98% of customers use AI' and EliseAI '43% more likely to apply' claims appeared in a search summary of a Vellum/other page and are NOT on the LeadSimple page; treat as unverified (vendor claim). https://leadsimple.com/blog/property-management-predictions-for-2026 ; https://www.vellum.ai/blog/best-ai-assistants-for-property-managers (not re-fetched). No independent market size found.
4. Scores: Pain 4 / WTP 3 / Reach 3 / Build 4 / Comp 2 / Reg 3 (fair housing in leasing communications).
Verdict: leasing is covered by funded players; small operators underserved on custom reporting/ops glue.

## 9. Insurance agencies (independent)
1. Re-keying data into carrier portals/submissions; certificates & endorsements servicing; renewal/cross-sell outreach.
2. Opportunity: submission data-entry automation, COI/servicing inbox triage, renewal-review workflows, agency dashboards.
3. Evidence: Applied Systems 2026 survey (702 agents, Apr-May 2026; verified on page): 90% reduced business with a carrier over submission friction; re-keying is top pain (74%); commercial submission automation wanted by 79%. https://prod.ivans.com/news/press-releases/2026/agents-are-choosing-carriers-that-automate-submissions-say-findings-in-2026-insurance-agency-carrier-connectivity-trends-survey-report/ . Insurance Thought Leadership page (fetched): nearly 30% of agencies expect AI process improvement to deliver strongest 2026 ROI; >1/3 say most value comes from AI embedded in existing tools. My earlier 'Big I: two-thirds plan to increase AI, 31% use none' is NOT on that page and is removed as unverified. https://www.insurancethoughtleadership.com/agent-broker/independent-agencies-top-priorities-2026 . I found no COI-specific data.
4. Scores: Pain 4 / WTP 4 / Reach 3 / Build 3 / Comp 3 / Reg 3 (licensing applies to advice not tooling; PII).
Verdict: strong, surveyed, independent-sourced pain; AMS integrations (Applied Epic, EZLynx, HawkSoft) are a gatekeeper.

## 10. Logistics: freight brokers, small carriers, dispatch
1. Email-to-load order entry/quoting; check calls and tracking updates; billing QA, POD/BOL doc matching, detention claims.
2. Opportunity: email/PDF extraction -> TMS entry, auto invoicing packets (BOL+POD+rate con), detention/accessorial recovery tracking.
3. Evidence: only trade/vendor commentary found; "AI is showing up first in narrow workflow assistance" (TMS vendor; verified on arktms page, also notes AI document checking is not production-ready everywhere); detention-specific 2026 data thin. https://arktms.com/blog/ai-freight-brokerage-smart-tms-features-2026 ; https://advalorem.substack.com/p/the-ai-dispatch-desk-automating-quoting . No hard $ stats found.
4. Scores: Pain 4 / WTP 3 / Reach 2 (cold-reach hard, lower-margin, relationship/FB-group driven) / Build 4 / Comp 3 / Reg 4.
Verdict: genuinely repetitive document work; small buyers are thin-margin, and well-funded freight-AI startups (Vooma, Pallet, etc. - from my background knowledge, unverified here) target brokers.

## 11. Construction (subs and small GCs)
1. Estimating/takeoff; change-order pricing and tracking; RFI/submittal/paperwork and payment applications.
2. Opportunity: bid-intake/estimate-assembly workflows, change-order and pay-app generators, bid follow-up CRM, reporting dashboards.
3. Evidence: takeoff errors drive 5-10% material overruns (contractormag page says 'studies estimate', no source cited; page does not discuss change orders); vendor claims of 80% takeoff time cut; tools like Togal $299/user/mo, Kreo from $35/mo, STACK, Contractor Foreman $49/mo. No independent change-order data. https://www.contractormag.com/management/best-practices/article/55247411/how-specialty-subcontractors-can-use-ai-to-improve-bidding-material-takeoffs-and-scheduling ; https://gobridgit.com/blog/construction-estimating-software/
4. Scores: Pain 4 / WTP 3 / Reach 2 / Build 3 / Comp 3 / Reg 4.
Verdict: pain is real, owners busy on site and hard to reach. Takeoff AI is its own funded category - avoid; do the admin glue.

## 12. Restaurants / hospitality
1. Phone ordering/reservations; labor scheduling and turnover; invoice/COGS tracking, review management.
2. Opportunity: invoice-to-COGS dashboards, review responses, catering lead handling. Phone ordering = saturated.
3. Evidence: SoundHound powers 10,000+ locations, Q1 2026 revenue $44.2M (+52%), and partnered with Toast (Feb 2026) to put phone ordering in the POS; 8+ independent-focused voice vendors at $99-$499/mo/location. https://restauranttechnologynews.com/2026/06/soundhound-ai-brings-voice-and-agentic-ai-to-restaurant-ordering-drive-thru-automation-and-guest-service/ ; https://loman.ai/blog/ai-phone-ordering-systems-restaurants
4. Scores: Pain 3 / WTP 2 (thin margins, low ARPU) / Reach 3 / Build 4 / Comp 1 / Reg 4.
Verdict: avoid.

## 13. E-commerce / DTC
1. Support tickets (WISMO, returns); catalog/content ops; reporting/profit analytics.
2. Opportunity: custom support agent + returns flows, profit/inventory dashboards, ops automations (your skills).
3. Evidence: WISMO often 30-60% of support volume; returns 10-20% (vendor guides); off-the-shelf stack (Gorgias from $10/mo, eDesk $39/agent) is cheap, so small stores buy subscriptions not agencies. https://getzowie.com/blog/ecommerce-customer-service-software ; https://www.edesk.com/blog/best-ai-customer-support-tool-shopify/ . No agency-spend data found.
4. Scores: Pain 3 / WTP 3 / Reach 4 / Build 5 / Comp 1 / Reg 4.
Verdict: easy to build and reach, but commoditized and low ticket; best at $3M+ brands needing custom analytics/ops.

## 14. Auto repair shops & dealerships
1. Missed calls/appointment booking; service-lane communication; estimate approvals/parts invoice reconciliation.
2. Opportunity: text-based estimate approval + follow-up, invoice/core-credit reconciliation, dealership service BDC overflow.
3. Evidence: vendors claim independents miss 25-40% of calls (unverified); Numa analysis of 1.5M reviews: communication failures are in 36.8% of negative mentions; 58% of auto callers prefer a human (Invoca 2026 via JustCall). WickedFile notes AI phone agents don't touch back-office. https://www.numa.com/blog/how-ai-is-used-in-automotive-dealerships-2026 ; https://www.wickedfile.com/blogs/ai-phone-agents-auto-repair/ ; https://justcall.io/blog/best-ai-answering-services-auto-repair.html
4. Scores: Pain 3 / WTP 3 / Reach 3 / Build 4 / Comp 2 / Reg 4. Dealerships: higher WTP, but long sales cycles and DMS lock-in (CDK, Reynolds).
Verdict: phone saturated; back-office invoice work is an underserved gap.

## 15. Education / tutoring centers / private schools
1. Enrollment inquiry follow-up; payment chasing; parent comms.
2. Opportunity: enrollment funnel automation.
3. Evidence: only vendor pages (e.g. Frontdesk); claims like "40% more enrollment" unsourced. No independent data.
4. Scores: Pain 2 / WTP 2 / Reach 3 / Build 5 / Comp 2 / Reg 2 (FERPA/child data).
Verdict: low budgets. Skip.

## 16. Nonprofits
1. Grant research/writing; donor communications; reporting to funders.
2. Opportunity: grant pipeline tracker + drafting, donor data hygiene dashboards.
3. Evidence: 92% use AI but only 7% report major improvement (Virtuous/Fundraising.AI, 346 orgs, Feb 2026); orgs >$1M budgets adopt at nearly 2x rate of smaller (TechSoup 66% vs 34%); ~30% of small orgs cite budget as barrier. https://nonprofitpro.com/article/2025-ai-benchmark-report-how-artificial-intelligence-is-changing-the-nonprofit-sector ; https://blog.techsoup.org/posts/what-ai-means-for-nonprofits-in-2025-insights-from-the-ai-benchmark-report ; 67% of foundations undecided on AI-written applications (secondary compilation, low confidence).
4. Scores: Pain 3 / WTP 2 / Reach 3 / Build 4 / Comp 3 / Reg 4.
Verdict: sympathetic but budget-poor, long procurement. Skip.

## 17. Marketing / creative agencies
1. Client reporting; content production; lead-gen ops for their clients.
2. Opportunity: white-label reporting dashboards, workflow builds; selling TO agencies who resell.
3. Evidence: AgencyAnalytics 2026 benchmark (494 respondents): 79% save 5+ hrs/week with AI, reporting summaries top value (42%), 38% using agentic automation. https://agencyanalytics.com/company/newsroom/press-release-agency-benchmarks-report-2026 . Secondary claim that 73% finish a report in <1 hr (unverified) suggests reporting pain is modest, and tooling (AgencyAnalytics, Databox, Improvado) is mature.
4. Scores: Pain 2 / WTP 3 / Reach 5 / Build 5 / Comp 1 / Reg 5.
Verdict: easiest to reach, but agencies are your competitors and DIY themselves. Useful as a channel/partner, not a niche.

## 18. Small manufacturers / job shops
1. RFQ intake and quoting; order/ERP data entry; quality docs/compliance.
2. Opportunity: RFQ email -> quote draft workflow; quote follow-up; customer-portal.
3. Evidence: the 'fast quotes win 28-35% vs 12-20%' stat is NOT on the CloudNC page (which is marketing and only argues qualitatively that RFQ queues bottleneck); unverified, removed from reliance. AMFG page confirms its 'under 90 seconds, +/-10%' claim (vendor claim). Competitors: Paperless Parts, Uptool ($195/mo), AMFG, Quotara (CA$149/mo). https://www.cloudnc.com/blog/why-quoting-is-the-bottleneck-in-manufacturing ; https://www.amfg.ai/job-shop . No adoption survey found.
4. Scores: Pain 4 / WTP 4 / Reach 2 / Build 3 / Comp 3 / Reg 4.
Verdict: strong ticket sizes; reach is slow (trade shows, MEP centers); quoting needs domain depth (CAD/geometry).

## 19. Fitness studios / gyms; Beauty salons / med spas
1. No-shows and rebooking; lead follow-up; membership churn/retention.
2. Opportunity: rebooking/retention automation, win-back campaigns.
3. Evidence: salon no-show ~20% without reminders (unsourced stats page), market-size estimates differ ~10x ($518M booking-only vs $12B management software); the platforms (Zenoti, Mindbody, Vagaro, Phorest) ship AI receptionists/retention themselves. https://zenoti.com/blog/how-to-reduce-no-shows/ . Med spa has higher ticket sizes (my judgment, unsourced).
4. Scores: Fitness/salon: Pain 3 / WTP 2 / Reach 3 / Build 4 / Comp 1 / Reg 4. Med spa: WTP 3, Reg 3.
Verdict: platform-native AI eats this. Skip, except med spa as a sub-niche of high-ticket aesthetics clinics.

## 20. Recruiting / staffing agencies
1. Resume screening and candidate matching; outreach/re-engagement; compliance and timesheets.
2. Opportunity: ATS-integrated screening, candidate database reactivation, timesheet-to-invoice automation for small staffing firms.
3. Evidence: only vendor claims (Bullhorn: 51% more submissions; unverified); "7.4M open US jobs June 2026" cited by Bullhorn. Agencies carry legal exposure on AI screening. https://www.bullhorn.com/blog/best-recruitment-agency-software/ ; https://recruitbpm.com/blog/ai-candidate-screening-discover-ai-game-changer-in-recruitment
4. Scores: Pain 3 / WTP 3 / Reach 4 (LinkedIn) / Build 4 / Comp 1 / Reg 2 (NYC LL144, EU AI Act, state AI-hiring laws - I did not verify current rules).
Verdict: crowded and regulatory-heavy. Staffing back office (timesheets/payroll/invoicing) is better than screening.

## 21. Events / wedding venues
1. Inquiry response speed; tour scheduling; proposal/contract generation.
2. Opportunity: inquiry-to-tour automation.
3. Evidence: 76% of planners expect a venue response within 24 hrs but 49% unsure and 29% don't plan to use AI (VenueNow Jan 2026, Australia/NZ, n=335). Couples contact avg 4.7 venues (The Knot via vendor). https://venuenow.com/blog/?p=165107
4. Scores: Pain 3 / WTP 3 / Reach 3 / Build 5 / Comp 2 / Reg 4.
Verdict: small and seasonal; lots of cheap chatbot vendors.

## 22. Previously-unsearched niches (now researched; revised)

### 22a. Mortgage brokers / lenders (processing, document collection, conditions)
1. Workflows: borrower document chasing; conditions clearing/underwriting file prep; closing-disclosure balancing.
2. Opportunity: doc-collection portal + chase automation, condition tracking for small brokers/IMBs.
3. Evidence: cost to originate ~ $11,000 per loan, with compensation ~2/3 of direct cost and technology only ~4% (MBA data as analyzed by HousingWire; authors' models, not measurements) https://www.housingwire.com/articles/cost-originate-ai-economics/ . Lender AI adoption 15% (2023) -> 37% (2024) -> 60% (2025) per STRATMOR (same article) - i.e., this is already a crowded, funded space (SnapDocs etc.; one lender case: QC review time -71%, vendor-reported). NMN survey of 150+ pros: 57% expect AI underwriting to be the biggest 2026 change; 49% expect income/employment verification to be streamlined https://www.nationalmortgagenews.com/news/ai-hits-underwriting-57-of-pros-predict-change . Another NMP piece on reinventing origination was found but not fetched. No practitioner-forum (Reddit) evidence found. Compliance: fair-lending enforcement noted by a vendor roundup (unverified).
4. Scores: Pain 4 / WTP 4 / Reach 3 / Build 3 / Comp 2 / Reg 2 (GLBA, TRID, fair lending; PII).
Verdict: pain is now supported by non-vendor-ish data, but adoption is already ~60% and it is regulated. Dropped from #4 to #9.

### 22b. Real estate agents / brokerages
1. Workflows: lead follow-up; listing/marketing content; transaction paperwork.
2. Evidence: NAR 2026 Technology Report (released 2026-09-22): ~48% of agents use AI weekly (23% daily), non-users fell to 21% from 32%; use cases: listing descriptions 75%, social 56%, emails 52%, document review/summaries 27%; ChatGPT used by 91% of AI-using agents; barriers: learning curve 63%, cost 59%; 11% report negative AI impact (vs 4%). https://www.realestatenews.com/2026/09/22/agents-branching-out-from-generative-ai-as-adoption-grows ; https://www.housingwire.com/articles/realtors-ai-use-2026 (from search results; Inman page returned 403). Budgets: 73% of agents spend <= $500/mo on all tech; 18% spend <$50 (NAR 2026, 1,165 responses; verified) https://theclose.com/stats-trends/news-real-estate-tech-spending/ . No transaction-coordinator-specific data found; no forum data.
3. Scores: Pain 3 / WTP 2 / Reach 4 / Build 4 / Comp 1 / Reg 4.
Verdict: heavy DIY ChatGPT use plus low per-agent budgets = poor niche for paid services. Only brokerage-level (many agents) deals look viable.

### 22c. Government-contractor proposal writing
1. Evidence is weak: no 2026 non-vendor survey found. Only dated data: American Express OPEN survey, FY2015 - small firms spent on average $148,124 in time and money pursuing federal work; 'nearly half' of prime bids successful (GovExec, verified) https://govexec.com/management/2017/01/keep-winning-federal-contracts-small-business-say-they-have-spend-more/134380 . Everything on 2026 cost per bid ($5k-$50k vs $20k-$200k+; $25k->$5k with AI) is vendor claim and mutually inconsistent. A vendor says GSA/FedRAMP/CMMC may constrain AI tools handling CUI (unverified). No Reddit/practitioner forum results surfaced.
2. Scores: Pain 3 / WTP 3 / Reach 3 / Build 4 / Comp 2 (Loopio, Responsive, Qvidian, Unanet, many govcon-specific AI) / Reg 3.
Verdict: unsupported by evidence; keep out of top 10.

### 22d. Solar installers (sales / lead handling)
1. Evidence: Wood Mackenzie (independent): residential solar CAC fell to $0.60/W in 2025, forecast to rise ~40% to $0.84/W in 2026 as the 25D credit expires, with the market projected to contract 19% (verified) https://woodmac.com/news/opinion/us-residential-solar-customer-acquisition-costs-set-to-spike-40-in-2026-before-gradual-decline/ . Speed-to-lead: '81.2% of companies responding after an hour lose leads' (Blazeo via Thoughtly, a vendor) and AI-appointment-setter claims like 'Thoughtly: 38% more closed deals' are (vendor claim). Trina Solar blog puts CAC near $10,000/sale (~25% of install cost) citing LBNL (not independently checked) https://www.trinasolar.com/us/resources/blog/Remain-Competitive-in-the-Residential-Solar-Sector-20260401/ .
2. Scores: Pain 4 / WTP 3 (shrinking market, tighter budgets) / Reach 3 / Build 4 / Comp 2 / Reg 3 (TCPA).
Verdict: acute CAC pain, but market is contracting and installers are cash-constrained; high churn/bankruptcy risk for a client base. Not top 10.

### 22e. Cleaning / landscaping / lawn care
1. Evidence: no Reddit/forum posts surfaced; sources are vendor/review pages. ServiceM8 (vendor) names scheduling, office-field comms, route planning, quoting follow-up; Jobber is the dominant incumbent (~1,460 Capterra reviews); cheap quoting tools exist (LawnVex from $49/mo, satellite-measured quotes). One reviewer wanted 'not a lot of autopilot'. Turf Magazine fetch returned 403. https://www.servicem8.com/articles/how-to-optimize-your-lawn-mowing-business ; https://sourceforge.net/software/product/LawnVex/
2. Scores: Pain 3 / WTP 2 / Reach 4 / Build 5 / Comp 2 / Reg 5.
Verdict: low WTP, bundled incumbents. Not top 10.

### 22f. Not researched further (judgment only)
- Medical/chiro/PT front-desk: same saturation as dental (Pain 3 / WTP 3 / Reach 3 / Build 3 / Comp 2 / Reg 2).
- Fractional-CFO / SMB finance dashboards (Pain 3 / WTP 3 / Reach 3 / Build 5 / Comp 2 / Reg 3) - judgment only, no evidence gathered.

---
## RANKED TOP 10 (revised 2026-10-09; for this builder: web/dashboards/workflows/finance tools, solo)

1. **Accounting & bookkeeping firms (back-office workflow + custom finance tooling).** Best skill match and open APIs (QBO/Xero). Intuit 2026 (verified): 88% use AI for client services, but the average firm runs 10 apps and only 41% say tools are fully integrated - an integration/glue gap. Financial Cents (verified): only 20% of AI-using respondents see clear measurable ROI and ~87% have no written AI policy. Reachable via CPA communities. Risk: many point tools; win as implementer for 5-30 person firms.

2. **Independent insurance agencies (submission/servicing automation).** Applied Systems 2026 (n=702, verified): 90% reduced business with a carrier over submission friction; re-keying across portals is top pain (74%); 79% want commercial submission automation. Agencies pay for software. Gatekeeper: AMS integrations (Applied Epic, EZLynx, HawkSoft). Less crowded than voice.

3. **Small manufacturers / job shops (RFQ-to-quote workflow).** High ticket values and a plausible lever (quote speed), but evidence is mostly vendor/qualitative (CloudNC argues RFQ queues bottleneck; win-rate stat unverified). Competitors exist at $149-$195/mo. Reach is slow (MEP centers, trade groups) and domain depth needed. Evidence is thinner than first stated.

4. **Small property managers: owner reporting, maintenance ops glue.** Leasing is covered by funded vendors; small operators are underserved on reporting/exceptions (fits dashboards/finance). Evidence is mostly vendor; platform vendors will keep absorbing features, so moat risk is real. Moved up one slot.

5. **Legal: niche-practice intake and follow-up (PI, immigration, family).** High WTP; solo/small firm AI use is mostly light experimentation (Canadian Lawyer; Clio 2026 71-75% use AI), and 43% of legal pros report no formal AI policy and no plans (verified). Slower, risk-averse buyers; pick one practice area.

6. **Construction subs / specialty contractors (bid intake, change orders, pay apps).** Admin pain is plausible but evidence is thin (the 5-10% overrun stat has no cited source; no change-order data). Hard to reach; stay on paperwork/workflow, not takeoff.

7. **Home services (non-phone ops: quote follow-up, reactivation, reporting).** Largest buyer pool, but every number is a vendor claim and AI answering is saturated/bundled (ServiceTitan). Only viable with a differentiated back-office offer.

8. **Logistics: small brokers/carriers (email-to-TMS, billing packet, detention recovery).** Repetitive document work, but no hard numbers found and buyers are low-margin; trade/vendor commentary says AI is arriving as narrow workflow assistance.

9. **Mortgage brokers / small lenders (doc collection, conditions).** Moved down from #4. Pain is real ($11k cost to originate, comp ~2/3) but lender AI adoption is already ~60% (STRATMOR via HousingWire), funded vendors are entrenched, and compliance (GLBA/TRID/fair lending) is heavy. No forum evidence found.

10. **Dental / clinic insurance verification & recall automation.** Best-quantified unit economics ($10-11 and ~11 min per manual check, CAQH via RaftLabs) but HIPAA and PMS access push it down for a solo; consider only via a BAA-compliant partner.

Deliberately NOT ranked (saturated, low budget, or unsupported): generic AI receptionists in any vertical, restaurants, salons/gyms, tutoring, nonprofits, events, vet scribes, recruiting screening, marketing agencies as customers, real estate agents (heavy DIY ChatGPT, low budgets), gov-con proposals (no current non-vendor evidence), solar installers (market contracting 19%), cleaning/landscaping (low WTP, Jobber-dominated).

## Biggest surprises / caveats
- The best independent evidence (Applied Systems, Intuit, Clio, Census) points to back-office workflows, not phones.
- Platforms (ServiceTitan, AppFolio, Entrata, Toast, Zenoti) are shipping native AI - the "layer on top of the system of record" window is closing.
- Nearly all missed-call dollar figures trace to vendors; treat as marketing.
- Gaps remaining: no Reddit/practitioner-forum sources surfaced for any of the five revisited niches (search tool returns mostly vendor/trade pages); freight/construction hard numbers still thin; Clio and Inman pages blocked (403).

---
## Revision notes (2026-10-09, second pass)
- Researched mortgage, real estate agents, gov-con, solar, cleaning/landscaping (section 22a-e). Found 2+ sources each, but mostly trade/vendor; no Reddit/forum content surfaced. Mortgage dropped from #4 to #9 (60% lender AI adoption, regulation). Real estate, gov-con, solar, cleaning kept out of top 10.
- Fetched sources cited in top 10 and corrected:
  - Verified: Intuit survey (88%, 54%, 51%, fragmentation); Applied Systems/IVANS (702, 90%, 74%, 79%); arktms (narrow workflow assistance); AMA (61%, n=1,000); NC Bar (43% no policy; Clio 2026 71%/75%); AMFG claims; RaftLabs ($10-11/11 min, $0.50-2.00).
  - Corrected: Financial Cents (20% is of AI-using respondents; no-policy is 87% in body vs 90% on cover); Big I '2/3 plan more AI, 31% none' not on cited ITL page - removed; Clio 2025 '72%/67%/8%/4%' unverifiable (403, not on Canadian Lawyer) - removed; ServiceTitan '42 min response' not on page - removed, other figures kept and labelled (vendor claim); RaftLabs '$2.1B dental' not on page - removed; CloudNC win-rate stat '28-35% vs 12-20%' not on page - removed; LeadSimple page lacks Entrata/AppFolio/EliseAI claims - flagged unverified; contractormag 5-10% has no cited source and page has no change-order content.
  - Not fetched (still search-summary level): gobridgit, advalorem substack, justcall, vellum, thoughtly, becker's, scribenote/digitail, SoundHound/Loman, TechSoup/Virtuous, AgencyAnalytics, Census, VenueNow, Numa, WickedFile. These are outside the top-10 evidence or lower priority; treat as unverified.
- Vendor-sourced numbers are now explicitly marked (vendor claim) in the sections touched; remaining unmarked vendor figures in sections 3-21 should be read as vendor claims per the method note at the top.
- Re-ranking: property management to #4 (from #5), legal #5, construction #6, home services #7, logistics #8, mortgage #9, dental #10; manufacturers kept #3 with downgraded evidence strength.
