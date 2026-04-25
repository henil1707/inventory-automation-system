# Inventory Automation System

> **Python-based pharma inventory intelligence** — batch-level stock analysis, expiry risk tracking, demand forecasting, and automated reorder alerts built for real-world distribution operations.

---

## The Problem

Pharmaceutical distributors lose revenue in two silent ways:

- **Stock dumping** — slow-moving and non-moving products expire before they sell
- **Stockout surprises** — fast-moving SKUs run out before the next reorder arrives

Manual Excel-based tracking misses both. This system automates the entire detection and alert pipeline.

---

## What This System Does

| Module | What it solves |
|---|---|
| **Stock classification** | Flags every SKU as fast / slow / dead stock based on velocity |
| **Expiry risk engine** | Segments batches by days-to-expiry (0–60 / 61–90 / 91–180 / 180+) |
| **Demand forecasting** | Projects 30 / 60 / 90-day sales trends per product |
| **Reorder automation** | Calculates safety stock and minimum reorder quantity per SKU |
| **Alert reports** | Auto-generates stock alert, expiry, and reorder recommendation reports |

---

## Key Results

- **15% reduction** in stock dumping by catching slow-movers before expiry window closes
- **20% reduction** in expiry wastage through batch-level expiry segmentation
- **Eliminated manual triage** — what took 4+ hours per week now runs in minutes

---

## Tech Stack

```
Python 3.x
├── Pandas          — data manipulation and batch analysis
├── NumPy           — numerical computations and rolling averages
├── Jupyter Notebook — interactive analysis and report generation
└── openpyxl        — Excel report output
```

---

## Project Structure

```
inventory-automation-system/
│
├── Inventory Automation.ipynb    # Main analysis notebook
└── README.md
```

---

## How It Works

### 1. Stock classification
Every SKU is scored by movement velocity over a trailing 90-day window. Products are classified as:
- **Fast moving** — consistently high velocity, prioritise restock
- **Slow moving** — declining velocity, flag for promotion or return
- **Dead / non-moving** — zero sales in window, immediate action required

### 2. Expiry risk segmentation
Each batch is mapped to an expiry bucket:

```
0–60 days    → Critical risk   → Immediate markdown / return action
61–90 days   → High risk       → Accelerate sales or bundle offer
91–180 days  → Medium risk     → Monitor weekly
180+ days    → Low risk        → Standard reorder cycle
```

### 3. Demand forecasting
Rolling 30 / 60 / 90-day sales averages are computed per SKU to project near-term demand. Safety stock and reorder quantities are calculated using:

```
Reorder Point = (Average Daily Sales × Lead Time) + Safety Stock
Safety Stock  = Z-score × Std Dev of Daily Sales × √Lead Time
```

### 4. Automated alerts
The system outputs three actionable reports:
- **Stock alert report** — SKUs needing immediate attention
- **Expiry breakdown report** — batch-level expiry risk by product
- **Reorder recommendation report** — quantities and timing per SKU

---

## Getting Started

### Prerequisites
```bash
pip install pandas numpy openpyxl jupyter
```

### Run
```bash
git clone https://github.com/henil1707/inventory-automation-system.git
cd inventory-automation-system
jupyter notebook "Inventory Automation.ipynb"
```

Replace the sample data section in the notebook with your own inventory CSV to run on live data.

---

## Sample Output

The notebook generates structured DataFrames for each report type. Example stock alert output:

| SKU | Product | Movement | Days to Expiry | Reorder Qty | Action |
|---|---|---|---|---|---|
| SKU-001 | Product A | Dead | 48 | 0 | Return / markdown |
| SKU-042 | Product B | Slow | 74 | 0 | Accelerate sales |
| SKU-118 | Product C | Fast | 210 | 500 units | Reorder now |

---

## Business Context

This system was built to solve real operational challenges in pharmaceutical distribution — specifically around reducing wastage from expired stock and preventing stockouts on high-velocity SKUs. The classification logic and expiry segmentation thresholds are calibrated for pharma distribution cycles.

---

## Author

**Henil Jariwala** — Senior Data Analyst, Pharma Industry

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/henil-jariwala)
[![GitHub](https://img.shields.io/badge/GitHub-henil1707-black?style=flat&logo=github)](https://github.com/henil1707)

---

## Related Projects

- [inventory-dashboard-powerbi](https://github.com/henil1707/inventory-dashboard-powerbi) — Power BI dashboard visualising inventory health metrics

---

*Built with Python · Pandas · Jupyter Notebook*

