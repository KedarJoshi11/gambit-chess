# Gambit chess coaching

This is a dynamic Cloudflare Pages app. Pages Functions read coach data and availability from Cloudflare D1; confirmed bookings are saved to it.

## Deploy

1. Push this folder to GitHub.
2. The project is configured for the existing D1 database `01be239b-440f-4deb-88af-e18dfa069a72`.
3. Execute `migrations/0001_initial.sql` in that database's Cloudflare console.
4. Create a Pages project from the repository: no build command, `.` output directory.
5. Add a Pages D1 binding named `DB`, pointing to `gambit-bookings`, then deploy.

## What works now

Coach profiles load from the database. Availability reflects stored bookings. Booking data is saved server-side, and the database prevents double-booking a coach's time slot.

Before charging customers, add authentication, coach approval, payment processing with Stripe Connect, payment webhooks, email notifications, cancellation rules, and an admin area.
