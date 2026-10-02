# DXC Skill Library

A clean, reusable set of AI skill files for building storefront, brand, and admin experiences.

## Overview

This repo contains a focused skill library for creating polished commerce and brand websites without drifting into generic templates.

The library is organized into three categories:

- Storefront pages: landing pages, brand/story pages, and visual styling
- Admin tools: back-office dashboards, stock management, and order control
- UI system guidance: Tailwind, shadcn/ui, typography, responsiveness, and accessibility

## Skill index

### Storefront / brand
- `references/skills/landing-page-kit-SKILL.md` — build a landing page with hero, value props, CTA, and product storytelling
- `references/skills/about-page-kit-SKILL.md` — create an about/story page that matches the brand's existing design

### Admin / commerce operations
- `references/skills/admin-panel-kit-SKILL.md` — build a login-gated admin dashboard and management screens
- `references/skills/store-admin-kit-SKILL.md` — manage stock levels, low-inventory alerts, and order tracking for a store backend

### UI / design system
- `references/skills/ui-styling-SKILL.md` — UI patterns using Tailwind and shadcn/ui

## Supporting references

- `references/fonts.md` — font pairings by vibe
- `references/fonts-by-vibe.md` — short alias for font guidance
- `references/shadcn-components.md` — component catalog
- `references/shadcn-theming.md` — color and theme setup
- `references/shadcn-accessibility.md` — accessibility best practices
- `references/tailwind-utilities.md` — utility class quick reference
- `references/tailwind-responsive.md` — responsive layout patterns
- `references/tailwind-customization.md` — custom config guidance
- `references/canvas-design-system.md` — visual design principles

## Suggested use

Use the relevant skill file based on the feature you need:

- Need a landing page? → `landing-page-kit-SKILL.md`
- Need a brand/about page? → `about-page-kit-SKILL.md`
- Need an admin panel? → `admin-panel-kit-SKILL.md`
- Need stock + order management? → `store-admin-kit-SKILL.md`
- Need UI styling help? → `ui-styling-SKILL.md`

## File structure

```text
README.md
references/
  fonts.md
  fonts-by-vibe.md
  shadcn-components.md
  shadcn-theming.md
  shadcn-accessibility.md
  tailwind-utilities.md
  tailwind-responsive.md
  tailwind-customization.md
  canvas-design-system.md
  skills/
    README.md
    admin-panel-kit-SKILL.md
    store-admin-kit-SKILL.md
    about-page-kit-SKILL.md
    landing-page-kit-SKILL.md
    ui-styling-SKILL.md
```

## Purpose

These skill files are designed to help an AI agent create consistent storefront and admin experiences that are:

- visually aligned with the brand
- practical for real business work
- more usable than generic template output
- structured around authentic auth, inventory, and order flows where needed
