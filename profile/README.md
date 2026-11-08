# Velociti HQ

**The delivery marketplace for Uyo — linking businesses and customers with independent riders.**

Book a pickup, pay, and watch your parcel move in real time. Auth and delivery first, bills next.

## Repositories

| Repo | Stack | What lives there |
|------|-------|-----------------|
| [velociti-api](https://github.com/Velociti-HQ/velociti-api) | Go · Postgres | Backend: OTP auth, delivery jobs, rider offers, proof-of-delivery, tracking, append-only ledger |
| [velociti-customer-app](https://github.com/Velociti-HQ/velociti-customer-app) | Flutter (Dart) | Customer, rider and partner apps with shared Dart packages — quote, book, pay, track |
| [velociti-web](https://github.com/Velociti-HQ/velociti-web) | Next.js (TypeScript) | Official website |

(https://github.com/Velociti-HQ/velociti-api#run).
- App: `flutter pub get && flutter run` — see the customer app repo.
- Web: `npm install && npm run dev` — see the web repo.
