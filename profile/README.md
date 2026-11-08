# Velociti HQ

**The delivery marketplace for Uyo — linking businesses and customers with independent riders.**

Book a pickup, pay, and watch your parcel move in real time. Auth and delivery first, bills next.

## Repositories

| Repo | Stack | What lives there |
|------|-------|-----------------|
| [velociti-api](https://github.com/Velociti-HQ/velociti-api) | Go · Postgres | Backend: OTP auth, delivery jobs, rider offers, proof-of-delivery, tracking, append-only ledger |
| [velociti-customer-app](https://github.com/Velociti-HQ/velociti-customer-app) | Flutter (Dart) | Customer, rider and partner apps with shared Dart packages — quote, book, pay, track |
| [velociti-web](https://github.com/Velociti-HQ/velociti-web) | Next.js (TypeScript) | Official website |

## How we build

- **The contract is the source of truth** — `api/openapi.yaml` in `velociti-api` defines every endpoint; clients follow it.
- **Money is integers, never floats** — amounts are kobo counts, and CI greps the ledger to prove it.
- **The client never sends a price** — it sends a `quote_id`; the server snapshots what it quoted.
- **The ledger is append-only** — corrections are reversals, never updates. A provider timeout is *pending*, not failed.
- **Retries are safe** — every money-moving request carries an `Idempotency-Key`; the stored response replays on retry.
- **Small, reviewable commits** — one concern per commit, pushed as it lands.

## Getting started

- Backend: `cd backend && cp .env.example .env && go run ./cmd/api` (needs `DATABASE_URL`) — see [velociti-api](https://github.com/Velociti-HQ/velociti-api#run).
- App: `flutter pub get && flutter run` — see the customer app repo.
- Web: `npm install && npm run dev` — see the web repo.
