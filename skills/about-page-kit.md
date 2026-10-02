---
name: about-page-kit
description: Build an about page for a store/brand (story, mission, values, team) that visually matches an existing landing page's proportions and style. Use whenever the user asks for an about page, especially when they want it to match an existing site's design, or need a font pairing chosen for a vibe like luxury, futuristic, modern, minimal, playful, elegant, vintage, or bold.
---

# About Page Kit

Builds an about page that reads as the same site as the landing page, not a visually disconnected page bolted on afterward.

## 0. Figure out the stack (ask once, if not already told)

Plain HTML/CSS/JS, React (Vite/Next), or a Lovable project? Don't re-ask if already answered earlier in the conversation.

Load `frontend-design` for layout and design-token conventions in this environment. `impeccable` and `ui-styling` are useful for a final polish pass.

## 1. Match the existing design system — do not invent a new one

If a landing page or existing site is provided, extract its actual values and reuse them exactly:

- **Fonts** — same heading/body pairing already in use. Only pick a new pairing from `../references/fonts.md` if there is no existing site to match yet.
- **Colors** — same palette (primary, secondary, background, text, accent).
- **Spacing and proportions** — same container max-width, section rhythm, radius, button shape.
- **Component style** — same nav/footer treatment, same button and card styles, same image treatment.

The test: someone should not be able to tell, from layout and type alone, that they navigated to a different page.

## 2. Page structure

Typical sections, adapted to the content actually available:

1. Intro / mission statement
2. Story or founding narrative (if provided)
3. Values or process (if provided)
4. Team (if provided; photos + names + roles; skip entirely rather than using placeholder headshots)
5. CTA back to shop or contact

## 3. Tone and content rules

- Keep the copy consistent with the brand voice already established elsewhere
- Use the same section spacing, card shapes, and rhythm as the landing page
- Avoid heavy novelty effects that make the page feel disconnected from the product story
- If there is no team content, do not invent a team
- If there are no values, do not invent them; only include a values section when real content exists

## 4. Brand matching and typography

When there is no existing site to match, choose from `../references/fonts.md` based on the brand vibe:

- **Luxury:** large-serif heading + clean grotesk body
- **Futuristic:** geometric headings + technical sans body
- **Modern / minimal:** clean grotesk pairing with low contrast
- **Elegant:** editorial serif pairing
- **Playful:** warm rounded sans or soft serif
- **Vintage:** retro serif + classic body font
- **Bold / streetwear:** condensed heavy heading + clean body

## Reference files

- `../references/fonts.md` — font pairings by vibe
