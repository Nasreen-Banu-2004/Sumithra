Climate & Environmental Analytics — Next.js + Python

Data-driven climate and environmental analytics with a modern Next.js (App Router) frontend and a Python analysis layer. It provides interactive dashboards for climate trends, environmental metrics, and simple predictive insights. No authentication or deployment setup is included.

## Prerequisites
- Node.js ≥ 20.9
- Python 3.10+ with pip
- Windows, macOS, or Linux

## Setup

1) Install Node dependencies:

```bash
npm install
```

2) Install Python dependencies:

```bash
python -m pip install -r analytics/requirements.txt
```

## Development

Start the dev server:

```bash
npm run dev
```

Visit http://localhost:3000.

Useful checks:

- Lint: `npm run lint`
- Typecheck: `npm run typecheck`

## Frontend

- Next.js 16 (App Router) + Tailwind CSS
- Charts: Recharts
- Pages:
  - `/` Overview dashboard
  - `/trends` Climate trend analysis
  - `/environment` Environmental metrics
  - `/predictions` Simple projections

## Backend (Python Analytics)

- Data ingestion and processing via pandas/numpy
- Simple trend fitting and projections via numpy/scikit-learn
- Scripts live in `analytics/` and read sample CSVs from `data/`

APIs (JSON):

- `GET /api/overview` — Aggregated headline metrics and series
- `GET /api/trends` — Temperature and CO₂ trends from CSV
- `GET /api/environment` — Air quality series (PM2.5)
- `GET /api/predictions` — Linear forecasts for temp anomaly and CO₂

The Next.js API routes spawn a Python process and return its JSON output. Python path can be overridden with the `PYTHON` env var.

## Data Sources (Sample)

Included mock CSVs under `data/`:
- `temperature.csv` (year, anomaly)
- `co2.csv` (year, ppm)
- `air_quality.csv` (year, pm25)

Replace with public datasets (e.g., NASA GISTEMP, NOAA, Mauna Loa CO₂, WHO air quality). Keep format consistent or adapt the Python scripts.

## Notes

- No authentication or deployment integration is included.
- Keep API calls server-side for performance and to reuse Python efficiently.
