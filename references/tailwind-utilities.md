# Tailwind utility patterns

These are the most common utility classes used in modern storefront and admin interfaces.

## Layout

- `container mx-auto`
- `grid gap-6 md:grid-cols-2 lg:grid-cols-3`
- `flex items-center justify-between`
- `space-y-4` and `space-x-4`

## Typography

- `text-sm`, `text-base`, `text-lg`, `text-2xl`
- `font-medium`, `font-semibold`, `font-bold`
- `text-muted-foreground`

## Colors and surfaces

- `bg-white`, `bg-slate-50`, `bg-zinc-900`
- `text-slate-900`, `text-zinc-600`
- `border border-slate-200`

## States

- `hover:shadow-lg`
- `transition-colors`
- `focus-visible:ring-2`
- `disabled:opacity-50`

The rule is to keep utility classes readable and consistent, and only extract a component when a pattern repeats several times.
