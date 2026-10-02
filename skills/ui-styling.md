---
name: ui-styling
description: Create beautiful, accessible user interfaces with shadcn/ui components (built on Radix UI + Tailwind), Tailwind CSS utility-first styling, and canvas-based visual designs. Use when building user interfaces, implementing design systems, creating responsive layouts, adding accessible components (dialogs, dropdowns, forms, tables), customizing themes and colors, implementing dark mode, generating visual designs and posters, or establishing consistent styling patterns across applications.
argument-hint: "[component or layout]"
license: MIT
metadata:
  author: dxc
  version: "1.0.0"
---

# UI Styling Skill

Comprehensive skill for creating beautiful, accessible user interfaces using shadcn/ui, Tailwind CSS, and simple design-system conventions.

## When to use this skill

Use this when:

- building a UI with React-based frameworks (Next.js, Vite, Remix, Astro)
- implementing accessible components (dialogs, forms, tables, navigation)
- styling with a utility-first approach
- creating responsive mobile-first layouts
- implementing dark mode and theme customization
- building consistent design systems
- generating posters or visual compositions
- prototyping a polished storefront quickly

## Core stack

### Component layer: shadcn/ui

- accessible, Radix-powered primitives
- copy-paste model into your codebase
- TypeScript-friendly and composable
- good for tables, dialogs, forms, menus, and data-rich surfaces

### Styling layer: Tailwind CSS

- utility-first design
- good for spacing, layout, typography, color, and state handling
- builds cleanly and lightens CSS overhead

## Quick start

### Install shadcn/ui and Tailwind

```bash
npx shadcn@latest init
```

Then add components as needed:

```bash
npx shadcn@latest add button card dialog form
```

### Example

```tsx
import { Button } from "@/components/ui/button"
import { Card, CardHeader, CardTitle, CardContent } from "@/components/ui/card"

export function Dashboard() {
  return (
    <div className="container mx-auto p-6 grid gap-6 md:grid-cols-2 lg:grid-cols-3">
      <Card className="hover:shadow-lg transition-shadow">
        <CardHeader>
          <CardTitle className="text-2xl font-bold">Analytics</CardTitle>
        </CardHeader>
        <CardContent className="space-y-4">
          <p className="text-muted-foreground">View your metrics</p>
          <Button variant="default" className="w-full">View Details</Button>
        </CardContent>
      </Card>
    </div>
  )
}
```

## Component library guide

Use shadcn conventions for:

- forms and input controls
- cards and layout blocks
- tables and data rows
- dialogs and popovers
- nav menus and tabs
- alerts and feedback states

## Theme and accessibility guidance

- Keep focus states visible and strong
- Use semantic HTML and labels for forms
- Ensure contrast is readable in both light and dark themes
- Use consistent spacing multiples and typography scales
- Keep brand accents limited to buttons, links, and active states so the UI stays clear and functional

## Design practices

- prefer simple composition over decorative excess
- keep data readable above all else
- if matching a brand, apply the accent color consistently rather than redesigning the entire interface
- use mobile-first layout and later add wider-screen composition

## Reference docs

- `../references/fonts.md` — font pairings by vibe
- `../references/shadcn-components.md` — UI component catalog
- `../references/shadcn-theming.md` — theming guidance
- `../references/shadcn-accessibility.md` — accessibility patterns
- `../references/tailwind-utilities.md` — utility-first CSS patterns
- `../references/tailwind-responsive.md` — responsive layout rules
- `../references/tailwind-customization.md` — custom Tailwind config patterns
- `../references/canvas-design-system.md` — visual communication notes
