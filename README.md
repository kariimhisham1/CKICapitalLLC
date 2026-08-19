# CKI Capital LLC — Wholesale Real Estate Landing Page

Two files, drop-in ready for a Next.js (App Router) project:

- `data.json` — every piece of copy, form field, stat, testimonial, and FAQ. Edit this to change content without touching code.
- `page.tsx` — the full page component (`app/page.tsx`). Imports `data.json` directly.

## Install

```bash
npm i lucide-react
```

Tailwind CSS must already be configured in the project (this uses utility classes throughout — no extra Tailwind config needed beyond the defaults).

## Place the files

```
app/
  page.tsx     <- this file
  data.json    <- same folder
```

If your project structure differs, just make sure the `import data from "./data.json"` path resolves, and that your `tsconfig.json` has `"resolveJsonModule": true` (Next.js sets this by default).

## Wire up the form

The form currently POSTs to `/api/lead` and treats any response (including a failed fetch) as success, so the template is fully clickable out of the box. Replace the body of `handleSubmit` in `page.tsx` with your real integration — a server action, a CRM webhook (Podio, REsimpli, FollowUpBoss, etc.), or your own API route.

## What's included

- Sticky header with mobile menu
- Hero section with background photo, trust badges, and the offer form
- **Offer form** with the same field set and **TCPA-style consent checkbox** as the reference design — full client-side validation (name, phone, address, city, state, email format, and required consent), inline error states, loading state, and a success screen
- Stats strip, 3-step process, 6-item "why us" grid, situational tag list, testimonials, FAQ accordion, CTA banner, and footer with required disclosures
- A custom brand mark ("the seal") used as the signature visual element throughout
- Fully responsive, keyboard-focusable form controls, and `prefers-reduced-motion` respected

## Fonts

Loaded via a `<style jsx global>` Google Fonts `@import` (Fraunces / Sora / IBM Plex Mono) so the file works standalone. For production, swap this for `next/font` to avoid the render-blocking `@import` and get self-hosted, optimized fonts.

## Legal note

The consent checkbox language is a starting point modeled on standard TCPA-style lead-gen consent. Have counsel review the exact wording, and the `footer.disclosure` text, before this goes live — requirements vary by state and by how you plan to use the phone number collected.
