# Google Maps / Google Business Profile / Local Services Ads as the de facto local-services directory (state as of Nov 2026)

Research-method note for the report writer: page fetches were blocked in this session (brightlocal.com, mediagistic.com failed to resolve; network allowlist), so every finding below rests on search-result summaries of the linked pages, not on a full read of the page. Where a number came only from a vendor blog, a press release or a single secondary source, it is flagged "(unverified)" or "(single source)". Nothing below was taken from Google's live Help Center text except the chat/call-history page and the Maps Platform policy pages, which were quoted in search results.

## 1. How discovery works on Google Maps / local pack (ranking, reviews, user journey, Google's share)

### Takeaway
Google ranks local results on three stated factors (relevance, distance, prominence); practitioners say the primary GBP category, searcher proximity and keywords in the business name dominate, with reviews (count, rating, and increasingly recency) as the second-biggest lever. Google is still the top place consumers look for local businesses, but 2026 survey coverage shows its share slipping while AI tools and Apple Maps rise.

### Cited Findings
- Google states local results are based mainly on relevance, distance and prominence; actual weights are not public. — [Whitespark Local Search Ranking Factors](https://whitespark.ca/local-search-ranking-factors/)
- Whitespark's 2026 survey (reported as 47 local SEO experts, 187 factors): primary GBP category ranked #1, with proximity to the searcher and keywords in the business name close behind. — [Whitespark](https://whitespark.ca/local-search-ranking-factors/); summary at [Search Lab Digital](https://searchlabdigital.com/blog/just-released-2026-local-search-ranking-search-factors/)
- Third-party summaries of the 2026 Whitespark survey give local-pack group weights of roughly GBP signals 32%, review signals 20%, on-page 15%; eight of the top ten individual factors sit inside the profile. For local organic results on-page signals lead (~33%). These percentages come from secondary summaries that do not fully agree (unverified against the primary report). — [StoreRocket](https://storerocket.io/learn/local-seo-ranking-factors); [Loganix](https://loganix.com/google-local-search-ranking-factors/)
- Review recency is rising in importance: ranked 20th in the 2023 survey, but placed in the top 5 by at least one contributor in 2025. — [Whitespark blog](https://whitespark.ca/blog/7-local-search-ranking-factors/)
- BrightLocal Local Consumer Review Survey 2026 (published 11 Feb 2026; 1,002 US adults): 85% more likely to use a business after reading positive reviews; 77% put off by negative ones; 74% only care about reviews from the last three months; 47% will not use a business with fewer than 20 reviews. — [BrightLocal](https://www.brightlocal.com/research/local-consumer-review-survey/); [PinMeTo summary](https://www.pinmeto.com/news/brightlocal-local-consumer-review-survey-2026/)
- Same survey, per BrightLocal's own summary: "Google and Facebook remain top"; Apple Maps usage nearly doubled from 14% (2025) to 27% (2026); local news sites fell from 48% to 29%. — [BrightLocal](https://www.brightlocal.com/research/local-consumer-review-survey/)
- Secondary coverage of the same survey claims Google's share of local-business discovery fell from 83% to 71% and AI tools rose from 6% to 45% (third-largest channel); a March 2026 follow-up reportedly had ChatGPT at 31% of consumers and Google AI Mode at 23%. Single third-party analysis, not confirmed on BrightLocal's pages (unverified). — [Digital Applied](https://www.digitalapplied.com/blog/online-review-statistics-2026-consumer-trust-data)
- Widely repeated figure: 46% of Google searches carry local intent (attributed to Google; old and of uncertain provenance). Also cited: mobile drives 73% of initial local queries; 31% of consumers use AI monthly for local recommendations; ~76% of local searchers visit a business within 24 hours. All from marketing compilations (unverified). — [QuickSEO](https://quickseo.ai/blog/local-seo-in-2026-46-percent-of-searches-have-local-intent-50-more-stats-smbs-should-know); [Digital Applied](https://digitalapplied.com/blog/local-seo-statistics-2026-data-points)
- eMarketer headline (2026): Google holds local-search dominance while consumers compare several sources before buying. — [eMarketer](https://www.emarketer.com/content/google-holds-local-search-dominance-consumers-compare-sources-before-buying)

### Inferences
- The journey is: query ("plumber near me") -> LSA unit at top (paid, badge) -> local pack of ~3 / Maps list -> profile (rating, review count, recent reviews, photos, hours) -> call / website / message / booking link. The contact happens off Google's record: Google hands the customer to a phone call or website and has no view of quote, job, price or outcome. That hand-off is the gap a middleman app can occupy.
- Because proximity and category dominate and the pack shows only about three results, a provider's visibility is geographically narrow and winner-takes-most; new or home-based providers with few reviews are structurally disadvantaged (47% of consumers want 20+ reviews; 74% want reviews under three months old).
- Consumers increasingly cross-check several sources, so a new app does not need to replace Google at the top of the funnel; it has to be the place where the comparison and the transaction finish.

### Gaps
- No reliable, primary-sourced figure for "share of local-service searches that go through Google". The 83%->71% figure is unverified secondary coverage; the 46% local-intent figure is old and unsourced.
- Could not open the Whitespark 2026 report itself to confirm exact group weights.
- No home-services-specific breakdown (as opposed to all local businesses, which is restaurant-heavy).

## 2. Google Business Profile: what is free, features, and 2024-2026 changes (chat, call history, Q&A, Gemini, Ask Maps, AI Mode)

### Takeaway
GBP is a free listing whose native communication features have been steadily removed: chat and call history ended 31 July 2024, the Q&A section was retired in late 2025 in favour of Gemini answers, and in March 2026 Google launched "Ask Maps", a conversational layer that answers from profile data and reviews. Google is turning the directory into an AI answer surface, with less direct provider-customer interaction inside Google and less control for the provider.

### Cited Findings
- Google Help: "As of July 31, 2024, the chat and call history features are no longer available in your Business Profile." New chats stopped 15 July 2024; full removal 31 July 2024. — [Google Business Profile Help](https://support.google.com/business/answer/14919056?hl=en)
- Replacement is partial: for eligible accounts customers can contact the business from the profile via SMS text or WhatsApp (the business adds its own numbers); testing was reported in September 2024. — [Google Business Profile Help](https://support.google.com/business/answer/14919056?hl=en); [Cloodot](https://cloodot.com/blog/google-business-profiles-begin-testing-chat-integration-with-sms-whatsapp)
- One low-authority site claims a second chat/call-history sunset on 31 July 2026; this conflicts with Google's 2024 page and looks like an error (unverified, treat as wrong). — [slashpost.ai](https://slashpost.ai/blogs/google-business-profile/google-business-profile-updates-2026)
- Q&A retired: Google discontinued the Q&A API on 3 Nov 2025 and began deprecating the public Q&A section on 3 Dec 2025, replacing it with an AI-powered "Ask" button. — [Search Engine Roundtable](https://www.seroundtable.com/google-maps-qa-feature-ask-40594.html); [ppc.land](https://ppc.land/google-quietly-kills-q-a-for-an-ai-button-most-wont-use/); dates per [slashpost.ai](https://slashpost.ai/blogs/google-business-profile/google-business-profile-qa-removed-2026)
- Ask Maps: described by Google in March 2026 as a new conversational experience answering complex real-world questions; it draws on profile details and reviews, and if Gemini cannot find a clear answer it will skip or guess. One contractor-marketing source says Ask Maps returns a single recommendation versus the three-result pack (single source). — [BrightLocal](https://www.brightlocal.com/learn/google-business-profile-qa); [Groundset Digital](https://groundsetdigital.pages.dev/blog/ask-maps-google-business-profile-contractors/)
- Gemini app began showing local Maps results as visual cards (photos, ratings, practical details) in December 2025; Gemini can also manage a Business Profile, later extended to multi-location accounts. — [ppc.land](https://ppc.land/gemini-now-manages-your-google-business-profile-with-a-single-tap/); [ppc.land](https://ppc.land/google-business-profile-in-gemini-now-works-for-multi-location-accounts/)
- AI Overviews prevalence on local queries is disputed: a Whitespark 540-query study is cited as ~68% of local business queries overall, but only ~15% of true local-intent queries (local pack appears on ~93%); other studies report ~8% and 12.5% (5 of 40 "near me" searches). Adding a city/suburb or "near me" makes the AI answer step aside more often. — [Whitespark case study](https://whitespark.ca/blog/case-study-the-prevalence-of-ai-overviews-in-local-search/); [ThinkProfits](https://thinkprofits.com/digital-news/maps-pack-still-wins-local-ai-overviews-8-percent/); [Lilach Bullock study](https://www.lilachbullock.com/ai-overviews-local-services-study/) (whose own headline claims an AI answer on 88% of local service searches, illustrating how much results vary by method)
- AI Mode selects businesses differently from the local pack: a June 2026 study (1,120 query executions) found 28.5% of local-pack businesses were invisible in Google AI Mode (press-release study, single source). — [press release](https://smb.elizabethton.com/article/Local-SEO-Data-Study-Finds-285percent-of-Local-Pack-Businesses-Are-Invisible-in-Google-AI-Mode/6a299c6d5f1a39366789142f)
- "AI local packs" reported to cause large visibility drops; a Sterling Sky analysis of 322 US markets is cited as showing 88% of markets lost visibility (secondary report, not verified at source). — [Search Engine Roundtable](https://www.seroundtable.com/google-ai-overview-local-pack-drops-40773.html)
- Ahrefs is cited as finding AI Overviews cut click-through rate by 34.5% on average (general search, not local-specific). — [Search Engine Land guide](https://searchengineland.com/guide/how-ai-is-impacting-local-search)
- A January 2026 press release claims search-query data shows local businesses "losing faith" in GBP (press release, weak). — [ABNewswire via Observer-Reporter](https://stocks.observer-reporter.com/observerreporter/article/abnewswire-2026-1-16-search-query-data-reveals-local-businesses-losing-faith-in-google-business-profile)

### Inferences
- The free GBP listing still gives: name/category/hours/service area, photos, posts, services and products lists, reviews with owner replies, call and website buttons, third-party booking links, and basic performance metrics. What it no longer gives is any native two-way conversation, call log or owner-answered Q&A. In 2026 Google is a pure hand-off: it shows the listing and passes the customer to a phone number, WhatsApp/SMS or a website.
- Google pointing profile messaging to WhatsApp/SMS is an admission that the conversation lives elsewhere; in WhatsApp-heavy markets (South Asia, Middle East) that suits an app that structures the WhatsApp-style conversation (quote, schedule, payment) rather than competing with Google for the listing.
- AI answer layers (Ask Maps, AI Mode, Gemini) compress choice from ~3-20 listings toward one or a few recommendations, and answer from review text. That raises the value of structured, verified provider data (price, availability, licences, completed-job history) that Google does not have.

### Gaps
- Could not verify the current feature list on Google's Help Center directly (fetch blocked); the "what is free" list above is an inference from general knowledge plus the sources, not a quoted Google page.
- No verified data on how many users actually use Ask Maps or AI Mode for hiring service providers.
- No verified study quantifying a decline in GBP calls caused by AI features.

## 3. Local Services Ads: pay-per-lead model, badges, pricing, credits, bidding, complaints

### Takeaway
LSA is Google's pay-per-lead unit above the local pack. In 2025-2026 Google replaced Google Guaranteed/Screened with a single "Google Verified" badge (dropping the money-back guarantee, per trade sources), automated and narrowed lead credits, announced a 1 Oct 2026 lead-charge policy under which some missed and repeat calls are billable, and from August 2026 began migrating LSA into Google Ads as pay-per-lead Performance Max with no manual bidding. Each change shifts lead-quality risk from Google to the provider.

### Cited Findings
- Billing is per lead (phone calls and messages), not per click; this stays true after the Performance Max migration. — [Invoca](https://www.invoca.com/blog/googles-local-services-ads-move-to-performance-max-what-home-services-businesses-need-to-know)
- Badge change: Google Guaranteed, Google Screened and related badges were replaced by a single "Google Verified" badge; trade sources date this to 20 Oct 2025 and say the Google-backed reimbursement (money-back guarantee) went away with it. — [CI Web Group](https://www.ciwebgroup.com/blog/google-replaces-google-guaranteed-with-the-new-google-verified-badge--what-contractors-need-to-know); [Search Engine Roundtable via Pulse](https://www.pulse.bot/digital-marketing/news/google-local-service-ads-verified-section-details-5a679d05-ac3e-4675-b324-5d2e6b05911d/)
- Requirements shifting "verification first" from July 2026. — [TechWyse](https://www.techwyse.com/news/platform-updates/google-local-services-ads-requirements-july-2026)
- Lead credits: manual disputes were replaced by an automated credit system; the "job type not serviced" and "geo not serviced" credit categories were removed, so wrong-job and wrong-location leads are no longer credited. — [Footbridge Media](https://www.footbridgemedia.com/marketing-tips/5-changes-google-local-service-ads-contractors-should-know); [Elevarus](https://elevarus.com/google-local-services-ads-disputes-ranking-2026/)
- Lead charge policy update effective 1 Oct 2026: certain missed calls and subsequent (repeat) calls can count as billable leads even when the business never speaks with the customer. — [Mediagistic](https://www.mediagistic.com/blog/glsa-lead-charge-policy-2026); [Scorpion](https://www.scorpion.co/articles/topics/digital-advertising/google-is-changing-how-local-services-ads-call-l/)
- Migration: from August 2026 Google began moving US home and storefront service LSA advertisers into Google Ads as "Performance Max for pay-per-lead goals"; other categories and markets follow into 2027; the standalone LSA dashboard is being retired; placement stays on Search and Maps only. — [Invoca](https://www.invoca.com/blog/googles-local-services-ads-move-to-performance-max-what-home-services-businesses-need-to-know); [Stacker](https://stacker.com/stories/business-economy/google-local-services-ads-transition-performance-max-what-save-your-0)
- Migration costs to advertisers: historical reports do not carry over (must be exported before the migration date); manual bidding ends and the system sets the price per lead; high- and low-margin services compete under one bid target, which can raise lead cost for low-margin jobs. — [ppc.land](https://ppc.land/google-folds-local-services-ads-into-google-ads-cuts-historical-reports/); [Thrive Agency](https://thriveagency.com/news/how-will-googles-local-services-ads-migration-to-performance-max/); [Surefire Local](https://www.surefirelocal.com/?p=58035)
- Invoca's reading: Google has shifted the cost of lead quality onto the advertiser. — [Invoca](https://www.invoca.com/blog/three-shifts-every-home-services-marketer-needs-on-their-radar-right-now)
- Lead prices: a February 2026 benchmark (SearchLight Digital; 888 contractors, $6.72M spend) put blended home-services LSA cost per lead at ~$53; HVAC ~$51 per lead with a 44% booking rate (409 accounts, $1.52M spend) and ~$116 per booked job. — [Enrich Labs](https://www.enrichlabs.ai/blog/google-local-service-ads-complete-guide-2026); [Elevarus](https://elevarus.com/hvac-lead-generation-cost-per-lead-2026-benchmarks/)
- Market variation: one source says a Manhattan plumber pays $90-$120 per lead versus $25-$40 in rural Iowa; an undated agency list shows estate lawyer ~$45 and personal injury ~$249 per lead (both weakly sourced). — [99 Calls](https://blog.99calls.com/2026/05/07/lsa-cost-per-lead-by-industry-for-service-contractors/); [The Media Captain](https://www.themediacaptain.com/google-local-service-ad-statistics/)
- For comparison, standard Google search ads in home services (LocaliQ; 3,211 US campaigns, Apr 2024-Mar 2025): average cost per lead $90.92; roofing $228.15, plumbing $76.40, HVAC $84.92 (figures via secondary summary). — [PipelineOn](https://pipelineon.com/blog/home-service-marketing-benchmarks-2026/)
- A lead-seller's press release headline claims Google lead costs rose up to 69% in a year (interested party, unverified). — [Lead Smart press release](https://pr.davisjournal.com/article/Lead-Smart-Inc-Google-Lead-Costs-Rose-Up-to-69percent-in-a-Year-What-the-Same-Calls-Pay-Publishers/6a9d61185e47130002855182)

### Inferences
- At ~$53 per lead and a ~44% booking rate, a US home-services provider pays roughly $116-$120 to Google per booked job before doing any work, with no guarantee the customer hires them. That is the benchmark a middleman app's commission or lead fee competes against in the US; it only works on jobs with tickets in the hundreds or thousands of dollars.
- These economics do not translate to low-ticket markets (India, Pakistan), where a plumbing visit is a few dollars; LSA is in any case limited to a set of countries and verticals. Google has no paid lead product tuned to low-ticket services there.
- The loss of the money-back guarantee means Google's badge is now an identity/licence check, not a job-outcome promise. Outcome protection (escrow, redo guarantee, dispute resolution) is an open differentiator.
- Providers' complaints fall into a clear pattern: paying for leads outside their job type or area, paying for calls they never answered, no manual bid or dispute control, and loss of historical data. A provider-friendly charging model (pay on accepted/completed job) is a direct counter-position.

### Gaps
- "Direct business search" charges (Google charging for leads where the customer searched the business by name): no source found in this session. From recollection only, Google began charging for these in LSA around late 2023/2024; this needs verification before use.
- Could not read Google's own LSA Help pages for exact wording of the Oct 2026 lead-charge policy or the automated credit rules.
- No LocaliQ/WordStream LSA-specific 2026 benchmark by vertical was found; the vertical numbers are from agencies and vendors.
- No direct quotes from Reddit/contractor forums were retrieved; provider sentiment here is via agency and vendor commentary.
- Current country/vertical availability of LSA (including whether it exists in India, UAE or Saudi Arabia) was not verified.

## 4. Scale: businesses, users, revenue

### Takeaway
Google Maps has more than 2 billion monthly users and is commonly said to hold 200-250 million businesses and places, but Google does not publish local ads or LSA revenue and no credible analyst estimate was found.

### Cited Findings
- Google Maps passed 2 billion monthly active users (attributed to Sundar Pichai on Alphabet's Q3 2024 earnings call; via a marketing compilation). — [On The Map](https://www.onthemap.com/?p=56947)
- Business counts conflict: "250 million businesses and places" on Maps; "more than 200 million businesses have a Google Business Profile"; one outlier says 40 million (all marketing compilations, unverified). — [SQ Magazine](https://sqmagazine.co.uk/google-maps-statistics); [BizIQ](https://biziq.com/blog/google-business-profile-statistics/)
- Google published more than 1 billion reviews in 2025 while blocking or removing over 292 million policy-violating ones, which gives a sense of review throughput. — [Search Engine Roundtable](https://www.seroundtable.com/google-maps-spam-fighting-2025-41176.html)
- Total US local advertising market cited at $182-$184.5 billion across all channels in a 2026 agency guide (not Google-specific; source of the underlying forecast not seen). — [2Point Agency](https://www.2pointagency.com/guides/local-search-advertising-the-complete-2026-guide-to-dominating-nearby-search-results/)

### Inferences
- Review volume (~1 billion published per year) and 13 million fake profiles removed per year (section 5) suggest the "200M+ businesses" order of magnitude is plausible.

### Gaps
- No reliable estimate of Google local ads revenue or LSA revenue was found; Alphabet does not break it out. An "$8 billion in annual sales" figure on a contractor blog is unsourced and should not be used.
- The 2 billion MAU figure was not checked against the earnings-call transcript.
- GBP adoption among small businesses is unknown: sources give 35% and 82%, which cannot both be right.

## 5. Known problems and regulatory action

### Takeaway
Fake listings and fake reviews are an industrial-scale problem that Google fights mostly with automation (292M reviews and 13M fake profiles removed in 2025), and urgent-service categories such as locksmiths are the worst hit. Regulators are now active: UK CMA undertakings (Jan 2025), FTC Consumer Review Rule enforcement (warning letters Dec 2025, a home-services case in 2026), and a €460M EU DMA fine for search self-preferencing (July 2026).

### Cited Findings
- 2025: Google blocked or removed over 292 million policy-violating reviews (up 21% year on year), removed over 13 million fake Business Profiles, blocked 79 million inaccurate or unverified edits and restricted more than 782,000 accounts. — [Search Engine Roundtable](https://www.seroundtable.com/google-maps-spam-fighting-2025-41176.html)
- 2024 baseline: 240 million fake reviews, 70 million edits and 12 million fake listings blocked or removed. — [Search Engine Roundtable](https://www.seroundtable.com/google-maps-spam-fighting-2024-39186.html)
- March 2025: Google removed more than 10,000 fake listings and sued an alleged network that created and sold fake business profiles and fake positive reviews; named defendant Yaniv Asayag, owner of Maryland-based Eagle Locksmith / Eagle Services LLC. — [CBS News](https://www.cbsnews.com/news/google-maps-fake-listings-lawsuit-scams/); [IBTimes](https://ibtimes.com/google-sues-maryland-business-owner-over-fake-listings-consumer-data-sales-3767196)
- June 2023: Google sued Ethan QiQi Hu and his businesses GMBEYE and Rafadigital over fake listings and reviews. — [Search Engine Land](https://searchengineland.com/google-files-lawsuit-over-fake-review-scams-428365)
- Google uses Gemini to stop fake edits and review-extortion scams; it shows alerts (US, UK, India) when suspicious five-star reviews are removed and can temporarily suspend reviews on a profile. — [ppc.land](https://ppc.land/google-maps-uses-gemini-to-stop-fake-edits-and-blocks-review-extortion-scams/); [Google blog](https://blog.google/products-and-platforms/products/maps/new-ways-were-protecting-businesses-on-maps/)
- Side effect: automated enforcement has made it harder for businesses to get fake reviews removed by flagging, as most flags get a standard rejection without human review (trade-press claim). — [DesignRush](https://news.designrush.com/google-review-crackdown-agencies-compliance)
- Service-area businesses (hidden address): video verification is the norm; suspensions after address edits and denied appeals are reported on practitioner forums; P.O. boxes and UPS Store addresses are not allowed; overlapping service areas between two profiles trigger verification failures; a February 2026 change to the verification flow can lead to suspension or a forced hidden address if documents do not match. — [Sterling Sky](https://www.sterlingsky.ca/the-google-business-profile-2-hour-rule-is-a-myth-why-your-google-verification-is-actually-failing/); [Search Engine Roundtable](https://www.seroundtable.com/google-business-profile-verification-flow-caution-40991.html); [Local Search Forum](https://localsearchforum.com/threads/suspended-service-area-business-appeal-denied-offered-video-verification-but-link-never-sent-routing-id-dpnb.63331/)
- UK CMA: on 24 Jan 2025 Google signed undertakings on fake reviews: prominent warning alerts on profiles of businesses caught boosting ratings, a compliance officer, and three years of reporting to the CMA. — [GOV.UK](https://www.gov.uk/government/news/cma-secures-important-changes-from-google-to-tackle-fake-reviews)
- On 27 Mar 2026 the CMA opened five new fake/misleading review investigations under the DMCC Act (funeral, food-delivery, automotive sectors), with an update expected September 2026. — [Taylor Wessing](https://www.taylorwessing.com/en/insights-and-events/insights/2026/03/the-cma-steps-up-its-fight-against-fake-reviews)
- FTC Consumer Review Rule: civil penalties up to $53,088 per violation (was $51,744 at the 2024 announcement); first public enforcement step was warning letters in December 2025; in 2026 the FTC and DOJ filed a complaint against a home-services company alleging purchased fake reviews and misappropriated images of real people. — [Benesch](https://www.beneschlaw.com/insight/five-stars-zero-tolerance-ftc-turns-up-enforcement-under-consumer-review-rule/); [Venable](https://www.venable.com/insights/publications/2025/12/ftc-signals-heightened-enforcement-of-new); [Global Policy Watch](https://www.globalpolicywatch.com/2026/06/ftc-and-doj-continue-focus-on-consumer-reviews-rule-with-complaint-against-premium-home-service/)
- EU DMA: on 23 July 2026 the European Commission fined Google €460 million for self-preferencing in Google Search (shopping, hotels, transport, sports results named) plus €430 million over Play steering (€890M total), with 60 days to comply or face periodic penalties of up to 5% of worldwide turnover; dialogue continues on applying the decision to AI Overviews and AI Mode. Local search was part of the original complaint but is not named in the official finding. — [European Commission press release](https://europa.eu/newsroom/ecpc-failover/pdf/ip-26-1670_en.pdf); [ppc.land](https://ppc.land/eu-fines-google-890-million-euros-and-gives-it-60-days-to-fix-search/)

### Inferences
- Structural weaknesses of Google as a hiring venue, which follow from the product design described in sections 2-3: no price display or quote comparison, no availability, no job record, no payment or escrow, no outcome guarantee since the Guaranteed badge ended, reviews not tied to a verified transaction, and listings that can be faked. A middleman app that verifies identity, ties every review to a paid job and holds payment addresses each of these.
- Any app that hosts reviews falls under the FTC rule (US) and the DMCC Act (UK); transaction-verified reviews are both a trust feature and a compliance defence.
- The DMA decision may over time force Google to give rival vertical services more room in EU results, but there is no evidence yet of a concrete change to local results.

### Gaps
- No source found specifically on "lead-gen spam listings" (fake local listings that resell calls) beyond the locksmith lawsuit.
- No sourced consumer-harm figure for scams via fake Maps listings.
- Whether the Commission's 60-day compliance deadline (late Sept 2026) was met, and any appeal, was not checked.
- An unverified site claims five FTC settlements totalling $27.4M in April 2026; no law-firm or FTC source corroborated it, so it is excluded.

## 6. Competing discovery surfaces (US and emerging markets)

### Takeaway
In the US, Facebook, Apple Maps (27% usage in 2026, up from 14%) and AI assistants are the fastest-moving alternatives, and Yelp has turned itself into a data supplier to ChatGPT. In India Justdial remains a very large paid directory (about 193 million quarterly unique visitors, 56 million listings), while in Pakistan and the Gulf the evidence, which is thin, points to word of mouth and WhatsApp/Facebook referrals with Google Maps as a first shortlist.

### Cited Findings
- Apple Maps usage for local business research rose from 14% (2025) to 27% (2026); Google and Facebook remain the top two. — [BrightLocal](https://www.brightlocal.com/research/local-consumer-review-survey/)
- Yelp licensed reviews, photos and business information to OpenAI for ChatGPT local recommendations (Axios, 23 July 2026); Yelp also supplies Apple Maps and Yahoo; terms undisclosed and non-exclusive; reported as covering ~330 million reviews. — [Axios](https://axios.com/2026/07/23/yelp-reviews-chatgpt-geo-partnership); [Search Engine Land](https://searchengineland.com/openai-yelp-deal-483326); [TechWyse](https://www.techwyse.com/news/platform-updates/yelp-openai-licensing-deal-chatgpt-local-reviews)
- Claims about ChatGPT's local data sources conflict: one vendor says over 70% of ChatGPT local results came from Foursquare (Dec 2024 analysis), another says Bing Places is primary (both vendor blogs, weak). — [Yext](https://www.yext.com/blog/where-do-google-gemini-chatgpt-get-local-business-information); [eClincher](https://www.eclincher.com/articles/business-not-showing-in-chatgpt-google-ai-near-me)
- India, Justdial Q1 FY27 (quarter ended 30 June 2026): 192.9 million quarterly unique visitors (-0.2% YoY, +5.8% QoQ); 86.5% of traffic mobile, 10.6% desktop, 2.9% voice; 56.1 million active listings (+13% YoY). Q4 FY26: 182.4 million visitors, operating revenue ₹307 crore. — [Indiantelevision](https://indiantelevision.com/mam/justdial-begins-fy27-with-10-per-cent-revenue-growth-on-ai-led-momentum/); [Sahi](https://www.sahi.com/blogs/just-dial-q1-fy-27-results-revenue-rises-10-net-profit-jumps-4-yo-y); [Outlook Business](https://www.outlookbusiness.com/corporate/just-dial-q4-results-operating-revenue-hits-307-cr-profit-dips-on-treasury-drag)
- MENA: word-of-mouth recommendations described as homeowners' "safest bet" for choosing providers whose quality is hard to verify. — [Arab News](https://www.arabnews.pk/node/1554181)
- Pakistan: providers are commonly found via numbers forwarded in WhatsApp groups and recommendations from friends and neighbours (vendor blog); in car repair, people still rely on word of mouth but Google Maps has become the "first shortlist"; a founder calls the segment "very disorganised" and says it is hard to find the right people (Dawn, 2017). — [FatafatService](https://fatafatservice.com/blog/why-service-discovery-depends-on-contacts-fatafatservice); [House of Pakistan](https://www.smart.houseofpakistan.com/hidden-growth-opportunities-in-pakistans-car-maintenance-market/); [Dawn](https://www.dawn.com/news/1309231/can-pakistani-home-repair-startup-sukooncompk-live-up-to-its-name)
- Pakistan has had local home-service marketplaces for years (Sukoon, Mahir Company) and is covered in Gulf press as a digitising service economy. — [Khaleej Times](https://www.khaleejtimes.com/supplements/beyond-repairs-how-technology-is-reshaping-pakistans-service-economy); [Mahir Company](https://mahircompany.com/blog/?p=1231)

### Inferences
- Justdial's traffic has been flat for a year while listings grow 13%, which suggests supply is eager to be listed but consumer demand for a pure directory is saturated; this is consistent with Google Maps and WhatsApp absorbing discovery in India.
- In South Asia and the Gulf the real competitor is not Google's ad product but the informal referral graph (WhatsApp groups, neighbours, building watchmen). Google Maps supplies a shortlist and a phone number; the trust decision is made socially. An app must therefore import social proof (referrals, neighbours' completed jobs) rather than rely on star ratings alone.
- AI assistants are becoming a new intermediary that ingests licensed directory data (Yelp->OpenAI). A new app with verified, structured provider data could be a data supplier to assistants as well as a consumer destination.

### Gaps
- No data found on Nextdoor, Facebook groups/Marketplace or Bing Places share for home-services hiring in 2026.
- No formal consumer survey found for Pakistan, UAE or Saudi Arabia on how people find tradespeople; all evidence is anecdotal or vendor marketing.
- Apple Business Connect feature details and Google Maps usage figures for India were not retrieved. Urban Company's scale was not researched here (likely covered by another researcher).

## 7. What Google data/APIs a third-party app can build on (Places API pricing and terms)

### Takeaway
Places API (New) can seed a provider directory, but it is priced per request with small free monthly allowances per SKU, and Google's terms forbid building a persistent copy: only place IDs may be stored indefinitely, coordinates may be cached for at most 30 days, and Google content must be attributed and kept distinguishable. Google listings and reviews can be displayed live but cannot be the app's own database.

### Cited Findings
- From 1 March 2025 Google replaced the $200 monthly credit with a free monthly usage threshold per Core Services SKU. — [Google Maps Platform, March 2025 changes](https://developers.google.com/maps/billing-and-pricing/march-2025); [Google pricing page](https://developers.google.com/maps/billing-and-pricing/pricing)
- Third-party guides give the allowances as 10,000 free calls per month for Essentials SKUs, 5,000 for Pro and 1,000 for Enterprise. — [Woosmap](https://www.woosmap.com/blog/is-google-maps-api-free); [Open Places API](https://openplacesapi.com/blog/google-places-api-free-tier)
- Example price: Text Search Pro $32.00 per 1,000 calls for the first 100,000 per month, stepping down through volume bands to $2.40 above 5 million (third-party calculator; verify on Google's list). — [Open Places API](https://openplacesapi.com/blog/google-places-api-pricing)
- Billing is per request, not per place returned; the field mask determines which SKU (and price tier) applies; Autocomplete session requests are free but the following Place Details call is charged. — [Woosmap](https://www.woosmap.com/blog/google-places-api-pricing)
- The original Places API is Legacy and cannot be enabled on new projects; new work must use Places API (New). — [Woosmap](https://www.woosmap.com/blog/google-places-api-pricing)
- Caching: "The place ID, used to uniquely identify a place, is exempt from the caching restrictions. You can therefore store place ID values indefinitely." Latitude/longitude from Places API may be cached for up to 30 consecutive calendar days and then must be deleted; Places lat/long may not be used for point-in-polygon analysis. — [Google policies page](https://developers.google.com/maps/documentation/geocoding/policies); [Maps Service Specific Terms](https://cloud.google.com/maps-platform/terms/maps-service-terms)
- Attribution: if Google content is combined with third-party content the developer must make clear to the end user what is Google Maps Content and what is not. — [Maps Service Specific Terms](https://cloud.google.com/maps-platform/terms/maps-service-terms)
- Separate EEA service-specific terms exist, with their own rules on using Google content with maps. — [Maps Platform EEA Service Specific Terms](https://cloud.google.com/terms/maps-platform/eea/maps-service-terms)
- The GBP Q&A API was shut down on 3 Nov 2025, an example of Google withdrawing business-side APIs. — [slashpost.ai](https://slashpost.ai/blogs/google-business-profile/google-business-profile-qa-removed-2026)

### Inferences
- Practical pattern: store only the Google place ID against the app's own provider record, fetch Google name/rating/reviews live when shown (with attribution), and build first-party data (verified identity, prices, job history, own reviews) as the real asset. Importing Google reviews into the app's own rating would breach the caching terms.
- At $32 per 1,000 Text Search Pro calls, an app doing a Google-backed search on every user query would spend meaningfully at scale; search should run on the app's own index, with Google calls reserved for onboarding and enrichment.
- Platform dependence is a risk: Google has removed chat, call history, Q&A and its API within two years, and re-priced Maps Platform in 2025.

### Gaps
- Exact current per-SKU prices for Place Details, Nearby Search and review fields were not verified on Google's live pricing page.
- The specific terms on displaying Google reviews (number returned per place, required attribution format, ban on mixing into own ratings) and the general anti-scraping/"no creating a substitute database" clause were not retrieved verbatim.
- Whether the "no use with a non-Google map" rule applies to Places content in the current (non-EEA) terms was only seen in an archived 2018 version.
- GBP API (business-side) access rules and whether a marketplace could manage providers' profiles on their behalf were not researched.
