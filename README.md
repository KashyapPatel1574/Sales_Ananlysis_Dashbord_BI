# Sales Analytics | Power BI

An interactive Power BI dashboard project for exploring sales performance, product performance, customer and geographic patterns, and shipment operations.

The report is organized into five pages: **Home**, **Sales Overview**, **Product Analysis**, **Customer & Geography**, and **Shipment Operations Analytics**.

## Table of Contents

- [Project Overview](#project-overview)
- [Business Objectives](#business-objectives)
- [Tools and Technologies](#tools-and-technologies)
- [Repository Structure](#repository-structure)
- [Dataset and Source](#dataset-and-source)
- [Dashboard Preview](#dashboard-preview)
- [Dashboard Pages](#dashboard-pages)
- [KPIs and Analysis](#kpis-and-analysis)
- [Interactive Filters](#interactive-filters)
- [Validation Notes](#validation-notes)
- [How to Open the Report](#how-to-open-the-report)
- [Limitations and Responsible Use](#limitations-and-responsible-use)

## Project Overview

This project presents sales and shipment data through an interactive Power BI report. It is designed to help users explore sales results, product/category performance, customer segments, geographic distribution, and shipping outcomes from different perspectives.

The report is descriptive: it summarizes patterns in the dataset. Observed differences do not, by themselves, establish the cause of a business outcome.

## Business Objectives

- Monitor overall sales and order performance.
- Compare sales across product categories and subcategories.
- Identify high-performing products based on sales.
- Explore customer distribution and sales across regions, states, and cities.
- Review payment-mode distribution.
- Examine shipment status, shipping duration, delayed orders, and on-time delivery.
- Provide interactive filtering to explore the data from multiple business perspectives.

## Tools and Technologies

| Tool / technology | Purpose |
|---|---|
| Microsoft Power BI Desktop | Report authoring, data modeling, measures, and visualizations |
| CSV / tabular source data | Source data used by the report, subject to the actual file format in the repository |
| Power Query and DAX | Data preparation and calculations where implemented in the Power BI model |

The exact Power BI version and division of work between Power Query and DAX are not specified here because they have not been verified from the final `.pbix`.

## Repository Structure

```text
sales_analysis/
├── 01_Raw_Data/
│   └── sales_dataset_with_shipment_operations.csv 
├── 02_PowerBI_Report/
│   └── sales_analysis.pbix
├── 03_Documentation/
│   └── Sales_Shipment_Operations_Business_Documentation.docx
├── 04_Data_Dictionary/
│   └── Sales_Shipment_Operations_Data_Dictionary.xlsx
├── 05_Assets/
│   ├── background/
│   ├── dashboard_image/
│   │   ├── Page-1 Home.png
│   │   ├── Page-2 Sales Overview.png
│   │   ├── Page-3 Product Analysis.png
│   │   ├── Page-4 Customer & Geography.png
│   │   └── Page-5 Shipment Operations Analytics.png
│   └── icon/
└── README.md
```

The three document/data filenames shown with ellipses are truncated in the supplied file-explorer screenshot. Replace those descriptions with the full filenames if you want the README tree to show every filename exactly. The dashboard screenshot names above are based on the uploaded filenames.

## Dataset and Source

The raw-data folder contains the sales dataset used by the project. The project context indicates that the data was obtained from client and prepared for analysis.

The dashboard screenshots display fields and categories including order dates, region, category, subcategory, payment mode, state, city, product, gender, order ID, ship date, shipping days, and shipment status. Confirm these against the actual source file and model before treating this list as the complete data dictionary.

## Dashboard Preview

The images below use the screenshot filenames supplied for this project. They are stored in `05_Assets/dashboard_image/`.

### 1. Home

![Sales Analytics Home](05_Assets/dashboard_image/Page-1%20Home.png)

### 2. Sales Overview

![Sales Overview]("K:\Power BI\Power BI Project\Sales_Analysis\Asset\Sales overview.png")

### 3. Product Analysis

![Product Analysis]("K:\Power BI\Power BI Project\Sales_Analysis\Asset\Product analysis.png")

### 4. Customer & Geography

![Customer and Geography](05_Assets/dashboard_image/Page-4%20Customer%20%26%20Geography.png)

### 5. Shipment Operations Analytics

![Shipment Operations Analytics]("K:\Power BI\Power BI Project\Sales_Analysis\Asset\Shipment operation.png")

GitHub image links are case-sensitive. Keep the image filenames and relative paths in this section synchronized with the committed files.

## Dashboard Pages

### 1. Home

Provides a landing page for the report, headline KPIs, and navigation to the analytical pages. The screenshot shows headline metrics for orders, customers, sales, quantity, average order value, and average shipping days.

### 2. Sales Overview

Focuses on sales performance. The screenshot includes date and geographic/product/payment filters, KPI cards, a sales trend, sales by category and payment mode, sales by region, top products by sales, and sales by subcategory.

### 3. Product Analysis

Focuses on product and category performance. The screenshot includes sales by category and subcategory, top products by sales, a sales-versus-quantity comparison for top products, and a product performance table.

### 4. Customer & Geography

Explores customer and geographic patterns. The screenshot includes customer/order/sales KPIs, sales by gender, top customers by sales, sales by region, top states, top cities, and a state-level sales distribution map.

### 5. Shipment Operations Analytics

Focuses on shipment status and delivery performance. The screenshot includes orders shipped, average shipping days, delayed orders, on-time delivery percentage, pending shipments, shipping-status distribution, average shipping days by region, monthly on-time versus delayed orders, shipping-day distribution, city-level shipping duration, and recent shipments.

These descriptions are based on the supplied dashboard screenshots. The final `.pbix` remains the source of truth for exact visual behavior, calculations, and interactions.

## KPIs and Analysis

The report screenshots show the following KPI types:

| Area | KPI types visible in the screenshots |
|---|---|
| Sales | Total sales, total orders, average order value, total quantity |
| Product | Distinct products, categories, subcategories, product-level sales and quantity |
| Customer & geography | Total customers, sales per customer, orders per customer, repeat customers, sales by geographic area |
| Shipment operations | Orders shipped, average shipping days, delayed orders, on-time delivery percentage, orders pending shipment |

The screenshots contain different values for some similarly named KPIs across pages. For example, the Home and Sales Overview screenshots display different customer and quantity totals, and average order value is also displayed differently. These may reflect different measure definitions, filters, or a mismatch in the mockups/report; **the correct values should be reconciled in the final `.pbix` before publishing numerical claims in this README**. For that reason, this README describes KPI types rather than asserting one set of totals as validated.

### Calculation definitions to document

Confirm the exact measures in the model. Common definitions may include:

- **Total Sales:** sum of the sales amount field.
- **Total Orders:** distinct count of order IDs, if each order can appear on multiple rows.
- **Total Customers:** distinct count of customer IDs or the validated customer key.
- **Average Order Value:** total sales divided by the intended order count; document whether it is calculated over all orders or a filtered subset.
- **Average Shipping Days:** average of the shipping-duration field for the intended set of shipped orders.
- **Delayed Orders:** count of orders classified as delayed according to the report's actual status/business rule.
- **On-Time Delivery %:** on-time orders divided by the intended delivered/shipped order population.

These are definitions to validate, not confirmation of the exact DAX currently implemented.

## Interactive Filters

The supplied screenshots show filters including some combination of:

- Date / order date
- Region
- State
- City
- Category
- Subcategory
- Product
- Payment mode
- Gender

The exact filters differ by page. Use the final report to confirm which filters are present and whether they cross-filter other visuals as intended.

## Validation Notes

Before treating the dashboard as final, verify:

1. **Source and license:** Confirm the exact Kaggle dataset title, URL, and license/usage terms.
2. **File paths:** Ensure the `.pbix` points to the source file stored in `01_Raw_Data/`.
3. **Order counting:** Check whether one order can occupy multiple rows and use a distinct order count where appropriate.
4. **Customer counting:** Verify the customer key and the definition of repeat customers.
5. **KPI reconciliation:** Explain and resolve differences in total customers, total quantity, average order value, and any other measures shown on multiple pages.
6. **Shipment logic:** Confirm how delayed, on-time, pending, and shipped orders are defined and counted.
7. **Date logic:** Verify the date column used in each trend and the treatment of order date versus ship date.
8. **Filters and interactions:** Test slicers, cross-filtering, navigation, and reset/clear-filter controls.
9. **Screenshots:** Confirm that all five screenshots reflect the latest saved report.
10. **Public release:** Ensure the raw dataset and screenshots can be shared publicly and do not expose private customer information.

## How to Open the Report

1. Open Microsoft Power BI Desktop.
2. Open `02_PowerBI_Report/sales_analysis.pbix`.
3. If the source cannot be found, update the source path in Power Query to the file inside `01_Raw_Data/`.
4. Refresh the model and resolve any source or transformation errors.
5. Reconcile the key measures against the source data.
6. Test all five pages, slicers, navigation, and interactions.
7. Save the report after confirming that it refreshes correctly.

The exact source-path adjustment depends on how the `.pbix` was configured on the original machine.

## Limitations and Responsible Use

- Results describe the records in the supplied dataset and should not automatically be interpreted as live business performance.
- Sales trends depend on the date field, granularity, filters, and definitions used in the report.
- Differences between categories are descriptive and do not prove causation.
- Shipment measures depend on the definitions of shipped, delayed, pending, and on-time orders.
- Confirm the original dataset's license before publishing the raw file in a public repository.
- Review customer names, order identifiers, and any other potentially identifying details before publishing screenshots or data.

---

**Project:** Sales Analytics  
**Primary tool:** Microsoft Power BI  
**Report file:** `02_PowerBI_Report/sales_analysis.pbix`
