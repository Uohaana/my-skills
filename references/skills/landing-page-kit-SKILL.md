---
name: landing-page-kit
description: Build a store/brand landing page (hero, value props, featured products, CTA, footer). Use whenever the user asks to build or redesign a landing page for a store/brand/product, and especially when they mention a hero video, idle video, hero image, matching an existing site's style/proportions, or a vibe like luxury, futuristic, modern, minimal, playful, elegant, vintage, or bold that needs a font pairing. Also use when the user wants the landing page to match a design already shown in this conversation.
---

# Landing Page Kit

Builds a single landing page with a locked-down design system so the result does not drift into generic-template territory.

## 0. Figure out the stack (ask once, if not already told)

Plain HTML/CSS/JS, React (Vite/Next), or a Lovable project? Do not re-ask if already answered earlier in the conversation.

Load `frontend-design` for layout and design-token conventions in this environment before writing files. For a final polish pass, `impeccable` and `ui-styling` are useful too.

## 1. Lock the design system before building

Pull this from whatever is provided: an existing site, screenshots, hero image, brand colors, or a stated vibe. Ask only for what is genuinely missing.

- Vibe → font pairing: use `references/fonts.md` for pairings by vibe
- Color palette: primary, secondary, background, text, accent
- Spacing and proportions: container max-width, section rhythm, grid columns, radius, button shape
- Component style: nav, button, card, image treatment

Write these down as CSS variables, Tailwind config values, or a short design tokens block and reuse them consistently.

## 2. Hero media logic — check this every time

- If the user has provided (or the existing site has) an intro video and/or an idle looping background video, build the hero the same way it is already done: video as background or showcase, same layout and overlay treatment, same CTA placement.
- If no video is provided, use the provided hero image in that exact slot, at the same proportions the video would have occupied.
- Never fabricate placeholder stock video or imagery. Ask for the asset or describe what it should show.

## 3. Page structure

Hero → value props / featured products → social proof (only if provided) → secondary CTA → footer.

Adapt the order and number of sections to what the content actually supports. Do not invent testimonials, reviews, or product data that was not given.

## 4. Copy and CTA conventions

- Keep the headline consistent with the brand's tone and existing pages
- Use a single main CTA and an optional secondary CTA, not a cluttered set of competing actions
- Keep the value-prop section concrete and outcome-driven
- Use product cards that match the rest of the site, not a different visual language

## Reference files

- `references/fonts.md` — font pairings by vibe
- `references/skills/README.md` — skill index
