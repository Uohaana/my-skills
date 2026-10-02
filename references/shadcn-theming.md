# shadcn theming guide

## Theme structure

Use CSS variables to define the underlying brand colors and neutrals. Then apply Tailwind variables to UI surfaces and component variants.

## Common patterns

- brand accent for primary buttons and active navigation states
- neutral surfaces for admin pages
- dark mode with strong contrast and readable text
- accent color limited to key actions and status indicators

## Example

```css
:root {
  --background: 0 0% 100%;
  --foreground: 222.2 84% 4.9%;
  --primary: 221.2 83.2% 53.3%;
  --primary-foreground: 210 40% 98%;
}
```

Use these variables with shadcn component classes to preserve a consistent theme across the app.
