# Anastasia Literary Space

React/Vite one-page site based on the supplied design concept PDF.

## Run

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

## What is already implemented

- responsive one-page structure
- mobile navigation
- smooth-scroll navigation
- Framer Motion entrance/hover animations
- books section with format selector modal
- event list and booking/contact modal
- author-project request form
- gallery masonry layout
- typography/palette inspired by the supplied concept

## What still needs production integration

1. Replace photo placeholders with the author's real photos.
2. Replace sample event data with a CMS/database.
3. Connect forms to an email/CRM endpoint.
4. Connect the purchase CTA to a payment provider such as Stripe Checkout.
5. After successful payment, generate/provide the selected EPUB/PDF/MOBI file securely from the backend.
6. Add legal pages (mentions légales, confidentialité, CGV) before production launch.

### Stripe architecture

Keep payment secret keys on a backend, never in React. The frontend should POST the selected book/format to `/api/create-checkout-session`, receive the Checkout URL, and redirect the buyer. The backend creates the Stripe Checkout Session and handles the webhook for successful payment before exposing the download link.
