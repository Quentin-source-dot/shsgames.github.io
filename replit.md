# SHS Games

An unblocked games platform built with React + Vite + TypeScript.

## Project Structure

- `app/` - Main application source (Vite root)
  - `src/components/` - React UI components
  - `src/pages/` - Page-level components (auto-loaded via glob)
  - `src/runtime/` - Error boundary, keybinds
  - `src/hooks/` - Custom React hooks
  - `src/util/` - Utility functions
  - `styles/` - LESS stylesheets
  - `public/` - Static assets including games
  - `games.ts` - Game catalog data
  - `manifest.json` - PWA manifest (also defines `base` path)
- `vite.config.ts` - Vite build configuration
- `tsconfig.json` - TypeScript config
- `package.json` - Dependencies and scripts

## Tech Stack

- React 18 (with compatibility shim for ReactDOM.render)
- Vite 5 with PWA plugin
- TypeScript
- photoncss (UI component library, bundled with its own React - deduplicated via Vite)
- react-router-dom v6
- react-query v3
- LESS stylesheets

## Key Configuration Notes

- **Port**: Dev server runs on `0.0.0.0:5000` for Replit proxy
- **AllowedHosts**: Set to `true` for Replit proxy compatibility
- **React deduplication**: `resolve.dedupe: ["react", "react-dom"]` prevents duplicate React from photoncss's bundled node_modules
- **glob fix**: `import.meta.glob(..., { eager: true })` replaces deprecated `import.meta.globEager`
- **Base path**: Defined in `app/manifest.json` as `"base": "/"`

## Scripts

- `npm run dev` - Start dev server (port 5000)
- `npm run build` - TypeScript check + Vite build to `public_html/`
- `npm run preview` - Preview production build

## Deployment

Configured as static site deployment:
- Build command: `npm run build`
- Public directory: `public_html`
