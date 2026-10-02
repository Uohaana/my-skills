---
name: store-admin-kit
description: Build a login-gated admin panel for store/brand sites focused on stock management and order monitoring. Use whenever the user asks for an admin account to manage inventory, update product stock levels, track incoming orders, or monitor fulfillment status. Provides an efficient back-office for handling the critical operational tasks of running a store.
---

# Store Admin Kit

Builds a focused back-office for store operations: a gated admin account plus lean management pages for stock and orders. Prioritizes clarity and operational speed over design polish.

## 0. Confirm the stack and auth approach (ask once, if not already told)

- **Stack**: plain HTML/CSS/JS, React (Vite/Next), or a Lovable project?
- **Auth**: admin accounts need a backend to store users and sessions. If the stack has no auth yet, explicitly propose an option:
  - Supabase auth (via Lovable or direct integration)
  - Next.js built-in auth (NextAuth.js or similar)
  - Firebase Authentication
  - Hard-coded password gate (only for throwaway prototypes — be clear this is not production-ready)
  
  Never silently build fake auth; state plainly which approach you're using and why.

Don't re-ask if already answered earlier in the conversation.

Load `ui-styling` for shadcn/Tailwind component patterns (tables, forms, modals) before building admin UI.

## 1. Admin scope: stock + orders only

This kit focuses on two core admin pages:

- **Dashboard** — quick overview of stock health (low-stock alerts, total inventory), pending orders, and recent activity
- **Stock Management** — product list with current quantities, update stock levels, flag items for reorder
- **Orders** — incoming orders with customer details, fulfillment status (pending, processing, shipped), ability to update status and mark as complete

Ask the user if they need any additional pages (settings, customer list, analytics) rather than building speculatively.

## 2. Style: utility-first, minimal branding

- Clean, data-focused UI: tables for lists, inline editing or simple modals for updates, clear status indicators (in-stock vs. low-stock vs. out-of-stock)
- Use the brand's primary color as an accent for buttons and active navigation only — admin pages should be plain and fast, not a showcase
- Default to a system font or neutral web font (e.g. Inter, Helvetica Neue) for maximum legibility; no decorative fonts in data tables or forms
- No animations or flourishes; form feedback should be instant and unambiguous (inline validation, loading spinners, success/error toasts)

## 3. Baseline structure

- **Login page** — email/password form (or magic link if using an auth service), clear error messages, redirect to dashboard on success
- **Admin shell** — persistent navigation (sidebar or top bar) with links to Dashboard, Stock, and Orders; logout button; visual break from public site
- **Dashboard** — at a glance: low-stock summary, pending order count, recent orders list
- **Stock page** — table with columns: product name, SKU, current quantity, reorder level, actions (edit quantity, mark for reorder). Ability to bulk-update stock or set reorder alerts
- **Orders page** — table with: order ID, customer name, order date, status (pending/processing/shipped), total, actions (view details, update status, mark complete). Filter by status if helpful

## 4. Data storage & real-time sync

- Use the same backend/auth provider for persisting stock levels and order data (Supabase PostgreSQL, Firebase Firestore, etc.)
- Consider adding a simple real-time listener (e.g., Supabase subscriptions) so stock changes and new orders appear without page refresh
- Log stock updates (who changed it, when, old → new quantity) for audit purposes if the backend supports it

## Reference files

- `references/fonts.md` — font pairings by brand vibe (use restraint: pick a clean body font, avoid display fonts in admin UIs)
- `references/ui-styling.md` — shadcn/Tailwind patterns for tables, forms, and modals
