# TLP48 Production Starter

This version replaces browser-local authentication/coins with Supabase Auth + Postgres RLS.

Setup:
1. Create a Supabase project.
2. Run `supabase/schema.sql` in SQL Editor.
3. Enable Email/Password Auth and configure email verification.
4. Copy the project URL and publishable key into `.env.local` (see `.env.example`).
5. `npm install && npm run dev`.
6. On Vercel, add the same `NEXT_PUBLIC_SUPABASE_URL` and `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY` environment variables.
7. Create the first user through the app, then promote that user's `profiles.role` to `admin` in the Supabase SQL editor. Do not expose the service-role key in browser code.

Security:
- Passwords are handled by Supabase Auth.
- RLS protects profiles, orders and ledgers.
- Coins cannot be changed by normal client update policies.
- Redeem and purchase operations are transactional database functions.
- Admin access is checked in the database.

Before public launch: configure custom domain/email, backups, Storage policies for images, rate limits/bot protection, order fulfillment/payment workflow, audit logs, and production error monitoring.
