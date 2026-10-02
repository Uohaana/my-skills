# Tailwind customization guide

A simple Tailwind config should usually define:

- brand colors
- neutral shades
- font families
- radius scale
- spacing scale
- breakpoints if a custom system is needed

## Example

```js
export default {
  theme: {
    extend: {
      colors: {
        brand: {
          50: '#f5f7ff',
          500: '#3b82f6',
          900: '#1e3a8a'
        }
      },
      fontFamily: {
        sans: ['Inter', 'sans-serif'],
        display: ['Playfair Display', 'serif']
      }
    }
  }
}
```

Use the config to keep the visual system consistent across products, landing pages, and admin panels.
