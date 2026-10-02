---
name: admin-panel-kit
description: Build an admin account (login-gated) and admin pages (dashboard, products, orders, settings, etc.) for a store/brand site. Use whenever the user asks for an admin panel, admin account, dashboard, or back-office pages, or wants to add admin/management functionality to an existing site. Also covers picking a restrained, on-brand font for the admin UI when the user wants it to feel branded rather than purely generic.
---

# Admin Panel Kit

Builds the back-office side of a site: a gated admin account plus the management pages behind it. This is a different design problem from the public-facing site — the priority is clarity and speed of use, not marketing polish.

## 0. Figure out the stack and auth situation (ask once, if not already told)

- Stack: plain HTML/CSS/JS, React (Vite/Next), or a Lovable project?
- Auth: an admin account needs somewhere to store users and sessions. If the stack has no backend/auth yet, say so explicitly and propose an option such as:
  - Supabase auth via Lovable or direct integration
  - an auth library for Next.js
  - Firebase Authentication
  - a temporary hard-coded password gate only for a throwaway prototype, clearly labeled as non-production

Never silently build a fake login and let the user believe it is real auth; state plainly which kind you built.

Do not re-ask if already answered earlier in the conversation.

Load `ui-styling` for shadcn/Tailwind component patterns (tables, forms, dialogs) before building admin UI. `frontend-design` covers general layout/design-token conventions in this environment.

## 1. Pick admin pages with the user, do not assume all of them

Common defaults if the user has not specified: dashboard/overview, products (list + add/edit), orders, settings.

Ask which of these they actually need rather than building all of them speculatively — an admin panel for a five-product storefront does not need the same surface area as one for a large catalog.

## 2. Style: functional first, branded second

- Default to a clean, utilitarian UI: data tables, clear form inputs, sensible empty/loading/error states. A luxury storefront does not need a luxury-styled admin table — legibility and speed matter more here than aesthetics.
- It is normal and correct for the admin area to look plainer than the public site. Reuse the brand's primary color as an accent (buttons, active nav state) for continuity, not the full marketing design system.
- If the user explicitly wants the admin area to feel branded or on-vibe rather than default-utilitarian, pick a single restrained font from `references/fonts.md` for headings — favor the plainer end of the relevant vibe's pairing (for example, for a luxury brand, skip the ornate serif and just use its grotesk body font for admin headings too). Never use a script, handmade, or heavily decorative display font in an admin UI, even if that is the brand's public-facing vibe.

## 3. Baseline structure

- Login page — email/password form, error states, redirect to dashboard on success
- Layout shell — persistent sidebar or top nav with selected admin pages, logout action, and clear separation from the public site
- Each admin page — table/list view with the core fields the user cares about, plus creation/editing where relevant

## Recommended admin pages

Choose only the ones the business actually needs:

- Dashboard: KPIs, recent orders, low-stock alerts
- Products: product list, stock levels, create/edit/delete
- Orders: customer name, order date, total, fulfillment status, update status
- Settings: store profile, shipping rules, email settings, notifications

## Quality bar

The admin experience should:

- be fast to scan
- show status clearly
- minimize clicks for common tasks
- make stock and order actions obvious
- use validation and empty states consistently

## Reference files

- `references/fonts.md` — font pairings by vibe
- `references/skills/README.md` — index of available skills
