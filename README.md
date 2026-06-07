# 👕 Taylor Stitch Product Catalog Scraper — Web Scraping & Data Pipeline

## 📌 Project Overview

This project is an end-to-end **web scraping and product catalog extraction pipeline** built in Python for **TaylorStitch.com** — a premium US men's clothing and apparel brand running on Shopify. The scraper uses paginated API calls to capture the entire product catalog, cleans and transforms the raw data, generates internal SKUs, and exports a final master catalog ready for product data operations.

---

## 📊 Key Results

| Metric | Value |
|---|---|
| Pages Scraped | Multiple (100 products/page) |
| Raw Entries Captured | 4,806 rows |
| Unique Products (after dedup) | 3,659 products |
| Duplicate Rows Removed | 1,147 |
| Output Format | CSV (master catalog) |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core language |
| Requests | HTTP requests & paginated API calls |
| Pandas | Data transformation & cleaning |
| Shopify JSON API | Full product catalog extraction |

---

## 🔄 Pipeline Workflow

```
Step 1 — Setup
  └── Configure target domain: taylorstitch.com
      Base URL: /products.json

Step 2 — Extraction (Paginated)
  ├── Loop: page=1, limit=100 → fetch products
  ├── Continue until empty response (end of catalog)
  ├── Extract: Product Title, Vendor, Raw Price, Product Type
  └── Total captured: 4,806 raw entries across all pages

Step 3 — Transformation
  ├── Convert Raw Price to float (USD)
  ├── Remove duplicate products (keep first occurrence)
  ├── Generate Internal SKU: INF-TYS-XXX-2026
  └── Final clean catalog: 3,659 unique products

Step 4 — Export
  └── taylor_stitch_master_catalog.csv
```

---

## 📋 Data Fields Extracted

| Field | Description |
|---|---|
| Internal SKU | Generated: `INF-TYS-XXX-2026` |
| Product Title | Full product name |
| Brand/Vendor | Product vendor/brand |
| Price (USD) | Cleaned float price |
| Product Type | Category/type of product |

---

## 📁 Repository Structure

```
taylor-stitch-catalog-scraper/
│
├── Taylor_stich.ipynb                  # Main scraping notebook
├── taylor_stitch_master_catalog.csv    # Cleaned final catalog (3,659 products)
└── README.md                           # Project documentation
```

---

## 🚀 How to Run

1. Open the notebook in **Google Colab** or Jupyter
2. Run all cells from top to bottom
3. Output CSV will be saved automatically as `taylor_stitch_master_catalog.csv`

```bash
pip install requests pandas
```

---

## 💡 Key Concepts Demonstrated

- Paginated API scraping (100 products per page, auto-stop at end)
- Full catalog extraction from Shopify JSON API
- Data cleaning — deduplication, price type conversion
- Custom Internal SKU generation from product titles
- ETL pipeline — Extract → Transform → Load (CSV)
- Production-ready catalog output for e-commerce data operations

---

## 🔗 Use Cases

This type of pipeline is directly applicable to:
- **Product catalog management** for US retail clients
- **E-commerce data operations** and catalog standardization
- **Competitive product research** and price monitoring
- **Data ingestion** for inventory management systems

---

## 👤 Author

**Md Murtoza Mahir**
Data Analyst | Python | Web Scraping | ETL | Power BI | SQL
📧 murtozamahir.info@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/murtoza-mahir)
🌐 [Portfolio](https://murtoza-mahir.github.io)
