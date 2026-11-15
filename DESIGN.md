---
name: EU Leads Demo Templates
version: "alpha"
description: "Visual identity for the five GitHub Pages demo templates (salon, hotel, resort, restaurant, café) used to show EU small businesses what their website could look like. One shared system, one palette per template."
colors:
  primary: "#221d17"
  ink: "#221d17"
  background: "#faf7f1"
  card: "#f5efe6"
  sand: "#f3d9b0"
  gold: "#d99a2b"
  whatsapp: "#25d366"
  restaurant-deep: "#1e2b25"
  cafe-coffee: "#3a2c22"
typography:
  display:
    fontFamily: "Cormorant Garamond, Georgia, serif"
    fontSize: 2.5rem
  h1:
    fontFamily: "Cormorant Garamond, Georgia, serif"
    fontSize: 2.25rem
  h2:
    fontFamily: "Cormorant Garamond, Georgia, serif"
    fontSize: 1.5rem
  body:
    fontFamily: "Inter, system-ui, sans-serif"
    fontSize: 1rem
  small:
    fontFamily: "Inter, system-ui, sans-serif"
    fontSize: 0.875rem
  label-caps:
    fontFamily: "Inter, system-ui, sans-serif"
    fontSize: 0.6875rem
rounded:
  sm: 4px
  md: 8px
  lg: 16px
  pill: 999px
spacing:
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 32px
  section: 48px
components:
  button-primary:
    backgroundColor: "#221d17"
    textColor: "#ffffff"
    rounded: 999px
    padding: "11px 22px"
  button-whatsapp:
    backgroundColor: "#25d366"
    textColor: "#ffffff"
    rounded: 999px
  card:
    backgroundColor: "#f5efe6"
    rounded: 16px
    padding: "16px 24px"
---

## Overview

Warm, editorial, premium — the demo must feel like a website worth paying for, not a wireframe. Every template shares one system: Cormorant Garamond display type, Inter for body and booking UI, warm paper backgrounds, dark ink text, and a single gold accent. Only the per-template palette changes. Spacing follows an 8px scale; no arbitrary values (no 13px or 27px gaps).

## Colors

- **Ink (#221d17):** headlines, body text, primary buttons. Always on warm paper, never on pure white.
- **Background (#faf7f1):** warm paper page foundation, softer than white.
- **Card (#f5efe6):** panels, menus, booking steps.
- **Gold (#d99a2b):** the sole accent for prices, stars, and calls to action that are not the primary button.
- **WhatsApp (#25d366):** only for WhatsApp buttons and the sticky mobile bar. Note: white text on this green measures 1.98:1, below WCAG AA — a deliberate brand exception, matching WhatsApp's own button; body text never uses this combination.
- **Per-template palettes:** salon — cream, tan, sage; hotel — green and gold; resort — teal and sand; restaurant — deep green (#1e2b25) and brass; café — cream and terracotta/coffee (#3a2c22). A template never borrows another template's palette.

## Typography

- **Display (Cormorant Garamond):** business name, hero headline, section headings. Never use it for prices or booking UI.
- **Body (Inter):** everything else, including prices, times, buttons and forms.
- **Label caps:** 11px, uppercase, wide letter-spacing for kickers ("HAIR · BEAUTY · AMSTERDAM") and eyebrows above headings.

## Spacing

- **8px base unit; every spacing value is a multiple of 8** (4px only for dense inline gaps). Section padding is 48px on desktop, 32px on mobile. Card padding is 16–24px. Never eyeball padding.
- **External spacing is always larger than internal spacing:** gaps between sections exceed gaps inside a card, which exceed gaps between lines.

## Layout

- **Mobile-first, max-width content column, one primary action per screen.** The booking/reservation action is reachable within one tap at all times: a sticky Book/WhatsApp bar on mobile and a header Book button on desktop.
- **Hours, address and phone appear on the first screen** (hero chips) — the thing almost no real restaurant or café site does, and the reason these demos convert.
- **Header (hard rule, learned from a real bug):** `.nav` uses `min-height`, never a fixed height, so a long business name can wrap to two lines without clipping. The header Book button is `white-space: nowrap` with `flex-shrink: 0`. On phones (≤640px) the logo is 18px, wrap padding is `0 14px`, and the hamburger is 36px wide with `flex-shrink: 0`. Verify every template at 390px width before shipping.
- **Menus are text with prices shown**, never PDF-only. Prices always carry "from" where they vary.

## Components

- **Buttons:** pill-shaped (999px radius), dark ink primary, gold only for secondary emphasis, WhatsApp green only for WhatsApp. Minimum tap target 24px, comfortable target 44px.
- **Booking flow:** date → time (taken slots disabled) → party size / items → details → confirmation with a reference code (e.g. CP-2026-5278) and a WhatsApp link carrying that reference.
- **Cards:** 16px radius, warm card background, no heavy shadows.
- **Map:** Google Maps embed in the contact section, matching the business address.

## Personalisation

Every template personalises from URL query params `?name=&phone=&address=&city=` — name, phone (including `tel:` and `wa.me` links), address and city change everywhere: title, hero, footer, booking confirmation, WhatsApp messages and the Maps embed. No Supabase keys, no backend, no base64 images; photos are remote Unsplash URLs only, each verified to return HTTP 200. Placeholder contact emails use `.example` domains.

## Don't

- No gradients, no purple/indigo palette, no glassmorphism, no emoji as icons.
- No border radius above 16px except pill buttons.
- No arbitrary spacing values, no fixed-height headers, no PDF-only menus, no video heroes, no load pop-ups.
- Never invent a business's contact details — personalisation values come from verified lead data only.
