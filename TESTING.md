# Testing

## Automated tests

The project uses Vitest, jsdom, React Testing Library, and jest-dom.

Run:

```powershell
npm run test
```

Automated coverage currently verifies:

1. Initial owner metrics and redemption records render.
2. Search text filters the redemption table.
3. Sidebar navigation changes the active view.
4. The create-reward dialog opens, accepts input, and closes after submission.

## Manual test plan and recorded results

Tested on November 19, 2026 using the local Vite development server and production build.

| ID | Test | Steps | Expected | Result |
|---|---|---|---|---|
| M1 | Desktop layout | Run `npm run dev`; open `http://localhost:5173` at 1440 px width | Sidebar, metrics, table, chart, and fraud panel are visible and aligned | Pass |
| M2 | Search | Enter “Jackson” in redemption search | Only Jackson Lee remains | Pass |
| M3 | Status filter | Select “Flagged” | Only Noah Wilson remains | Pass |
| M4 | Clear filters | Select “All status” and clear search | All seeded redemptions return | Pass |
| M5 | Navigation | Click Rewards, Customers, Codes, and Payouts | Each view heading and placeholder update | Pass |
| M6 | Create reward | Open dialog; enter name and points; submit | Dialog closes and success toast appears | Pass |
| M7 | Modal cancel | Open then close dialog by Cancel or Close | Dialog closes without creating a reward | Pass |
| M8 | Tablet layout | Resize to approximately 900 px | Metrics become a 2-column grid and lower panels stack | Pass |
| M9 | Mobile layout | Resize to approximately 390 px | Sidebar becomes bottom navigation and tables remain horizontally scrollable | Pass |
| M10 | Production build | Run `npm run build` | TypeScript and Vite complete without errors | Pass |
| M11 | Invalid code outcome | Prototype has no backend, so enter an unknown code is not available | Production behavior is documented in assumptions and architecture | Documented gap |

## Test limitations

The current prototype uses seeded in-browser data and does not include authentication, a backend, a database, QR decoding, or real purchase-code validation. The manual test plan therefore validates presentation and client interactions, not production fraud or payment behavior.
