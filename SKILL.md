---
name: storefront-admin-kit
description: Build storefront pages, storefront brand pages, admin dashboards, stock management, and order tracking for store/brand websites. Use when the user wants a landing page, about page, admin panel, inventory system, order dashboard, or a clean UI system matching a brand's vibe and existing style.
---

# Storefront + Admin Kit

Use this skill to build a complete commerce or brand site experience with an appropriate mix of public-facing pages and operational back-office tools.

## 1. Start by identifying the task

Choose the relevant workflow based on the user's request:

- landing page / homepage
- about page / brand story
- admin dashboard / product control panel
- stock inventory panel
- order tracking / fulfillment status
- UI styling for storefront or admin screens

Do not assume the user wants all of these. Match the scope to their actual request.

## 2. Figure out the stack and auth situation

Ask once if needed:

- Plain HTML/CSS/JS, React (Vite/Next), or a Lovable project?
- Does the app already have auth or backend storage?

If there is no auth yet and the task needs admin login access, say so explicitly and propose one of these:

- Supabase auth
- NextAuth or a similar Next.js auth library
- Firebase Authentication
- a hard-coded password gate only for a quick prototype, clearly labeled as not production-ready

Never pretend a fake login is real auth.

## 3. For landing pages and brand pages

When building a public-facing page, prioritize consistency with the existing brand:

- reuse the available font pairing, colors, spacing, and layout proportions
- do not invent a new visual style unless the user asks for one
- use `references/fonts.md` if you need a brand vibe pairing
- keep the structure clear and conversion-oriented

Typical sections:

- hero with headline, subhead, CTA, supporting media
- value props / features
- product highlights
- brand story / about content
- final CTA and footer

## 4. For admin pages

When building an admin panel, prioritize speed, clarity, and operational use:

- login-gated dashboard
- stock management page
- orders page with status updates
- product page with create/edit/list behavior
- settings page only if explicitly needed

Use clean tables, clear statuses, minimal clicks, and explicit empty/loading/error states.

## 5. For stock and order workflows

If the store requires inventory and fulfillment management:

- show low-stock alerts
- allow stock quantity updates
- show pending/processing/shipped/completed order states
- let the admin update order status
- highlight delayed or incomplete work

This is especially important for storefront/back-office builds that need commerce operations.

## 6. For styling

Use a restrained, practical design system:

- keep admin UIs legible and dense where needed
- use the brand accent color sparingly for actions and active states
- avoid decorative display fonts in data-heavy admin screens
- prefer Tailwind + shadcn/ui patterns for accessible interfaces

## 7. Good default behaviors

- match the user’s existing site if one exists
- keep public pages and admin pages visually distinct but aligned in tone
- prefer real business logic over decorative placeholders
- ask for missing requirements only once
- use clear components, forms, tables, and states

## Reference files

- `README.md`
- `skills/landing-page-kit.md`
- `skills/about-page-kit.md`
- `skills/admin-panel-kit.md`
- `skills/store-admin-kit.md`
- `skills/ui-styling.md`
- `references/fonts.md`
- `references/shadcn-components.md`
- `references/shadcn-theming.md`
- `references/shadcn-accessibility.md`
- `references/tailwind-utilities.md`
- `references/tailwind-responsive.md`
- `references/tailwind-customization.md`
- `references/canvas-design-system.md`
