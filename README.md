# CharterIQ

CharterIQ is an internal decision-support dashboard for SAIL bulk cargo procurement. It helps procurement teams evaluate coking coal, thermal coal, and iron ore routes into India's East Coast ports.

The dashboard combines cargo inputs, vessel feasibility checks, freight-rate forecasting, explainable model drivers, and operational port risk signals in one workspace.

## Features

- **Procurement & Feasibility Engine**
  - Configure commodity, volume, origin, SAIL plant, destination, and laycan.
  - Check physical vessel constraints before rate recommendations.
  - Identify draft restrictions and split-parcel routing options.
  - Receive BUY, WAIT, vessel, contract, and savings recommendations.
- **Analytics & Forecasting**
  - View a 90-day freight forecast with confidence bands.
  - Compare the 10th, 50th, and 90th percentile forecast levels.
  - Review SHAP-style feature attribution for bunker fuel, BDI, congestion, and seasonality.
  - Compare historical spot spend with AI-timed procurement through the ROI view.
- **Risk Radar & Port Intelligence**
  - Review the East Coast port matrix, draft limits, LOA, berths, discharge rates, and congestion.
  - Monitor origin-port utilization, weather, queues, and delays.
  - Track geopolitical, seasonal, insurance, and IMO compliance risks.
- **Judge demo scenarios**
  - Use the header selector to load complete example routes in one click.

## Demo scenarios

| Scenario | Route | Expected signal |
| --- | --- | --- |
| A: Draft Restriction Alert | 150,000 MT Coking Coal, Newcastle to Haldia | Haldia draft restriction and split Panamax parcels |
| B: Cost Optimization Window | 75,000 MT Coking Coal, Richards Bay to Vizag | WAIT 12 DAYS and high projected savings |
| C: Sanctions / Risk Trigger | 50,000 MT Thermal Coal, Vostochny to Paradip | Geopolitical and insurance risk review |

## Requirements

- Node.js 18 or newer
- npm

## Run locally

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

Open the local URL printed by Vite, normally `http://localhost:5173`.

## Available scripts

```bash
npm run dev       # Start Vite with hot reload
npm run build     # Create a production build in dist/
npm run preview   # Preview the production build locally
npm run lint      # Run ESLint across the repository
```

## Project structure

```text
src/
├── App.jsx                         # Application shell and view selection
├── index.css                       # Global theme, layout, and component styles
├── components/
│   ├── Header.jsx                   # Branding, market rates, and demo scenarios
│   ├── Sidebar.jsx                  # Main view navigation
│   ├── ImporterPortal.jsx           # Procurement and feasibility workspace
│   ├── AnalyticsPortal.jsx          # Forecasting and explainability view
│   └── PortIntelligencePortal.jsx   # Port matrix and operational risk view
└── data/
    └── mockData.js                  # Local route, market, forecast, and port data
```

## Data and scope

This version is a frontend prototype. Dashboard values are local mock data in `src/data/mockData.js`; no live market API, authentication, procurement system, or database is connected yet. Replace the mock data layer with approved SAIL data services before production use.

## Production build

Run:

```bash
npm run build
```

The generated static files are written to `dist/` and can be served by any static web server.
