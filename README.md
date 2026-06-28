# Portfolio Diversification Score Calculator

An interactive single-page web app that quantifies how well-diversified an investment portfolio is across multiple metrics.

## Features

- **Three diversification metrics:**
  - Herfindahl-Hirschman Index (HHI) — 0–10,000 scale, lower = more diversified
  - Normalized HHI — 0–100 scale
  - Shannon Entropy — 0–100 scale, higher = more diversified
- **Portfolio composition breakdown** — equities, cash, and bonds
- **Geographic exposure table** — allocation by exchange/region
- **Currency exposure table** — allocation by currency
- **Holding overlap warnings** — flags pairs of holdings with significant underlying overlap
- **Live allocation progress bar** — validates that all positions sum to 100%
- **Example portfolio** — one-click load to explore the tool

## How to Use

1. Open `index.html` in any modern browser — no build step or server required.
2. Add your holdings using the dropdown (select a security type) and enter each position's allocation percentage.
3. Optionally enter cash and/or bonds allocations.
4. Ensure the total reaches 100%, then click **Calculate Diversification Score**.
5. Switch between metric views using the buttons above the gauge.

## Metrics Explained

| Metric | Range | Interpretation |
|---|---|---|
| HHI | 0 – 10,000 | Lower = more diversified. 10,000 = single holding |
| Normalized HHI | 0 – 100 | Adjusts HHI for number of positions. 0 = perfectly equal |
| Shannon Entropy | 0 – 100 | Higher = more diversified. 100 = perfectly equal |

## What This Calculator Measures (and Doesn't)

**It measures:** concentration at the position level — how evenly your capital is spread across holdings.

**It does not capture:**
- Underlying diversification within ETFs (a global ETF holding 3,500 stocks vs. a single stock both count as one position)
- Overlap between holdings (a US large-cap ETF is a significant portion of a global ETF)
- Correlation between holdings
- Sector or factor concentration
- Currency risk differences

## Supported Securities

The tool includes a built-in database of anonymised security types spanning multiple geographies:

| Code | Type | Geography | Exchange | Currency |
|---|---|---|---|---|
| `SG-ETF` | ETF | Singapore | Singapore | SGD |
| `CN-ETF` | ETF | China | NYSE | USD |
| `US-STOCK` | Stock | USA | NYSE | USD |
| `EM-ETF` | ETF | Emerging Markets | LSE | GBP |
| `EU-ETF` | ETF | Europe (ex-UK) | LSE | GBP |
| `GLOBAL-ETF` | ETF | Global | LSE | GBP |
| `US500-ETF` | ETF | USA | LSE | GBP |

## License

MIT
