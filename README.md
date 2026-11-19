# Flowdesk

Flowdesk is a factory-owner rewards operations dashboard for a business that sells physical products in boxes. It demonstrates how customers can prove a purchase, how purchase codes are protected against reuse, and how the factory owner manages and monitors reward activity.

## Features

- Unique-box-code redemption workflow concept with QR-code and fallback-code assumptions.
- Fraud controls, including reuse indicators, blocked codes, review status, and an owner-facing health score.
- Reward creation dialog with name, points requirement, reward type, and description.
- Searchable and filterable redemption activity table.
- Active-customer, redemption, reward-cost, and issued-reward metrics.
- Redemption activity chart and fraud-protection summary.
- Responsive layouts for desktop, tablet, and mobile use.

## Tech stack

- React 19
- TypeScript
- Vite 8
- Lucide React icons
- CSS
- Oxlint
- Vitest and React Testing Library for automated tests

## Getting started

### Prerequisites

- Node.js 20 or newer
- npm

### Setup

```powershell
npm install
cp .env.example .env
npm run dev
```

On Windows PowerShell, `.env` can instead be created with:

```powershell
Copy-Item .env.example .env
```

Open the local URL printed by Vite, normally `http://localhost:5173`.

### Available scripts

```powershell
npm run dev       # Start the development server
npm run build     # Type-check and build for production
npm run preview   # Preview the production build locally
npm run lint      # Run Oxlint
npm run test      # Run the automated test suite once
npm run test:watch
```

## Deployment

No public deployment URL is available in this prototype. The production build is in `dist/` after running `npm run build` and can be deployed to any static host such as Netlify, Vercel, or GitHub Pages.

## Environment variables

Copy `.env.example` for the local template. This front-end prototype uses seeded local data, so no environment variable is currently required for normal operation.

## Documentation

- `ASSUMPTIONS.md` — gaps and design choices
- `ARCHITECTURE.md` — stack rationale, data model, and system diagram
- `AI_LOG.md` — significant AI-assisted interactions and corrections
- `TESTING.md` — automated and manual test results
