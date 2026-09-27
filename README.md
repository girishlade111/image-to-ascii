# Image to ASCII

Convert images into ASCII art directly in your browser. Upload an image, tweak brightness, contrast, resolution, colors and fonts, then copy or download the result — all client-side, nothing ever leaves your device.

## Features

- **Image upload** — drag & drop or pick an image file
- **Live ASCII preview** — converts the image to text art in the browser
- **Controls** — brightness, contrast, resolution/width, color vs monochrome, invert, font size
- **Copy to clipboard** — copy the ASCII art as text
- **Download** — save the ASCII art as a file
- No uploads, no backend — 100% private, everything runs locally

## Tech Stack

- [Next.js](https://nextjs.org/) 15 (App Router, static export)
- [React](https://react.dev/) 19
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/) + `tailwindcss-animate`
- [shadcn/ui](https://ui.shadcn.com/) components (Radix UI primitives)
- [Lucide](https://lucide.dev/) icons

## Getting Started

```bash
npm install
npm run dev      # start dev server at http://localhost:3000
npm run build    # production build
npm start        # run production build
```

Node.js 18+ recommended. If you hit peer-dependency conflicts during install, use:

```bash
npm install --legacy-peer-deps
```

## Project Structure

```
app/                  # Next.js App Router pages and layout
  page.tsx            # main converter page
ascii-converter.tsx   # core ASCII conversion component
components/           # reusable UI
  theme-provider.tsx
  ui/                 # shadcn/ui primitives
lib/                  # utilities
public/               # static assets
styles/               # global styles
```

## Environment Variables

None required — the app runs fully client-side with no backend or API keys.

## Deployment

The app is statically exported (`output: 'export'` in `next.config.mjs`), so it can be hosted anywhere that serves static files:

```bash
npm run build   # outputs to ./out
```

Notes:

- The repo is synced from a v0.app project and was originally deployed on Vercel.
- When deployed under a subpath (e.g. GitHub Pages project pages), `next.config.mjs` sets `basePath: '/image-to-ascii'`. Remove `basePath` (and keep `output: 'export'`) when deploying to a root domain or Vercel, otherwise assets will resolve incorrectly.

## Built by

Built by Girish Lade — https://ladestack.in
