# Data Cleaning Assignment — README

## Overview
This workbook contains a raw e-commerce product dataset and a documented, step-by-step data cleaning exercise performed on it. It covers six core data-cleaning skills: handling missing values, correcting inconsistent data, removing duplicates, splitting/merging columns, number formatting, and conditional formatting.

## File Structure

| Sheet | Contents |
|---|---|
| **Dataset** | Raw product data — Product ID, Manufacturing Date, Country Code, Product Name, Brand Name, Product Brand, Price ($), Quantity, Category |
| **Sheet1** | Written answers, findings, and before/after examples for each cleaning task |

## Dataset Columns

| Column | Description |
|---|---|
| Product ID | Encodes manufacturing date + country code (e.g. `28-JAN-US`) |
| Manufacturing Date | Full date the product was manufactured |
| Country Code | 2-letter country code (US, UK, IN, AU, DE, CA, ES, CN, IT, RU, BR, FR) |
| Product Name | Name of the product |
| Brand Name | Manufacturer/brand |
| Product Brand | Merged field: Brand Name + Product Name |
| Price ($) | Unit price |
| Quantity | Units in stock/sold |
| Category | Product category (Electronics, Fashion, Kitchen, Accessories, Outdoor) |

## Cleaning Tasks Summary

### 1. Handling Missing Values
- **Missing prices:** 3 records had missing prices (Headphones, Camping Tent, Sunglasses) — filled using the average value of the Price column.
- **Missing categories:** 4 records had missing categories — imputed based on product type:
  - Backpack → Accessories
  - Sneakers (Adidas) → Fashion
  - Coffee Maker (Nespresso) → Kitchen
  - Fitness Tracker (Xiaomi) → Electronics

### 2. Correcting Inconsistent Data
- **Product Name capitalization** fixed via Find & Replace (Power Query):
  - laptop → Laptop
  - smartphone → Smartphone
  - headphones → Headphones
- **Category typos** fixed:
  - Electroni → Electronics

### 3. Removing Duplicates
Duplicate rows identified and removed:
- 21-AUG-CA — Laptop Bag
- 16-APR-ES — Headphones
- 17-JUN-IN — Laptop

### 4. Splitting and Merging Data
- **Split:** Product ID → separate Manufacturing Date and Country Code columns (e.g. `28-JAN-US` → `2026-01-28`, `US`).
- **Merged:** Brand Name + Product Name → new Product Brand column (e.g. Dell + Laptop → "Dell Laptop").

### 5. Number Formatting
- Price column converted to numeric/decimal and formatted as Currency: `1000 → $1,000.00`
- Manufacturing Date reformatted to `DD-MM-YYYY`: `28-JAN-2026 → 28-01-2026`

### 6. Conditional Formatting
- **Data Bars** applied to the Price column to visualize magnitude.
- **Highlight rule** applied to the Category column: cells equal to "Electronics" are highlighted.

## Tools Used
- Microsoft Excel (Find & Replace, Conditional Formatting, Number Formatting)
- Power Query (text standardization)

## Notes
- All transformations and rationale are documented inline in **Sheet1**, alongside before/after examples for traceability.
