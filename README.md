# NEBULA — Ticket Booking Website

A responsive, interactive ticket-booking website prototype built with plain HTML, CSS, and JavaScript. It requires no build step or package installation.

## Run locally

1. Extract the ZIP.
2. Open `index.html` in a modern browser.

For a local development server, open a terminal in this folder and run either:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

You can also use the VS Code **Live Server** extension.

## Working demo features

- Responsive dark, neon-inspired design
- Event cards and category filters for concerts, movies, comedy, workshops, and transit
- Search by event, venue, category, and city
- Sort by price or date
- Save/favourite events (stored in browser localStorage)
- Event detail modals
- Interactive seat selection for movie and concert demos
- Ticket tier and quantity selection for other event types
- Booking summary with service-fee calculation
- Demo checkout form with UPI, card, and wallet method selection
- Demo booking confirmation
- Ticket wallet with saved demo bookings
- Newsletter form interaction (simulated)
- Mobile-responsive layout

## Important: prototype, not a production ticketing backend

This ZIP is a fully interactive **front-end demo**, not a production payment or inventory system. It intentionally does not charge money.

- Event data is sample data in `app.js`.
- Seat availability is simulated in the browser and is not shared between users.
- Checkout only creates a local demo booking in `localStorage`.
- No real payment provider is connected.
- Ticket IDs shown are demo references; the UI does not create a cryptographically secure or scannable admission credential.
- Newsletter signup is simulated.
- Images are loaded from Unsplash and require an internet connection.

Before accepting real orders, build a backend with PostgreSQL transactions and unique inventory constraints, reservation expiry, payment-provider webhooks and signature validation, idempotency, refunds, ticket issuance, authentication, authorization, logging, and abuse prevention. Never trust a frontend-only seat lock or a browser-generated payment-success state.

## Files

- `index.html` — app layout and semantic structure
- `styles.css` — responsive design system, components, and animations
- `app.js` — sample event data, filtering, seat selection, demo checkout, and local ticket wallet

## Customizing

Edit the `events` array near the top of `app.js` to change sample events. Each event has `id`, `title`, `category`, `date`, `dateLabel`, `city`, `venue`, `price`, `image`, and `description` fields.

For a production implementation, suggested next step:
- Next.js + TypeScript frontend
- NestJS API
- PostgreSQL as the source of truth for inventory, reservations, orders, and tickets
- Redis for caching/rate limits/coordination (not the sole guarantee against double booking)
- Razorpay or Cashfree after business and integration eligibility checks
