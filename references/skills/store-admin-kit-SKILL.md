---
name: store-admin-kit
description: Build a login-gated admin panel for store/brand sites focused on stock management and order monitoring. Use whenever the user asks for an admin account to manage inventory, update product stock levels, track incoming orders, or monitor fulfillment status. Provides an efficient back-office for handling the critical operational tasks of running a store.
---

# Store Admin Kit

Builds a focused back-office for store operations: a gated admin account and management pages for stock and orders. Prioritizes clarity and operational speed over design polish.

## 0. Confirm the stack and auth approach (ask once, if not already told)

- Stack: plain HTML/CSS/JS, React (Vite/Next), or a Lovable project?
- Auth: admin accounts need a backend to store users and sessions. If the stack has no auth yet, explicitly propose a realistic path such as:
  - Supabase auth
  - Next.js auth libraries
  - Firebase Auth
  - an explicit password gate for a prototype only

Never silently build fake auth. State plainly which approach you used.

Load `ui-styling` for shadcn/Tailwind component patterns (tables, forms, modals) before building admin UI.

## 1. Admin scope: stock + orders only

This kit focuses on two core admin pages:

- Dashboard — quick overview of stock health, pending orders, and recent activity
- Stock Management — product list with current counts, updates, and reorder alerts
- Orders — incoming orders with customer data, fulfillment state, and status updates

Ask the user if they need additional pages such as settings, returns, or analytics before adding them.

## 2. Style: utility-first, minimal branding

- Clean, data-focused UI: tables for lists, inline editing or simple modals for updates, status badges for stock health
- Use the brand's primary color as an accent for buttons and active navigation only
- Default to a system or neutral web font for legibility; avoid decorative display fonts in admin interfaces
- Focus on speed and scanning, not aesthetic complexity

## 3. Baseline structure

- Login page — email/password or magic-link entry, bad-credential states, redirect to dashboard on success
- Admin shell — persistent navigation (sidebar or top bar), logout button, and separation from the public storefront
- Dashboard — low-stock summary, incoming order totals, recent order list, alerts
- Stock page — table with product name, SKU, quantity, reorder threshold, edit action
- Orders page — table with order ID, customer name, order date, status, total, update-status action

## 4. Data and workflow expectations

- Stock updates should be easy to perform and auditable
- Order updates should be simple: pending → processing → shipped → completed
- If a backend is available, persist stock counts and order data in the same app/database
- If a real-time view is available, refresh low-stock and order state automatically rather than requiring a manual reload

## 5. Operational behavior the agent should prefer

- Show low-stock warnings when quantity falls below reorder threshold
- Highlight delayed or unfulfilled orders
- Keep forms short and direct: quantity adjustment, fulfillment status, notes
- Use loading, success, and error states for stock updates

## Reference files

- `references/fonts.md` — font selections by vibe
- `references/skills/README.md` — skill index
