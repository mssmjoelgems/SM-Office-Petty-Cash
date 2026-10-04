# SM Office Petty Cash Handler – Cloud Bill Book

## What this is
A cloud-first petty cash/bill-book web app designed around the user's current register:
Date | Transaction Type | Category | Description | Driver Name / Vehicle No | Amount.

It supports:
- Cloud database storage
- Category add/activate/deactivate
- Drivers and vehicles
- Credit/Debit transactions
- Bill/Voucher number
- Monthly register and category reports
- Printable bill voucher with signatures
- PDF/image attachments in cloud storage
- Login with Supabase Auth
- Settings for office name, address and signature labels

## Cloud backend
This version uses Supabase (Postgres + Storage + Auth). It is intentionally not hard-wired to a private server.

### Setup
1. Create a Supabase project.
2. Open SQL Editor.
3. Run `schema.sql`.
4. In Authentication, create an email/password user.
5. Open `index.html`.
6. Enter your Supabase Project URL and **anon/public** key in the setup screen.
7. Sign in.

Never put a Supabase service-role key into `index.html`.

## Important
The browser is only the interface. Transactions, categories, drivers, vehicles, settings and uploaded files are stored in Supabase cloud. The HTML does not use local browser storage for financial records.

## Production
For a production office deployment, host `index.html` on HTTPS (Netlify, Vercel, Cloudflare Pages, GitHub Pages, or your own server) and use the Supabase project as the backend.

## Excel
The cloud database should be treated as the master record. Excel exports can be added later as a reporting feature or generated server-side. This avoids the unreliable "HTML writes directly into an .xlsx file" problem.
