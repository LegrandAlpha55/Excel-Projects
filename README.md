# Sales Performance Analysis Dashboard

## 📌 Project Overview
This repository contains an end-to-end data cleaning and analytics project built around the raw dataset `Sales_transactions_2022_2025.csv`.
The objective is to clean unformatted transactional records, standardize data types, and build an interactive Microsoft Excel dashboard to analyze sales performance, regional revenue distribution, and product trends.

---

## 📁 Repository Contents
* **`Sales_transactions_2022_2025.csv`** — Raw, uncleaned transactional sales dataset containing real-world data anomalies.
* **`README.md`** — Project documentation, data dictionary, and cleaning methodology.

---

## 📊 Dataset Schema (`Sales_transactions_2022_2025.csv`)

| Column Name | Description | Data Cleaning Applied |
| :--- | :--- | :--- |
| **Order ID** | Unique transaction identifier | Verified uniqueness and removed exact duplicate rows |
| **Order Date** | Transaction date | Standardized mixed date formats (`YYYY-MM-DD`, `MM/DD/YYYY`, `DD.MM.YYYY`) and handled invalid entries |
| **Product Name** | Name of item sold | Removed leading/trailing spaces (`TRIM`) and standardized naming |
| **Category** | Product category | Standardized inconsistent text casing (`PROPER`) |
| **Region** | Geographic sales zone | Standardized region names (`North`, `South`, `East`, `West`) and handled blank cells |
| **Salesperson** | Sales representative | Removed extra spaces and fixed inconsistent capitalization |
| **Quantity Sold** | Units sold per order | Converted text numbers (e.g., `"five"`) to integers, resolved negative values and blanks |
| **Unit Price** | Price per unit | Stripped `$` symbols and spaces, converted to numeric currency format |
| **Total Sales** | Total line-item revenue | Audited and recalculated using `Quantity Sold × Unit Price` to fix calculation mismatches and errors |

---

## 🧼 Data Cleaning & Transformation Steps ( Tool used: Power Query Microsoft 365).
1. **Deduplication:** Removed exact duplicate transaction entries.
2. **Text & Whitespace Cleanup:** Applied `TRIM()` and `PROPER()` across text columns (`Product Name`, `Category`, `Region`, `Salesperson`).
3. **Date Standardization:** Parsed inconsistent date formats into uniform `YYYY-MM-DD` dates and flagged/resolved invalid date strings.
4. **Numeric & Currency Parsing:** Cleaned `$` symbols, extra whitespace, and invalid text strings (`invalid_price`, `ERROR`, `"five"`) so mathematical aggregations work accurately.
5. **Formula Auditing:** Recalculated `Total Sales` across all rows to override corrupted values and calculation mismatches.

---

## 🛠️ Excel Skills & Features Used
* **Data Cleaning:** `TRIM`, `PROPER`, `CLEAN`, `IFERROR`, Remove Duplicates, Text-to-Columns.
* **Formulas & Logic:** `SUMIFS`, `COUNTIFS`, `AVERAGEIFS`, `IF`, `XLOOKUP`, Dynamic Arrays (`UNIQUE`, `SORT`, `FILTER`).
* **Analysis & Visualization:** Pivot Tables, Calculated Fields, Interactive Slicers, KPI Cards, and Conditional Formatting.

---

## 🚀 How to Use This Repository
1. Clone this repository to your local machine:
   ```bash
   git clone [https://github.com/LegrandAlpha55/Excel-Projects.git](https://github.com/LegrandAlpha55/Excel-Projects.git)
