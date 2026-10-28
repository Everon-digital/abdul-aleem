# Ecomm Tracker — by Everon Digital

WordPress / WooCommerce ke liye user tracking plugin (Wix eCommerce analytics jaisa).
Plugin website se download hoga (Free + Pro), aur store owner same account se mobile app
par login kar ke live notifications aur reports dekh sakega.

| Folder | Kya hai | Tech |
|---|---|---|
| `plugin/` | WordPress plugin (tracking + WP admin dashboard) | PHP 8.1+, JS |
| `backend/` | Cloud API: accounts, events ingest, licensing, push | Node.js (NestJS) + PostgreSQL + Redis |
| `dashboard/` | Web dashboard (app.ecommtracker.com) | Next.js |
| `mobile/` | Android + iOS app | React Native (Expo) + FCM/APNs |
| `website/` | Marketing site, download, pricing, checkout | Next.js / WordPress |

Poora plan: [`docs/PLAN.md`](docs/PLAN.md)
