# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A modern landing page website for an app, inspired by winston.cafe. Built to showcase app features with smooth animations, video demonstrations, and a polished design.

## Tech Stack

- **Next.js 16** (React framework with App Router)
- **React 19**
- **TypeScript**
- **Tailwind CSS v4** (utility-first styling)
- **ESLint** (code quality)

## Development Commands

```bash
# Start development server (localhost:3000)
npm run dev

# Build for production
npm build

# Start production server
npm start

# Run linter
npm run lint
```

## Project Structure

This project uses Next.js **App Router** (not Pages Router):

- `app/` - Main application directory
  - `page.tsx` - Homepage component
  - `layout.tsx` - Root layout (wraps all pages)
  - `globals.css` - Global styles and Tailwind imports
- `public/` - Static assets (images, videos, fonts)
- `tailwind.config.ts` - Tailwind configuration
- `next.config.ts` - Next.js configuration

## Key Architecture Notes

**App Router Routing:**
- File-based routing: files in `app/` directory become routes
- `page.tsx` files define route UI
- `layout.tsx` files define shared layouts
- Server Components by default (use `'use client'` directive for client-side interactivity)

**Styling Approach:**
- Tailwind CSS for utility classes
- Define custom colors/fonts in `tailwind.config.ts`
- Global styles in `app/globals.css`

**Inspiration Reference:**
- Target aesthetic: winston.cafe
- Features to implement: hero section, feature showcase with videos/images, smooth scrolling, animations
