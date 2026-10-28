# Ecomm Tracker — Master Plan

**Owner:** Everon Digital · **Product:** Ecomm Tracker
**Goal:** WordPress/WooCommerce stores ke liye Wix-style eCommerce analytics + visitor tracking, free/paid plugin, aur mobile app se real-time notifications.

---

## 1. Product Vision

Store owner plugin install kare → apne Ecomm Tracker account se connect kare → website par har visitor, cart aur order track ho → dashboard (WP admin, web, mobile) par reports dekhe → mobile par push notifications aaye ("New order Rs 4,500", "Cart abandoned", "15 live visitors").

## 2. Features

### Free plan
- Visitors, sessions, page views, unique users
- Traffic sources (direct, Google, social, referral, UTM)
- Device, browser, country/city
- Live visitors counter
- WooCommerce basics: orders, revenue, average order value
- Top pages & top products
- 30 din data retention, 1 website
- Mobile app: daily summary notification

### Pro plan (paid)
- **Sales funnel:** product view → add to cart → checkout → purchase (Wix jaisa)
- **Abandoned cart tracking** + alerts (aur email recovery, Phase 4)
- Customer journey / per-visitor timeline (kaun aya, kya dekha, kya khareeda)
- Product analytics: views vs add-to-cart vs conversion rate
- Coupon, refund, payment-method reports
- Real-time push notifications (new order, high-value order, abandoned cart, traffic spike)
- Custom events, goals, CSV/PDF export, scheduled email reports
- 1 / 5 / 25 websites (tiers), 1–2 saal retention
- Team members (staff accounts)

### Pricing draft
| Plan | Price | Sites |
|---|---|---|
| Free | $0 | 1 |
| Pro | $9/mo ya $79/yr | 1 |
| Business | $29/mo | 5 |
| Agency | $79/mo | 25 |
(Pakistan ke liye PKR pricing alag rakh sakte hain.)

## 3. Architecture

```
 WordPress site                         Ecomm Tracker Cloud
┌──────────────────┐   HTTPS/JSON   ┌─────────────────────────────┐
│ tracker.js (front)│──────────────▶│ Ingest API (high-throughput) │──▶ Queue (Redis/BullMQ)
│ PHP hooks (Woo)   │──server-side─▶│                              │        │
│ WP admin screens  │◀──REST────────│ Main API (auth, reports,     │   Workers: enrich (geo/UA),
└──────────────────┘                │  license, sites, billing)    │   aggregate, alerts
                                    └──────────┬──────────────────┘        │
                                               │                PostgreSQL + ClickHouse/Timescale
                       ┌───────────────────────┼─────────────┐             │
                       ▼                       ▼             ▼        FCM / APNs push
                 Web dashboard            Mobile app     Website + checkout
                  (Next.js)            (React Native)   (Stripe/Paddle/Freemius)
```

**Key decisions**
- **Data cloud mein store hoga** (WP database mein nahi) — WP site slow nahi hogi aur mobile app ko data milega. Free plan mein bhi lightweight cloud sync.
- **Orders server-side track honge** (`woocommerce_order_status_changed`, `woocommerce_payment_complete`) — adblockers se miss nahi honge. Page views/cart events JS se + fallback `woocommerce_add_to_cart` hook.
- **Ek hi account** website, dashboard aur mobile app teeno par (JWT + refresh tokens).
- Plugin site ko account se **API key / OAuth-style "Connect" button** se link karega.

## 4. Components detail

### 4.1 WordPress plugin (`plugin/`)
- PHP 8.1+, WP 6.x, WooCommerce 8+ (HPOS compatible)
- Settings page: Connect account, tracking on/off, exclude admins/roles, cookie consent mode
- `tracker.js` (<5 KB, async, `sendBeacon`), first-party cookie/anonymous visitor ID
- WooCommerce hooks: view_item, add_to_cart, remove_from_cart, begin_checkout, purchase, refund
- WP admin widget + mini dashboard (data API se)
- Licensing: free version wordpress.org par, Pro add-on license key se unlock (Freemius ya apna license server)
- Auto-updates for Pro (own update server)

### 4.2 Backend (`backend/`)
- Node.js (NestJS) + TypeScript
- PostgreSQL: users, sites, subscriptions, licenses
- ClickHouse (ya TimescaleDB) events ke liye — billions of rows sasti query
- Redis: live visitors, queues, rate-limit
- Modules: Auth, Sites, Ingest, Reports, Alerts/Notifications, Billing webhooks, License
- GeoIP (MaxMind GeoLite2), UA parsing, bot filtering

### 4.3 Web dashboard (`dashboard/`)
- Next.js + Tailwind + charts; overview, live, funnel, products, customers, sources, settings, billing

### 4.4 Mobile app (`mobile/`)
- React Native (Expo) — Android + iOS ek codebase
- Login (same account), site switcher, overview, live visitors, orders feed
- Push: Firebase Cloud Messaging (Android) + APNs (iOS via FCM)
- Notification settings per site (new order, min order value, abandoned cart, daily summary)

### 4.5 Website (`website/`)
- Landing, features, pricing, docs, blog, signup/login, **plugin download**, checkout
- Payments: Stripe / Paddle (international) + local option (JazzCash/Easypaisa/bank) baad mein

## 5. Privacy & compliance
- GDPR/CCPA: consent mode, IP anonymization, cookie-less option, data delete/export requests
- Privacy policy + DPA, data region choice (later)
- wordpress.org guidelines: free plugin "trialware" na ho; external service clearly disclose karna

## 6. Roadmap (phases)

| Phase | Time (approx) | Deliverable |
|---|---|---|
| 0. Setup | 1 hafta | Repo, CI, coding standards, domain, Figma designs |
| 1. MVP tracking | 4–5 hafte | Plugin + ingest API + basic web dashboard (visitors, pages, sources, orders) |
| 2. Accounts & licensing | 2–3 hafte | Signup/login, site connect, Free/Pro gating, website + download page |
| 3. Mobile app | 4 hafte | RN app, login, overview, live, push notifications |
| 4. Pro analytics | 4–6 hafte | Funnels, abandoned carts, customer journey, product analytics, exports, email reports |
| 5. Billing & launch | 2–3 hafte | Stripe/Paddle, wordpress.org submission, Play Store + App Store, beta users |
| 6. Growth | ongoing | Heatmaps/session recording, AI insights, Shopify/other platforms, agency white-label |

**Total MVP→launch:** ~4–5 mahine (2–3 developers).

## 7. Team
- 1 PHP/WordPress dev, 1 Node/backend dev, 1 React/React Native dev, 1 designer (part-time), QA

## 8. Monthly infra (shuru mein)
- VPS/Cloud (API + DB): $40–100, ClickHouse cloud/self-host: $0–50, FCM free, Apple dev $99/yr, Google Play $25 once, domain + email ~$20

## 9. Risks
- Adblockers → server-side order tracking + first-party endpoint (`/wp-json/ecomm-tracker/collect` proxy)
- High traffic sites → queue + batching + sampling
- wordpress.org review rules → free version standalone useful hona chahiye
- Privacy laws → consent mode default

## 10. Next steps
1. Product name/domain final karein (ecommtracker.com availability)
2. Figma wireframes: dashboard + mobile
3. Phase 1 start: plugin skeleton + ingest API
4. Alag private GitHub repo (`ecomm-tracker`) bana kar ye folder wahan move karna
