# Pay-Per-Call Networks and the Pay-Per-Call Model for Local Services (as of Nov 2026)

Research note on method and reliability: all findings below come from web search result summaries. Direct page fetches failed in this session (elevarus.com, leadgen-economy.com, blog.servicedirect.com, leadsmartinc.com were unreachable from the sandbox), so no page was read in full; figures are as surfaced in search snippets. Most payout data in this industry is published by vendors/networks with a commercial interest (Lead Smart, Elevarus, Service Direct, eLocal, CallScaler, Clicks Geek). Treat numbers as market indicators, not audited data. Primary/stronger sources: Marchex and Angi and Justdial investor releases, eLocal help centre and API docs, Service Direct's own pricing page, law-firm summaries of the FCC/Eleventh Circuit actions.

## 1. How does pay-per-call work mechanically (buyers, publishers, networks, tracking numbers, IVR, routing, ping-post/RTB, qualified-call definitions)?

### Takeaway
A publisher generates an inbound phone call on a tracking number; a routing platform (Ringba, TrackDrive, Retreaver etc.) either routes it by static rules or auctions it in 2-5 seconds to buyers; the buyer pays only if the call meets a contractual "billable" definition, most commonly a duration threshold (10 seconds at the low end at eLocal; 60-120 seconds typical elsewhere) plus geography/category match. The network's margin is the spread between what the buyer pays and what the publisher is paid.

### Cited Findings
- Economics definition: revenue from the buyer per qualified call, minus payout to the publisher per qualified call, equals the operator/network margin — [CallScaler](https://callscaler.com/blog/call-tracking-for-pay-per-call)
- Real-time bidding for calls is a "ping tree" (the call equivalent of ping/post in lead gen): a publisher's call is pinged to every buyer in the tree simultaneously, bids received within a window "usually between 2 and 5 seconds" are compared, and in standard routing the highest bidder wins — [Ringba blog](https://www.ringba.com/blog/pay-per-call/real-time-bidding-for-calls); [Ringba Ring Tree product page](https://www.ringba.com/ping-tree)
- Ringba describes RTB as the buying side of "programmatic" buying and selling of calls; static call flows are not compatible with RTB campaigns — [Ringba support, RTB Q&A, 12 May 2026](https://support.ringba.com/hc/en-us/articles/41409135078551-12-May-2026-Real-Time-Bidding-Q-A)
- eLocal exposes a public "Call Ping API": each bid returned to a publisher includes a price and a `billable_duration` value, which varies by the publisher's agreement with eLocal — [eLocal Call Ping API docs](https://elocal.com/docs/call_api/)
- Service Direct (buy side for contractors): the contractor sets the price it is willing to bid per lead and its service area; Service Direct's system gathers calls from many sources and bids on them based on the contractor's ZIP code and bid; the contractor pays only for calls meeting "billable lead" criteria — [Service Direct blog, HVAC](https://blog.servicedirect.com/what-to-expect-when-buying-hvac-leads-from-service-direct)
- Service Direct runs two campaign types: duration-based (time on the phone alone determines billable/non-billable; no manual lead review available) and reviewed campaigns — [Service Direct support, Lead Manager](https://support.servicedirect.com/lead-manager)
- Billable-duration thresholds: a call commonly becomes billable after 60-120 seconds depending on vertical; most buyers leave it at a 60- or 90-second platform default — [Elevarus guide](https://elevarus.com/pay-per-call-marketing-complete-guide/); [Elevarus buffer-time article](https://elevarus.com/pay-per-call-buffer-time-settings-by-vertical/)
- "Buffer time" is a grace window after connect where neither side counts the call, typically 10-30 seconds — [Elevarus buffer-time article](https://elevarus.com/pay-per-call-buffer-time-settings-by-vertical/)
- eLocal's rule is far looser: a call is billable if it rang for 10 or more seconds, even if the caller hangs up; calls the buyer declines or hangs up on are also billable; invalid calls can be credited (to the eLocal account balance, not refunded to card) on approval — [eLocal help: valid/invalid calls](https://help.elocal.com/features/valid-invalid-calls-leads/)
- Google's own pay-per-lead product (Local Services Ads) uses a comparable rule from 1 Oct 2026: missed calls during business hours are billable if the caller stays on the line more than 20 seconds; follow-up calls are charged at most once within 15 days of the first interaction — [PPC Land](https://ppc.land/google-charges-local-services-advertisers-for-missed-calls-over-20-seconds/); [Search Engine Roundtable](https://seroundtable.com/google-lsa-missed-subsequent-calls-41940.html)
- IVR dispositions are mapped to payout codes to reduce publisher disputes (one vendor proposes a 9-code disposition map) — [Elevarus IVR article](https://elevarus.com/pay-per-call-ivr-disposition-payout-mapping/)
- Lead Smart's August 2026 benchmark reports that every top-paying home-service category priced per appointment rather than per call duration — [Lead Smart press release via Portland Tribune](https://pr.portlandtribune.com/article/Lead-Smart-Inc-Publishes-August-2026-Pay-Per-Call-Payout-Benchmark-for-417983-ZIP-Service-Rows/6a7de4e775104c0002c9a2c6)

### Inferences
- The end-to-end chain is: consumer search/ad/listing -> tracking number (identifies publisher and source) -> optional IVR (press 1 for plumbing, enter ZIP) -> platform filters (geo, hours, caller-ID dedupe, buyer caps) -> static route or 2-5 second auction -> warm transfer to buyer -> duration timer -> billable event -> buyer invoiced, publisher paid on a delay to allow disputes.
- The "qualified call" definition is the single most contested contract term; thresholds range by a factor of 10x (10 s to 120 s), and the highest-value categories are migrating from duration to appointment-based billing, which shifts risk from buyer to network.
- Hours-of-operation and concurrency caps are standard routing filters in these platforms, but no source in this research gave specific numbers for them.

### Gaps
- No source gave Ringba's actual per-minute or platform fees (pricing is "custom"/usage-based; Capterra and review sites list no figures) — [Capterra](https://www.capterra.com/p/176276/Ringba).
- Service Direct's exact duration threshold was not found.
- No concrete data on typical publisher payment terms (net-15/net-30) or hold-back periods.

## 2. Who are the main networks and tech platforms, and what are their models, take rates and scale?

### Takeaway
The ecosystem splits into (a) routing/tracking software sold to networks and publishers (Ringba, TrackDrive, Retreaver, Phonexa, CallRail, Invoca, Marchex), (b) networks/marketplaces that buy calls from publishers and resell to contractors (Service Direct, eLocal, Soleo, Networx, Angi), and (c) Google LSA as the dominant first-party pay-per-lead channel. Hard scale data exists only for the public or disclosed companies; take rates are almost never published.

### Cited Findings
- Marchex (public, call analytics/conversation intelligence): 2025 GAAP revenue $45.4M vs $48.1M in 2024; Q4 2025 revenue $10.8M vs $11.9M; 2025 net loss $5.2M; adjusted EBITDA loss $0.7M; about 1,000 customers migrated to a new platform; guided to 10%+ adjusted EBITDA margins for 2026 — [Marchex Q4/FY2025 release](https://investors.marchex.com/news-releases/news-release-details/marchex-announces-fourth-quarter-and-full-year-2025-results-and)
- Marchex agreed (Nov 2025) to acquire Archenia, a performance-based "pay for outcomes"/pay-for-call customer acquisition firm, for about $10M upfront via convertible note plus earn-outs of up to 4M Class B shares; the acquisition was later announced as completed (2026) — [Marchex filing](https://investors.marchex.com/node/17826/pdf); [completion notice](https://www.01net.it/marchex-completes-acquisition-of-archenia/)
- Marchex historically sold its "Call Marketplace" and "Local Leads" products for $2.25M cash plus contingent consideration (buyer not named in the snippet) — [Marchex filing](https://investors.marchex.com/static-files/f58bf6e0-e5b3-479a-84ca-34a22a171948). Older context: Marchex bought pay-per-call firm VoiceStar for $20M in 2007 and Jingle Networks (800-FREE-411) in 2011 — [ClickZ](https://clickz.com/?p=82952); [Search Engine Land](https://searchengineland.com/marchex-acquires-800-free-411-owner-jingle-networks-72438)
- Invoca (enterprise call tracking/conversation intelligence): surpassed $100M ARR in fiscal year ended 31 Jan 2023; valued at $1.1B after an $83M round in June 2022; $184M total venture funding — [Invoca press release, Apr 2023](https://www.invoca.com/press-release/invoca-surpasses-100-million-annual-recurring-revenue-and-extends-leadership-in-ai-conversation-intelligence); [TechCrunch, Jun 2022](https://techcrunch.com/2022/06/14/proving-that-contact-center-tech-remains-desirable-invoca-raises-83m/). Third-party current-revenue estimates conflict: about $103.8M (Latka, Oct 2024) vs about $76M (TechList) — [Latka](https://getlatka.com/companies/invoca); [TechList](https://techlist.ai/invoca.com)
- CallRail (SMB call tracking): third-party estimate of about 180K customers and about $100M revenue (unverified estimate) — [Latka](https://getlatka.com/companies/callrail/vs/invoca)
- Ringba: usage-based pricing, marketed as no contracts/minimums; per a May 2026 competitor comparison, Ringba does not offer native AI voice answering or conversation intelligence — [CallRail blog](https://www.callrail.com/blog/ringba-alternatives); [SourceForge listing](https://sourceforge.net/software/product/Ringba)
- Service Direct: contractor-set bids per campaign; April 2026 "mySD" dashboard reports Won Calls, Billable Leads, average CPL and total spend; it also buys calls from outside publishers; has an "Enterprise" pay-per-call offering — [Newswire, mySD launch](https://www.newswire.com/news/service-direct-unveils-the-all-new-mysd-client-dashboard-with-our-22769339); [Service Direct blog: selling calls](https://blog.servicedirect.com/what-to-expect-selling-calls-to-service-direct)
- eLocal: operates both a contractor-facing pay-per-call product and an affiliate pay-per-call rev-share programme with a published category price list and a ping API for publishers — [eLocal affiliate price list](https://www.elocal.com/price-list/affiliate-pay-per-call-rev-share-category-coverage); [eLocal Call Ping API](https://elocal.com/docs/call_api/)
- Angi (largest US home-services lead marketplace; context for network-sourced leads): after "homeowner choice" launched Jan 2025, Network Service Requests fell 69% and Network Leads fell 78% YoY in Q4 2025; Q3 2026 revenue $242.0M (-8.9% YoY) with adjusted EBITDA $42.2M (+6.3%); Q3 2026 service requests about 4M (-2.4% YoY); Q2 2026 revenue -11%, leads -13%, revenue per lead +1%; management is deliberately shifting toward larger pros with bigger budgets and better lead-conversion capability — [Angi IR](https://ir.angi.com/node/13006/html); [MarketBeat Q3 2026 call highlights](https://www.marketbeat.com/instant-alerts/transcript-angi-q3-earnings-call-highlights-2026-11-04/); [MarketBeat Q2 2026](https://www.marketbeat.com/instant-alerts/angi-q2-earnings-call-highlights-2026-08-05/); [finsee Q3 2026 review](https://finsee.ai/earnings/angi/2026/q3/en/)
- Phonexa sells competing call-logic software with its own AI Call Agents and a UK-localised pay-per-call product — [Phonexa Ringba review](https://phonexa.com/blog/ringba-review/); [Phonexa UK](https://phonexa.uk/call-logic/pay-per-call/)

### Inferences
- Software platforms monetise per minute/per usage and take no call-quality risk; networks monetise the buyer-minus-publisher spread and carry dispute/credit risk. A middleman app is structurally a network, not a platform.
- Angi's 78% collapse in network leads after requiring homeowners to choose the pro (rather than blasting the lead to several) shows how much volume in the legacy model depended on reselling one consumer to multiple buyers; consent/choice requirements shrink supply sharply but the remaining leads monetise better.
- The low valuations and shrinking revenue at Marchex suggest stand-alone call analytics is commoditising; value is moving to outcome-based acquisition (the Archenia rationale) and AI qualification.

### Gaps
- No reliable data found on Soleo, Networx, Aragon Advertising, Palo, Astoria, RingPartner, Retreaver or TrackDrive scale, pricing or take rates; these are private and searches returned nothing citable.
- No published network take rate. Vendor guides describe the spread but give no verified percentage. Any margin figure in a final report should be labelled an estimate.
- Ringba's annual call volume and revenue were not found.

## 3. Typical payouts per qualified call by local-service vertical, buyer conversion rates and economics

### Takeaway
What contractors pay per billable call in US home services in 2026 runs roughly $15-$75 for locksmith, $22-$85 appliance repair, $40-$195 pest control, $60-$255 plumbing, $65-$325 AC/HVAC and $85-$550 roofing (Service Direct's published ranges); what publishers receive is materially lower (Lead Smart network medians of $14 appliance repair, about $33 plumbing, $38.50 HVAC, $42 roofing; all-vertical median $32.50). Service Direct says 50-60% of billable leads become booked appointments.

### Cited Findings
Buyer-side prices (what the contractor pays):
- Service Direct published pay-per-lead ranges by trade: air conditioning $65-$325; appliance repair $22-$85; electrician $55-$175; locksmith $15-$75; pest control $40-$195; plumbing $60-$255; roofing $85-$550 (table formatting in the search result was partly jumbled, so row pairings should be re-verified on the page) — [Service Direct pay-per-lead costs](https://servicedirect.com/pay-per-lead-costs/)
- eLocal published ranges: air conditioning contractors $15-$340; fencing contractors $22-$90 — [eLocal affiliate price list](https://www.elocal.com/price-list/affiliate-pay-per-call-rev-share-category-coverage)
- Third-party estimates: plumbing $35-$80 per call (another source: $20-$100 in 2026); HVAC service $40-$90, HVAC install $80-$200 per call; locksmith $25-$60 per call; pest control $20-$80+; water damage $80-$350; exclusive roofing leads $150-$300+ vs shared roofing leads $75-$110+ — [Baadigi Service Direct review](https://www.baadigi.com/blog/service-direct-leads-review); [ResultCalls 2026 prices by trade](https://resultcalls.com/blog/how-much-do-home-service-leads-cost-in-2026-prices-by-trade); [Lead Search Pros](https://leadsearchpros.com/lead-pricing)
- Across published vendor figures a pay-per-call lead sells for anywhere between $15 (locksmith, low end) and $2,250 — [Elevarus guide](https://elevarus.com/pay-per-call-marketing-complete-guide/)
- General ranges from vendor blogs: $20-$150+ per qualified call; one guide puts home services between $35 (low-ticket pest control) and $120 (HVAC replacement, roofing) — [Clicks Geek](https://clicksgeek.com/pay-per-lead-services/); [EDM Network](https://edmleadnetwork.com/top-pay-per-call-verticals-2026/)

Publisher-side payouts (what the call generator receives):
- Lead Smart September 2026 release, pay-per-call payout rates: roofing $42.00, HVAC $38.50, plumbing $33.25, appliance repair $14.00 — [Lead Smart, 5 Sep 2026](https://leadsmartinc.com/news/press-google-lsa-lead-costs-rise-payout-data-september-2026)
- Lead Smart August 2026 benchmark (417,983 ZIP-service rows): all-vertical median payout $32.50; water damage is the top-paying home-service category; every top-paying category priced per appointment, not per call duration — [Lead Smart via Portland Tribune](https://pr.portlandtribune.com/article/Lead-Smart-Inc-Publishes-August-2026-Pay-Per-Call-Payout-Benchmark-for-417983-ZIP-Service-Rows/6a7de4e775104c0002c9a2c6)
- One vendor claims payouts of $15-$258 per call for urgent repairs (unsourced, broad) — [Elite Leads Alliance](https://eliteleadsalliance.it.com/)

Benchmark against Google Local Services Ads (the alternative channel and a traffic source for arbitrage):
- Lead Smart's own LSA campaign data, Q2 2026: roofing LSA cost per lead $101.15 (up from mid-$60s a year earlier); HVAC $50.21; plumbing $66.17 (down 5.6%); headline claim that Google lead costs rose up to 69% in a year — [Lead Smart via Davis Journal](https://pr.davisjournal.com/article/Lead-Smart-Inc-Google-Lead-Costs-Rose-Up-to-69percent-in-a-Year-What-the-Same-Calls-Pay-Publishers/6a9d61185e47130002855182)

Conversion/economics:
- Service Direct: approximately 50%-60% of billable leads turn into booked appointments, depending on service category — [Service Direct marketplace info sheet](https://support.servicedirect.com/hubfs/Product%20Marketing/Info%20Sheets%20and%20User%20Guides/Service%20Direct%20Marketplace%20for%20Clients/ServiceDirect-Marketplace-Clients-Success-HomeServices.pdf)
- Angi: revenue per lead fell 5% YoY in Q1 2026 and rose 1% in Q2 2026 — [Panabee Q1 2026](https://www.panabee.com/news/angi-earnings-q1-2026); [MarketBeat Q2 2026](https://www.marketbeat.com/instant-alerts/angi-q2-earnings-call-highlights-2026-08-05/)

### Inferences
- Comparing Lead Smart publisher payouts ($33-$42 for plumbing/HVAC/roofing) with Service Direct's contractor price bands ($60-$550) and LSA CPLs ($50-$101) implies the publisher typically receives well under the contractor's price; the gap covers network margin, non-billable calls and credits. These are different companies' data sets, so the implied spread is illustrative only, not a measured take rate.
- At a 50-60% booking rate, a $100 plumbing call costs $170-$200 per booked appointment; economics work for tickets of several hundred dollars and up, which is why low-ticket categories (locksmith, appliance repair, towing) sit at $14-$75 and high-ticket ones (roofing, water damage, HVAC replacement) carry the top prices and are moving to per-appointment billing.
- Pricing is ZIP-level and auction-driven (Lead Smart benchmarks by ZIP-service row; Service Direct bids by ZIP), so a single national "payout per vertical" is a simplification.

### Gaps
- No citable 2026 pay-per-call figure for towing or local legal services was found; no separate locksmith pay-per-call median (only the $15 low-end lead price and $15-$75 / $25-$60 ranges).
- No independent (non-vendor) data on contractor close rates from booked appointment to paid job, or on contractor ROI/CAC by trade.
- Lead Smart's methodology and sample could not be reviewed (site unreachable); it reports its own network's data.

## 4. How do "rank and rent" sites and Google Business Profile lead-gen operators feed calls into these networks?

### Takeaway
Rank-and-rent operators build generic local-service websites and Google Business Profiles that rank organically or in the map pack, put a tracking number on them, and either rent the asset to one contractor for a flat fee or sell the calls per call (directly or into networks via ping APIs such as eLocal's). Google treats lead-gen/fake listings as policy violations, has sued operators, and ran a large suspension wave in spring 2026.

### Cited Findings
- Google's lawsuit defines rank and rent as creating a business website and associated Business Profile to sell leads, rent the profile to a business for a set price, or sell the profile and website; the defendant was allegedly associated with more than 350 fake Business Profiles since mid-2021, with fake reviews posted to make them look legitimate; Google sought treble damages and attorneys' fees — [Search Engine Journal](https://www.searchenginejournal.com/google-lawsuit-rank-and-rent/489666/)
- Networks openly buy this traffic: eLocal runs an affiliate pay-per-call rev-share programme with a ping API returning a price and billable duration per call; Service Direct publishes guidance for publishers selling calls to it — [eLocal Call Ping API](https://elocal.com/docs/call_api/); [Service Direct blog](https://blog.servicedirect.com/what-to-expect-selling-calls-to-service-direct)
- Reported 2026 enforcement: stricter enforcement against keyword-stuffed business names and fake reviews from an April rollout; starting around 27 April, thousands of Business Profile listings reportedly disappeared from Maps without warning (third-party agency account) — [The Ad Firm](https://www.theadfirm.net/googles-google-business-profile-crackdown-what-small-businesses-need-to-fix-now/)
- Common suspension triggers: spammy/keyword-stuffed names, virtual-office addresses; a suspension on one Google account usually takes down all listings in that account; Google rarely states which violation triggered it — [BrightLocal suspension research](https://www.brightlocal.com/research/google-business-profile-suspensions/); [The Home Service Marketer](https://thehomeservicemarketer.beehiiv.com/p/google-business-profile-suspension-risk-factors-656726126533419f)
- Suspension waves are also attributed to Google support failures affecting legitimate businesses — [Near Media](https://nearmedia.co/waves-of-gbp-suspensions-reflect-google-support-failures)
- Older context: reporting on millions of fake Google Maps listings harming real businesses and consumers (2019) — [Search Engine Land](https://searchengineland.com/millions-of-fake-google-maps-listings-hurt-real-business-and-consumers-318629)
- Paid arbitrage is the other feeder: publishers buy Google LSA / Performance Max traffic and resell calls; Lead Smart frames its payout data against LSA lead costs, which it says rose up to 69% in a year — [Lead Smart, 20 Aug 2026](https://leadsmartinc.com/news/press-local-services-ads-performance-max-payout-data-2026)

### Inferences
- Rank-and-rent is a supply-side dependency on Google: an operator's entire call inventory can vanish with one account suspension, so networks buying from such publishers have volatile supply.
- Rising LSA costs ($50-$101 per lead) against publisher payouts of $33-$42 compress paid-arbitrage margins, pushing publishers toward organic/GBP assets, which is exactly where Google enforcement is tightening.
- A consumer app with its own brand and repeat users is a first-party demand source that avoids this dependency; that is a structural advantage over network publishers.

### Gaps
- No quantitative data on what share of network call volume originates from rank-and-rent/GBP assets versus paid search.
- Typical flat rental prices for rank-and-rent sites were not found in a citable source.
- Google's current written Business Profile guideline text on lead-generation listings was not retrieved directly.

## 5. Quality/fraud problems and regulatory issues (TCPA, FCC one-to-one consent status, recording consent, Google policies)

### Takeaway
Disputes centre on short calls, duplicates, spam/robocalls and wrong-service callers, managed through duration thresholds, buffer windows, repeat-caller rules and credit programmes. On regulation, the FCC one-to-one consent rule was vacated on 24 January 2025 and never took effect; the "revoke-all" consent revocation rule has been repeatedly delayed (reportedly to 31 January 2027); AI-generated voices have counted as "artificial or prerecorded voice" under the TCPA since February 2024.

### Cited Findings
Quality and fraud:
- Fraud types listed by vendors: robocalls, duplicate callers, and short calls engineered to pass duration thresholds without being genuine leads; affiliate fraud (publishers attracting illegitimate leads or hiding sources) is described as the most common type — [CallScaler](https://callscaler.com/blog/call-tracking-for-pay-per-call); [Anura](https://www.anura.io/blog/topic/call-fraud); [Invoca on affiliate fraud](https://www.invoca.com/blog/4-types-of-affiliate-fraud-performance-marketers-need-to-know-about)
- The billable-duration threshold is described as the driver of most dispute volume; a threshold/buffer set too low means buyers pay for calls that would have disqualified anyway — [Elevarus](https://elevarus.com/pay-per-call-buffer-time-settings-by-vertical/)
- Platforms provide formal dispute workflows for spam, bot traffic and duplicates — [Dialics help centre](https://dialics.com/help-center/disputes/how-to-create-and-track-a-call-dispute-as-a-buyer/); call deduplication by caller ID is a standard feature — [Phonexa](https://phonexa.com/blog/what-is-call-deduplication/)
- Repeat-caller rules can fail: an Invoca community thread reports repeat caller IDs still being paid despite a no-payout-on-callback-within-X-days rule — [Invoca community](https://community.invoca.com/t5/solutions/repeat-caller-payout-conditions-corrections/ta-p/4301)
- eLocal bills calls that rang 10+ seconds, including calls the buyer declined or hung up on; credits for invalid calls go to account balance on approval — [eLocal help](https://help.elocal.com/features/valid-invalid-calls-leads/)
- Google LSA: automated review credits junk leads (earlier reporting: every charged lead reviewed within 72 hours); Google says it can continue evaluating a lead for 30 days and issue a later credit; the Oct 2026 missed-call change was announced without a stated dispute process — [Search Engine Roundtable](https://seroundtable.com/google-local-service-ads-how-leads-work-42259.html); [PPC Land](https://ppc.land/google-lsa-advertisers-face-missed-call-charges-from-october-1/)
- Businesses with Google Business Profiles face rising robocall scams impersonating Google — [Search Engine Land](https://searchengineland.com/google-business-profile-robocall-scams-increasing-431166)

Regulation:
- One-to-one consent: in Insurance Marketing Coalition v. FCC, the Eleventh Circuit on 24 January 2025 vacated the one-to-one consent requirement and the "logically and topically related" requirement of the FCC's December 2023 order as exceeding FCC authority under the TCPA, and remanded; the FCC had the same day postponed the effective date to 26 January 2026 — [Morrison Foerster](https://www.mofo.com/resources/insights/250130-eleventh-circuit-vacates-fcc-s-tcpa-one-to-one-consent-rule); [Hudson Cook](https://www.hudsoncook.com/article/fccs-new-robocall-one-to-one-consent-standard-postponed-by-fcc-and-vacated-by-court-on-eve-of-effective-date/)
- Result: the lead-gen standard reverted to prior express written consent without the one-to-one constraint; no 2026 FCC action reinstating it was found — [ComplianceHub](https://compliancehub.wiki/tcpa-2026-consent-revocation-one-to-one-rule-vacated-compliance/)
- Consumer advocates criticised the vacatur as denying relief from unwanted telemarketing — [NCLC](https://www.nclc.org/consumers-denied-relief-from-unwanted-telemarketing-calls-after-federal-court-scraps-consent-rule/)
- Consent revocation ("revoke-all") rule: first delayed to 11 April 2026; on 6 January 2026 the FCC further extended its waiver, so revocation can still be applied per brand/call type; other revocation requirements (e.g. honouring standard opt-out keywords) are unaffected; in October 2025 the FCC issued a further notice proposing to amend the rule — [Consumer Financial Services Law Monitor, Jan 2026](https://www.consumerfinancialserviceslawmonitor.com/2026/01/fcc-further-extends-effective-date-for-tcpa-revoke-all-rule/); [Privacy World, Oct 2025](https://www.privacyworld.blog/2025/10/fcc-proposes-amendments-to-tcpa-consent-revocation-rules-proposed-changes-to-dnc-rules-deleted-from-final-text/). A single compliance blog gives the new date as 31 January 2027 (unconfirmed by a second source) — [ComplianceHub](https://compliancehub.wiki/tcpa-2026-consent-revocation-one-to-one-rule-vacated-compliance/)
- AI voices: FCC Declaratory Ruling 24-17 (adopted 2 Feb 2024, released 8 Feb 2024) holds AI-generated voices are "artificial or prerecorded voice" under the TCPA, so outbound calls using them require prior consent — [FCC](https://www.fcc.gov/document/fcc-makes-ai-generated-voices-robocalls-illegal); [Hunton](https://www.hunton.com/privacy-and-cybersecurity-law-blog/fcc-issues-declaratory-ruling-that-tcpa-applies-to-ai-generated-voice-calls)
- In August 2024 the FCC proposed requiring disclosure of intended AI-generated call use when obtaining consent; adoption status was not confirmed — [BABL AI](https://babl.ai/fcc-proposes-making-ai-generated-voice-robocalls-illegal/)
- The FTC's 900-Number ("Pay-Per-Call") Rule is a different thing: it governs caller-paid premium-rate services, not performance marketing — [FTC](https://www.ftc.gov/sites/default/files/paypercallrule.pdf)

### Inferences
- Pure inbound pay-per-call (consumer dials the number) carries far less TCPA exposure than form-lead models where the buyer calls the consumer back; the TCPA rules above bite on outbound calls/texts and AI-voice callbacks. This is a major reason call-based models survived the 2024-2025 consent turmoil.
- An app that itself places an AI-voiced outbound call or callback to a consumer in the US would fall under the AI-voice ruling and need prior consent.
- Billing definitions that charge for unanswered or declined calls (eLocal 10 s, Google 20 s missed-call rule) are a recurring source of contractor resentment and a positioning opportunity for a fairer middleman.

### Gaps
- Call recording consent (one-party vs all-party states, e.g. California) was not researched to a citable source in this session; needs separate verification.
- No published industry dispute/return-rate benchmark was found.
- A claimed "5 June 2026" FCC AI ruling appears in blogs but could not be verified and seems to recycle the 2024 ruling; treat as unconfirmed — [dev.to post](https://dev.to/alfredo_romero_fc4afdcb68/tcpa-2026-the-new-compliance-rules-every-ai-voice-agency-must-follow-1a4).
- Contractor-forum (buyer-side) complaints were not directly sampled; only eLocal's self-hosted testimonials surfaced, which are self-selected — [eLocal reviews](https://elocal.com/plumber/elocal-reviews).

## 6. How are AI voice agents and AI call qualification changing pay-per-call in 2025-2026?

### Takeaway
AI voice agents are being inserted in front of the routing layer to answer, qualify (service, ZIP, urgency) and then transfer or book, at a claimed cost of roughly $0.07-$0.31 per minute, enabling "pay only for qualified calls" and per-appointment pricing. Marketplaces (Justdial, Angi, Marchex) are publicly attributing matching and monetisation gains to AI, while Google's missed-call billing makes instant AI answering nearly mandatory for contractors.

### Cited Findings
- Third-party AI qualification layers market themselves as working before or alongside Ringba, Retreaver, Phonexa and CallRail to pre-qualify every call before it reaches a buyer — [SkipCalls](https://skipcalls.com/pay-per-call-ai-qualification); [CallGrid AI voice agent](https://callgrid.com/ai-voice-agent)
- Cost claims: AI qualification about $0.10-$0.15 per minute (vendor estimate); Retell lists $0.07-$0.31 per minute pay-as-you-go — [SkipCalls](https://skipcalls.com/pay-per-call-ai-qualification); [Retell AI](https://www.retellai.com/use-cases/ai-lead-qualification)
- Phonexa offers AI Call Agents for initial qualification and routing before human hand-off; Ringba, per a May 2026 competitor article, has no native AI voice answering or conversation intelligence — [Phonexa](https://phonexa.com/blog/ringba-review/); [CallRail](https://www.callrail.com/blog/ringba-alternatives)
- Voice AI described as "overhauling" pay-per-call campaigns (Aug 2025 vendor piece) — [Phonely](https://www.phonely.ai/blogs/pay-per-call-marketing-campaigns-get-overhauled-with-voice-ai)
- Marchex positions its platform around generative AI features (call summarisation, sentiment) and, with Archenia, as an "AI-driven customer acquisition and outcome optimization platform" — [Marchex release](https://investors.marchex.com/news-releases/news-release-details/marchex-announces-fourth-quarter-and-full-year-2025-results-and); [Panabee summary](https://www.panabee.com/news/marchex-earnings-2025-annual)
- Justdial management says AI voice agents help understand user intent and qualify leads, producing stronger buyer-seller matches; Q1 FY27 revenue growth of about 10% was attributed to AI-led momentum — [Indian Television](https://indiantelevision.com/mam/justdial-begins-fy27-with-10-per-cent-revenue-growth-on-ai-led-momentum/)
- Google LSA's 20-second missed-call billing from 1 Oct 2026 is being used by AI-receptionist vendors as the reason to deploy AI answering — [Avoca](https://www.avoca.ai/blog/google-lsa-missed-call-charges-2026)
- Top-paying home-service categories now price per appointment rather than per call duration (Aug 2026) — [Lead Smart via Portland Tribune](https://pr.portlandtribune.com/article/Lead-Smart-Inc-Publishes-August-2026-Pay-Per-Call-Payout-Benchmark-for-417983-ZIP-Service-Rows/6a7de4e775104c0002c9a2c6)

### Inferences
- AI qualification replaces the crude duration proxy with content-based qualification (did the caller actually need a plumber in this ZIP?), which should reduce disputes and supports the shift from pay-per-call to pay-per-booked-appointment.
- At $0.07-$0.31 per minute, a 2-3 minute AI qualification costs under $1 against $30-$250 call values, so the cost is negligible relative to the dispute/credit savings.
- Value is moving from "who owns the phone number" to "who owns the qualification and booking step" — the position a consumer-facing app naturally occupies.

### Gaps
- No independent data on AI-qualified call conversion uplift, consumer drop-off when greeted by AI, or dispute-rate reductions; all claims are vendor marketing.
- No evidence found on whether Ringba has shipped native AI since May 2026.

## 7. Is pay-per-call used outside the US (India, Middle East, Pakistan, UK)? Justdial, Sulekha models

### Takeaway
Outside the US, true per-qualified-call auctions are rare; the dominant models are subscription/paid-listing packages (Justdial, Checkatrade) and prepaid lead credits with shared leads (Sulekha, Bark). Justdial is the large-scale proof point: about 631K paid campaigns at roughly INR 19K average revenue per campaign (analyst figure; period basis unverified). No citable data was found for Pakistan or the Gulf.

### Cited Findings
- Justdial (India): Q1 FY27 (quarter ended 30 Jun 2026) operating revenue Rs 327.5 crore, +9.9% YoY and +6.6% QoQ from Rs 307.2 crore; shares rose 15-20% on the result — [Indian Television](https://indiantelevision.com/mam/justdial-begins-fy27-with-10-per-cent-revenue-growth-on-ai-led-momentum/); [Business Today](https://www.businesstoday.in/markets/stocks/story/just-dial-shares-jump-nearly-15-on-q1-fy27-earnings-details-here-542458-2026-07-13)
- Justdial Q4 FY26 operating revenue Rs 307 crore; FY26 revenue +6.3% YoY — [Outlook Business](https://www.outlookbusiness.com/corporate/just-dial-q4-results-operating-revenue-hits-307-cr-profit-dips-on-treasury-drag)
- Justdial paid campaigns: 631,530 as of March 2026 (+3%); 629,180 in the December 2025 quarter (+4.7% YoY); active listings 56.1 million (+13.0% YoY) — [Business Standard](https://www.business-standard.com/markets/capital-market-news/just-dial-reports-37-drop-in-q4-pat-126041400229_1.html); [Trendlyne Q3 FY26](https://trendlyne.com/posts/5482420/q3fy26-quarterly-result-announced-for-just-dial-ltd)
- Justdial average revenue per campaign INR 19,363 in Q1 FY26 (+1.4% YoY), per a JM Financial note (period basis not stated in snippet; verify whether annualised) — [JM Financial via Business Standard](https://bsmedia.business-standard.com/_media/bs/data/market-reports/equity-brokertips/2025-07/17526567150.65575900.pdf)
- Justdial's paid package bundles qualified lead generation, catalogues, "Trusted"/"Verified" badges, rating certificates, banners and priority visibility; it reports as a single segment (search and related services) — [Lokmat Times](https://www.lokmattimes.com/business/justdial-strengthens-its-all-in-one-business-platform-to-support-local-merchants/amp)
- Sulekha (India): sells leads to service providers through paid packages delivered via partner app/dashboard; a vendor knowledge base describes prepaid lead credits consumed per lead, with each requirement sent to a limited number of matching providers; a reseller claims roughly INR 150-800 per lead depending on category and geography (unverified against Sulekha) — [LeadSquared](https://www.leadsquared.com/learn/marketing/sulekha-leads/); [Bison knowledge base](https://knowledgebase.bison.co.in/view_article.php?id=485); [SmartAds](https://smartads.in/services/digital/sulekha-digital-advertising)
- UK: Checkatrade publishes only its entry tier (GBP 30 + VAT) with a 12-month minimum term; Bark sells each lead to up to 5 professionals; only 3 of 10 UK trade platforms publish full pricing; a vendor worked example puts a plumber on Checkatrade mid tiers at about GBP 100 membership plus 15 leads at about GBP 20 each, about GBP 400/month — [Whito UK trade directory costs](https://whito.co.uk/trades/research/uk-trade-directory-costs/)
- UK pay-per-call tooling exists (Phonexa UK markets pay-per-call routing and fraud prevention software) — [Phonexa UK](https://phonexa.uk/call-logic/pay-per-call/)
- UAE: one Dubai-focused source discusses Google Local Services Ads with caveats on availability and eligibility in the UAE (weak source) — [Clozer](https://clozer.pages.dev/blog/google-local-services-ads-dubai.html)

### Inferences
- In India, the UK and similar markets, providers are sold visibility plus a stream of shared leads on prepaid/subscription terms; the provider bears lead-quality risk. The US pay-per-call model, where the buyer pays only for a call that meets a quality bar, is a differentiator in those markets rather than an established norm.
- Justdial's roughly 1.1% paid penetration (631K paid campaigns on 56.1M listings, computed from the cited figures) shows how small the paying share of local businesses is under a subscription model; a pure performance model could reach providers unwilling to prepay.
- Lead prices in India (INR 150-800, about USD 2-10 if the reseller figure is right) are one to two orders of magnitude below US call prices, so unit economics must rest on volume, automation (AI qualification) and low-cost channels such as WhatsApp rather than per-call telephony auctions.

### Gaps
- No citable information on pay-per-call or local-lead marketplaces in Pakistan or the Gulf (UAE/Saudi) was found; no data on Urban Company commission in this session.
- Sulekha's official pricing and current scale were not found; the per-lead figure is from a reseller.
- Bark's per-lead credit prices were not found in a citable source.

## 8. What could a new mobile app acting as a middleman between customers and local service providers borrow from pay-per-call?

### Takeaway
The transferable ideas are: charge providers only on a clearly defined, verifiable billable event; auction or price demand by category and locality; mask numbers so every contact is tracked; dedupe and auto-credit bad contacts; and use AI to qualify before connecting, ideally billing per booked appointment. The app's own consumer base avoids the Google-dependency and fraud problems that affect third-party publishers.

### Cited Findings
- Provider-set bids by service area with pay-only-for-billable-leads is an established, accepted contractor model (Service Direct) — [Service Direct blog](https://blog.servicedirect.com/what-to-expect-when-buying-hvac-leads-from-service-direct)
- Real-time auction among buyers in a 2-5 second window with highest bidder winning is proven technology — [Ringba](https://www.ringba.com/blog/pay-per-call/real-time-bidding-for-calls)
- 50-60% of billable leads becoming booked appointments is the benchmark a new marketplace should match or beat — [Service Direct info sheet](https://support.servicedirect.com/hubfs/Product%20Marketing/Info%20Sheets%20and%20User%20Guides/Service%20Direct%20Marketplace%20for%20Clients/ServiceDirect-Marketplace-Clients-Success-HomeServices.pdf)
- Highest-value categories are already priced per appointment rather than per call duration — [Lead Smart via Portland Tribune](https://pr.portlandtribune.com/article/Lead-Smart-Inc-Publishes-August-2026-Pay-Per-Call-Payout-Benchmark-for-417983-ZIP-Service-Rows/6a7de4e775104c0002c9a2c6)
- Requiring the consumer to choose the provider (Angi homeowner choice) cut network leads 78% but coincided with improving monetisation and EBITDA — [Angi IR](https://ir.angi.com/node/13006/html); [finsee Q3 2026](https://finsee.ai/earnings/angi/2026/q3/en/)
- Automated crediting of junk leads (Google: review within 72 hours, evaluation up to 30 days) and credit-to-balance programmes (eLocal) are the standard dispute remedies — [Search Engine Roundtable](https://seroundtable.com/google-local-service-ads-how-leads-work-42259.html); [eLocal help](https://help.elocal.com/features/valid-invalid-calls-leads/)
- Shared leads sold to up to 5 professionals (Bark) and prepaid credits (Sulekha) are the incumbent models in the UK and India — [Whito](https://whito.co.uk/trades/research/uk-trade-directory-costs/); [Bison knowledge base](https://knowledgebase.bison.co.in/view_article.php?id=485)

### Inferences
- Billable event design: define it by outcome (connected and qualified conversation, or booked appointment) rather than by raw duration; publish the rule and auto-credit violations. Avoid charging for unanswered or declined contacts, which is the most resented incumbent practice.
- Exclusive, consumer-chosen connections command higher prices and fewer disputes than shared leads; start exclusive.
- Use masked/in-app calling and chat so the platform has the same attribution, duration and recording data a call-tracking platform has, enabling dedupe (same customer, same provider, within N days is not re-billed, mirroring Google's 15-day rule).
- Price by category and locality, letting providers set a bid or accept a rate card; low-ticket urgent services (locksmith, appliance repair) sit near the bottom of the price range and roofing/HVAC/water damage near the top, a ratio of roughly 5-10x in US data.
- Put AI qualification in front of the hand-off (service type, location, urgency, budget) at a cost of cents per minute; it is the cheapest way to raise the booked-appointment rate and justify per-appointment pricing.
- Surplus demand the app cannot fulfil with its own providers could, in the US, be sold into networks via ping APIs (eLocal-style) as a secondary revenue line; conversely, networks are a way to buy provider-side demand coverage early. Outside the US this outlet largely does not exist.
- Regulatory posture: keep contact consumer-initiated (inbound) where possible; any AI-voiced or automated outbound contact to US consumers needs prior consent under the TCPA.

### Gaps
- No evidence on how consumers in South Asia or the Gulf respond to masked-number or AI-qualified calls, or on provider willingness to pay per outcome there.
- No verified network take rate to benchmark a commission against; this must be estimated or sourced from the adjacent marketplace research.
