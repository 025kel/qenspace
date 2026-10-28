# QenSpace Solutions & Mobile Repairs — Prototype

## Open the prototype
1. Extract `qenspace-shop-prototype.zip`.
2. Open `index.html` in a modern browser (Chrome, Edge, Firefox).
3. Use the navigation to try Sales/POS, Inventory, Repairs, M-Pesa Agent, Cashbook, Reports, and Settings & Data.

No installation, server, API key, or internet connection is required to try this single-file demo.

## What works in this prototype
- Add and edit accessory products with separate category, brand, model/variant, buying cost, selling price and stock quantity; filter inventory by category or low-stock status.
- Add a branded starter catalogue with 28 illustrative product variants covering Amaya, Oraimo, Samsung, Tecno, Infinix, Itel, Redmi, Apple and generic accessories. The sample KSh prices and quantities must be edited to match the shop’s real supplier prices and stock.
- Record accessory sales, split payment methods, deduct inventory, and open a digital receipt that can be printed or saved as PDF.
- Register repair jobs, create an initial quotation, record a deposit and later payments, update repair status, and create a digital repair job card.
- Manually record M-Pesa agent deposits and withdrawals, transaction references, commission, cash effect and float effect.
- Record expenses and other cash movements.
- Estimate cash and float balances, save a daily closing snapshot, view simple reports, export CSV and download/restore a JSON backup.
- Data persists in this browser using localStorage.

## Important prototype limitations
- This is a browser-only prototype, not a secure production application.
- Data is local to this browser/device; it does not sync to a second device or user.
- There is no real login, server, cloud database, role-based access, multi-user concurrency, automated backup, or tamper-resistant audit trail.
- M-Pesa transaction entry is manual. No Safaricom API connection, live verification, STK push, payment execution or automated statement import is implemented.
- Opening balances are configurable demo values. Confirm the cash/float movement convention against the actual M-Pesa agent workflow before using real records.
- Stock receiving updates quantity but does not automatically create a supplier payment or full purchase-accounting entry.
- Refund, reversal, quotation revision, approval, collection and accounting controls are demonstrations only and require production-grade validation.
- Reports are operational estimates, not audited accounts or tax reports.
- Do not enter real customer-sensitive data or rely on this prototype as the sole record of actual business transactions.

## Production build recommendations
1. Implement a server-backed application (e.g. Next.js + TypeScript API and PostgreSQL).
2. Add secure authentication and owner/attendant permissions.
3. Implement a balanced, append-only financial ledger and inventory movement ledger.
4. Add database transactions, unique transaction codes, idempotency keys, reversal workflows and audit logs.
5. Validate the M-Pesa agent accounting model against official agent statements and investigate authorized Safaricom integration options.
6. Add automated encrypted backups, recovery tests, monitoring and HTTPS.
7. Run acceptance tests with sample transactions, then migrate real data only after reconciliation and user sign-off.


## Admin and attendant portals (updated 28 October 2026)

Open `index.html` in a modern browser. The sign-in screen offers these demonstration accounts:

- Administrator: username `admin`, password `Admin123!`
- Shop attendant: username `attendant`, password `Staff123!`

The administrator has full access, including staff accounts, inventory editing, reports, settings, and backups. Attendants can record sales, view product stock and selling prices, manage repair jobs, record manual M-Pesa transactions, and use the cashbook. They cannot edit inventory, void sales, manage users, open settings, or export/restore backups. The administrator can add staff accounts from **Staff Accounts**.

The first visit can use **Inventory → Add branded starter catalogue** after signing in as admin to add the Amaya, Oraimo, Samsung, Tecno, Infinix, Itel, Redmi, Apple and generic product variants. Example prices and stock quantities must be adjusted to actual supplier prices and counts.

**Security limitation:** this remains a single-file front-end prototype. User accounts, passwords and records are stored in browser local storage, without secure server-side authentication or cross-device synchronization. Role restrictions are useful for demonstration but can be bypassed by someone with developer tools. Do not use real passwords or rely on it as the sole source of live financial records. Production use requires a backend database, password hashing, server-enforced permissions, authenticated sessions, audit controls and tested backups.
