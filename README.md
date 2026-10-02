# DXC Skill Library

This repository contains a small, reusable skill library for building storefront, landing-page, and admin experiences for brand and commerce websites.

## Included skill files

- `references/skills/admin-panel-kit-SKILL.md` — gated admin panels for dashboards, product management, and settings
- `references/skills/store-admin-kit-SKILL.md` — store operations admin for stock updates and order tracking
- `references/skills/about-page-kit-SKILL.md` — about/story pages that match the site style
- `references/skills/landing-page-kit-SKILL.md` — landing page hero + CTA + product storytelling
- `references/skills/ui-styling-SKILL.md` — reusable UI styling patterns with Tailwind and shadcn/ui

## Included supporting reference files

- `references/fonts.md` — font pairings by vibe
- `references/fonts-by-vibe.md` — alias/documentation copy for font pairings
- `references/shadcn-components.md` — UI component catalog
- `references/shadcn-theming.md` — theming and dark mode patterns
- `references/shadcn-accessibility.md` — accessibility guidance
- `references/tailwind-utilities.md` — utility-first patterns
- `references/tailwind-responsive.md` — responsive layout rules
- `references/tailwind-customization.md` — custom Tailwind config patterns
- `references/canvas-design-system.md` — visual design philosophy and composition notes

## Purpose

These documents are designed to guide an AI coding agent to build consistent storefront experiences without drifting into overly generic layouts. They emphasize:

- matching an existing brand system when one exists
- keeping admin workflows operational and clear
- using real auth when the app needs login-gated admin access
- using restrained, on-brand type choices for storefront and admin work
- favoring practical business functionality over flashy but less usable UI

## Suggested usage

Point the agent to the relevant skill file depending on the requested feature:

- landing page or hero redesign → `landing-page-kit-SKILL.md`
- about page matching an existing site → `about-page-kit-SKILL.md`
- admin login + dashboard + product or order management → `admin-panel-kit-SKILL.md`
- stock + order operations for a store → `store-admin-kit-SKILL.md`
- Tailwind/shadcn styling patterns → `ui-styling-SKILL.md`
