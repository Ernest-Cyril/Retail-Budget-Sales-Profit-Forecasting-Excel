# Retail Budget, Sales and Profit Forecasting Model

## Overview

This Excel project analyses sales, profitability and inventory for a fictional Mexican toy-store chain. It compares historical sales against modelled budget targets and estimates future sales, costs and gross profit under adjustable scenarios.

Developed as a professional portfolio project to demonstrate practical data analytics skills to recruiters and hiring managers.

The project demonstrates data preparation, data modelling, financial calculations, budget analysis, scenario planning and dashboard reporting using Microsoft Excel 2019.

## Dataset

**Source:** Maven Analytics — Mexico Toy Sales  
**Dataset link:** [Mexico Toy Sales](https://mavenanalytics.io/data-playground/mexico-toy-sales)

The project uses the following files:

| File | Purpose |
|---|---|
| `sales.csv` | Sales transactions, dates, store IDs, product IDs and units sold |
| `products.csv` | Product names, categories, costs and selling prices |
| `stores.csv` | Store names, cities, locations and opening dates |
| `inventory.csv` | Stock available for each store and product |
| `calendar.csv` | Dates used for time-based analysis |
| `data_dictionary.csv` | Descriptions of the source fields |

The imported sales table contained **829,262 sales transaction-line records**, based on the project’s recorded row count.

## Tools and Techniques

- **Microsoft Excel 2019:** Workbook development, calculations and reporting.
- **Power Query:** CSV imports, data-type corrections, validation, merges and calculated columns.
- **Excel Data Model:** Relationships between sales, products, stores, calendar and inventory tables.
- **PivotTables and PivotCharts:** Supporting analysis and dashboard reporting.
- **Excel formulas:** Lookup, aggregation, conditional and error-handling calculations.
- **Scenario assumptions:** Expected, Best Case and Worst Case planning.
- **Dashboard slicers:** Interactive filtering of historical performance.

## Business Questions

The workbook supports the following questions:

1. Are actual sales meeting the modelled monthly budget?
2. Which product categories, stores and cities contribute the most sales and gross profit?
3. Which months and categories fall below their budget targets?
4. How much money is tied up in inventory?
5. What sales, costs and gross profit are forecast for October–December 2023?
6. How do forecast results change under Expected, Best Case and Worst Case assumptions?

## Data Preparation and Validation

### Import and cleaning

The source files were imported into Power Query and organised into raw queries:

- `Sales_Raw`
- `Products_Raw`
- `Stores_Raw`
- `Inventory_Raw`
- `Calendar_Raw`
- `DataDictionary_Raw`

Clean queries were created from the raw queries. Preparation included reviewing headers, assigning appropriate data types, trimming relevant text fields and converting product costs and prices into numeric values.

Raw queries were retained as connections to support the preparation workflow.

### Quality checks

The following checks were completed during data preparation:

| Check | Recorded result |
|---|---|
| Sales field checks | 0 flagged rows |
| Product field checks | 0 flagged rows |
| Store field checks | 0 flagged rows |
| Inventory field checks | 0 flagged rows |
| Blank calendar dates | 0 |
| Repeated calendar dates | 0 |
| Missing days within the calendar date range | 0 |
| Duplicate Sale IDs | 0 |
| Duplicate Product IDs | 0 |
| Duplicate Store IDs | 0 |
| Duplicate Store ID–Product ID inventory combinations | 0 |
| Sales Product IDs missing from Products | 0 |
| Sales Store IDs missing from Stores | 0 |
| Inventory Product IDs missing from Products | 0 |
| Inventory Store IDs missing from Stores | 0 |
| Sales dates missing from Calendar | 0 |

The data dictionary was also reviewed for blank fields and consistency with the source tables.

These checks found no issues under the validation rules applied. Temporary check queries were removed after their results were recorded.

### Financial calculations

Sales data was merged with product information to calculate:

| Metric | Calculation |
|---|---|
| Sales Revenue | Units × Product Price |
| Total Cost | Units × Product Cost |
| Gross Profit | Sales Revenue − Total Cost |
| Profit Margin | Gross Profit ÷ Sales Revenue |
| Unit Profit | Product Price − Product Cost |

Inventory data was enriched with product costs and prices to calculate:

| Metric | Calculation |
|---|---|
| Inventory Value | Stock on Hand × Product Cost |
| Potential Retail Value | Stock on Hand × Product Price |
| Potential Inventory Profit | Potential Retail Value − Inventory Value |

Calendar fields were added to support monthly analysis, including Year, Month Number, Month Name, Month Start and Year–Month sorting fields.

## Workbook Sheets

| Sheet | Purpose |
|---|---|
| Instructions | Project purpose, usage guidance, definitions and limitations |
| Dashboard | KPI cards, charts and interactive historical analysis |
| Assumptions | Editable inputs and scenario selection |
| Budget | Comparison of actual sales against modelled targets |
| Forecast | Forecast sales, costs and gross profit |
| Analysis | Supporting PivotTables for business, product, store and inventory analysis |
| Clean Data | Prepared data and supporting summaries |
| Raw Data | Source Data Register documenting imported files and queries |

## Key Findings and Validated Results

- The recorded field-quality checks returned no flagged rows.
- The tested sales, product and store IDs contained no duplicates.
- Inventory contained no duplicate Store ID–Product ID combinations.
- The tested relationships contained no unmatched product IDs, store IDs or sales dates.
- The calendar contained no blank dates, repeated dates or missing days within its date range.

The workbook also provides actual-versus-budget comparisons, profitability analysis, inventory valuation and scenario-based forecasts. Business conclusions should be read alongside the selected filters and assumptions.

## Budget and Forecast Methodology

### Modelled budget

The source dataset does not contain an official company budget.

Budget targets were therefore constructed using comparable prior-year sales adjusted by editable category growth targets.

**Budget = Prior-year comparable sales × (1 + Category growth target)**

Budget comparisons show whether actual sales are above or below these modelled targets.

### Forecast

Forecasts use a historical baseline adjusted by the selected growth and cost assumptions.

The model supports:

- **Expected Case:** Baseline planning assumptions.
- **Best Case:** More favourable planning assumptions.
- **Worst Case:** Less favourable planning assumptions.

Forecast sales and gross profit for **October–December 2023** are presented separately from historical results.

## How to Use

1. Open the `01_Excel_Workbook` folder in this repository.
2. Download the Excel workbook.
3. Open it in Microsoft Excel desktop, preferably Excel 2019 or a compatible newer version.
4. Read the **Instructions** sheet.
5. Open **Assumptions** and select a scenario.
6. Review the **Budget** and **Forecast** sheets.
7. Explore historical performance using the **Dashboard** slicers.
8. Use the **Analysis** sheet for supporting detail.

### Refreshing the source data

The workbook’s Power Query connections may reference CSV files stored on the author’s computer.

To refresh using your own copies:

1. Download the required source files.
2. In Excel, open **Data → Get Data → Data Source Settings**.
3. Select each file source and use **Change Source** to point it to the corresponding CSV on your computer.
4. Select **Data → Refresh All**.

Review the saved workbook results before refreshing.

## Limitations

- **Modelled budget:** Budget figures are analytical targets created for this project, rather than an official company budget.
- **Forecast uncertainty:** Forecasts are estimates based on historical data and editable assumptions.
- **Gross profit scope:** Calculated profit excludes operating expenses such as rent, salaries, utilities and taxes. It represents gross profit rather than net profit.
- **Product price and cost assumptions:** Sales calculations use the prices and costs supplied in the product table. Historical price or cost changes cannot be reconstructed without additional data.
- **Inventory snapshot:** Inventory analysis reflects the supplied stock snapshot rather than historical stock movements.
- **Refresh requirements:** Source paths may need updating before Power Query can refresh on another computer.
- **Filter scope:** Historical dashboard slicers and forecast scenario controls serve different parts of the workbook; review each result’s label and assumptions.

## Repository Structure

| Folder or file | Contents |
|---|---|
| `01_Excel_Workbook` | Completed Excel workbook |
| `02_Documentation` | Project documentation |
| `03_Screenshots` | Data preparation, model, analysis, dashboard and scenario screenshots |
| `README.md` | Project overview and usage instructions |

## Author

**Ernest-Cyril Divine Onyeze**  
Data Analyst | Business Intelligence Analyst

- [Portfolio](https://cyrilanalytics.com)
- [GitHub](https://github.com/Ernest-Cyril)
