# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML landing page for a dental clinic (Dra. Liciara Alves) in Hortolândia, São Paulo, Brazil. Written in Portuguese (pt-BR).

## Development

**No build system, no tests, no linter.** The site is a single `index.html` file with embedded CSS and JavaScript.

- Edit `index.html` directly
- Open in browser to preview changes
- Deploy via FTP or file transfer to Apache server

**CDN dependencies:**
- Bootstrap 5.3.2 (CSS + JS bundle)
- Google Fonts (Inter, Merriweather)

## Architecture

Single `index.html` with all CSS in `<style>` and all JS in `<script>` at the end of `<body>`. Sections use anchor navigation (`#about`, `#specialties`, `#gallery`, `#reviews`, `#contact`).

**Static assets in `/public/`:**
- `FotoHero.jpeg` - Hero section photo
- `consultorio/` - Clinic interior photos for gallery carousel

**Key JS functions:**
- `scheduleConsultation()` / `openWhatsApp()` — Open WhatsApp chat (number: 5519953316535)
- `openGoogleReview()` — Open Google Maps listing
- IIFE `setupFloatingButtonAlternation()` — Alternates floating button between WhatsApp and Instagram every 7 seconds
- IntersectionObserver — Fade-in animations on scroll for `.section` elements
- Bootstrap Modal — Image lightbox for gallery photos

## Server Configuration

Apache `.htaccess` handles: HTTPS redirect, domain redirect (`draliciara.com.br` → `www.liciaraalvesodontologia.com.br`), GZIP, browser caching, security headers, and `.html` extension removal.

## Color Scheme

Gold/brown palette:
- Primary gold: `#c49b61`
- Secondary gold: `#b8905a`
- Dark brown (hero title): `#6b5b47`
- Text: `#333` (dark), `#666` (muted)
- Stars/accents: `#ffd700`

## Integrations

- **WhatsApp:** Floating button + CTA buttons throughout page
- **Instagram:** `@dra.liciaraalves` — floating button alternates with WhatsApp
- **Google Maps:** Embedded iframe in contact section
- **SEO:** `sitemap.xml`, `robots.txt`, Open Graph/Twitter Card meta tags, geo-location meta tags
