# Where does your money go? Consumer prices in Morocco (2020-2026)

An interactive dashboard and a small pandas analysis on inflation, food versus non-food prices, and the 2026 diesel increase in Morocco.

**Live dashboard:** https://salmaelmansoury79.github.io/morocco-prices/

## Question

How much have prices really risen in Morocco since 2020, which categories drove it, and what does the 2026 diesel jump mean for a household?

## Key findings

- Cumulative consumer price rise from 2021 to 2025: **+16.6%** (HCP annual averages).
- Food prices rose **+26.9%** between 2022 and 2025, against **+7.5%** for non-food products. The gap was largest in 2023 (food +12.5%, non-food +1.7%).
- Diesel went from **11.50 MAD** per litre in February 2026 to about **16.90 MAD** on 1 November 2026 (+47%). A 50 L tank went from about 575 to 845 MAD.

## Data

| File | Content | Source |
|---|---|---|
| `inflation_annual.csv` | Average annual inflation 2020-2025 | HCP (Haut-Commissariat au Plan) |
| `inflation_by_category.csv` | Food and non-food inflation 2022-2025 | HCP |
| `fuel_diesel_2026.csv` | Diesel pump prices, 6 dates in 2026 | Moroccan business press (Bladi.net, Le Site Info, Finances News Hebdo, LesMRE) |

## Method

`analysis.py` loads the CSV files with pandas, compounds annual rates into a cumulative index (2020 = 100), computes the cost of a 50 L tank, and measures the food versus non-food gap. The dashboard is a single static HTML page (no framework, no external data calls).

Run it:

```
pip install -r requirements.txt
python analysis.py
```

## Limitations

- Figures were collected from HCP notes and press coverage, not from the raw HCP files. They should be checked against hcp.ma.
- Food versus non-food data for 2020 and 2021 is not included yet.
- Diesel prices vary by distributor (16.30 to 16.99 MAD in November 2026).
- Prices of individual products (bread, oil, milk) are not included yet.

## Next steps

- Add city-level inflation and individual product prices from HCP tables.
- Load the raw HCP files directly in the script.

Built by Salma El Mansoury, software engineering student.
