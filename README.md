# Sales Analytics Reports

This repository contains exported sales and finance reports for the fictional AtliQ Hardwares dataset. The available artifacts show customer performance, market results against targets, and profit-and-loss views across fiscal periods and markets.

The repository contains report exports only. It does not include the source workbook, raw data, Power Query steps, data model, or formulas used to generate them.

## Reports

- [Customer performance](reports/customer-performance-report.pdf): net sales by customer for 2019–2021, including 2021 versus 2020 growth.
- [Market performance versus target](reports/market-performance-vs-target-report.pdf): country-level net sales and 2021 target variance.
- [P&L by fiscal year](reports/pl-by-fiscal-year.pdf): net sales, cost of goods sold, gross margin, and gross margin percentage for 2019–2021.
- [P&L by market](reports/pl-by-market.pdf): 2021 profit-and-loss measures by market.
- [P&L by month](reports/pl-by-month.pdf): monthly and quarterly profit-and-loss results, plus year-over-year net sales comparisons.

## Features

- Customer-level sales performance across three fiscal years.
- Country-level sales target variance analysis.
- Profit-and-loss summaries by year, month, and market.
- Filters recorded in the exports for region, market, division, customer, and fiscal year.
- Conditional formatting that highlights relative values and variances.

## Technology stack

The PDF metadata identifies Microsoft Excel LTSC as the export tool. The original project notes describe an Excel workflow using Power Query for transformation, Power Pivot for the data model, pivot tables for reporting, and DAX for calculated fields. Those editable assets are not included, so that implementation cannot be independently inspected here.

## Architecture

```mermaid
flowchart LR
    A[Source sales and finance data] --> B[Power Query transformations]
    B --> C[Power Pivot data model]
    C --> D[DAX measures and pivot reports]
    D --> E[PDF report exports]
```

The diagram reflects the workflow described in the original project notes. This repository begins at the final PDF export stage.

## Installation and use

No installation is required.

1. Clone the repository.
2. Open any file in [`reports/`](reports/) with a PDF viewer.

```bash
git clone https://github.com/Puneeth0106/sales-analytics-reports.git
cd sales-analytics-reports
```

## Configuration

Runtime configuration is not required. The optional `.env.example` entry documents where a separately obtained source workbook could be stored locally; no included code reads it.

## Reproducing the reports

The reports cannot be regenerated from this repository alone. To reproduce or modify them, obtain the original Excel workbook and its source data, refresh the queries and data model in a compatible version of Excel, then export the report worksheets to PDF.

## Project structure

```text
.
├── reports/
│   ├── customer-performance-report.pdf
│   ├── market-performance-vs-target-report.pdf
│   ├── pl-by-fiscal-year.pdf
│   ├── pl-by-market.pdf
│   └── pl-by-month.pdf
├── .env.example
├── .gitattributes
├── .gitignore
└── README.md
```

## Known limitations

- Only static PDF exports are available; source data and editable Excel files are absent.
- Filters and pivot controls shown in the PDFs are not interactive.
- The reports mix INR and USD units; check each report heading before comparing values.
- The monthly P&L export spans four pages, with continuation columns isolated on later pages.
- Data accuracy and transformation logic cannot be independently validated without the source workbook and data.
