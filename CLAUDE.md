# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Astro-based web project counting down to the day of the developers wedding. The project uses TypeScript with strict type checking enabled.

## Development Commands

Run from the project root:

- `npm run dev` - Start development server at `localhost:4321`
- `npm run build` - Build production site to `./dist/`
- `npm run preview` - Preview production build locally
- `npm run astro ...` - Run Astro CLI commands (e.g., `astro add`, `astro check`)

## Architecture

### Directory Structure

- `src/pages/` - File-based routing (`.astro` files become routes)
- `src/layouts/` - Reusable page layouts that wrap page content
- `src/components/` - Reusable Astro components
- `src/assets/` - Static assets (images, SVGs) processed by Astro
- `public/` - Static files served as-is (favicon, etc.)

### Key Concepts

**Astro Components**: Files with `.astro` extension have three parts:
1. Frontmatter (TypeScript/JavaScript between `---` fences)
2. Template (HTML with component syntax)
3. Scoped styles (optional `<style>` tag)

**Layout Pattern**: The `Layout.astro` component provides the base HTML structure. Pages import and wrap content in layouts using the `<slot />` pattern.

**Asset Imports**: Images and SVGs in `src/assets/` are imported as modules and optimized. Access the URL via `.src` property (e.g., `astroLogo.src`).

## Configuration

- `astro.config.mjs` - Main Astro configuration (currently using defaults)
- `tsconfig.json` - Extends `astro/tsconfigs/strict` for strict TypeScript checking
