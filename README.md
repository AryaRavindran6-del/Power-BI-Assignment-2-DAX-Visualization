# Power-BI-Assignment-2-DAX-Visualization
Power BI Assignment 2 for the AI-Driven Data Analytics program, covering DAX calculations, data visualization, and data quality analysis.

## Project Overview
This project was completed as part of the **Program in AI-Driven Data Analytics** offered by Entri App. The objective was to analyze multiple datasets using Microsoft Power BI, create meaningful visualizations, implement DAX calculations, and summarize key findings through KPI cards.

## Tools & Technologies
- **Microsoft Power BI Desktop** – Data modeling and visualization
- **Power Query Editor** – Data preparation and type conversion
- **DAX (Data Analysis Expressions)** – Calculated columns and measures

## Workflow
1. **Data Import:** Imported the Amazingcart, Customer Data, and Employee Layoffs datasets into Power BI.
2. **Data Preparation:** Checked column headers, corrected data types, and handled numeric and currency values while preserving missing data.
3. **Data Visualization:** Created a clustered column chart for country-wise orders, a line chart for daily order trends, and a pie chart for layoffs by location.
4. **Calculated Column:** Calculated total price using quantity and price per unit.
5. **DAX Measures:** Created measures for total layoffs, row count, valid records, missing values, minimum layoffs, and maximum layoffs.
6. **Validation:** Compared calculated results with the source data and presented key metrics using card visuals.

## DAX Formulas Used

### 1. Calculated Total Price
```dax
Calculated Total Price =
    'Customer Data'[Quantity] *
    'Customer Data'[Price Per Unit]
```

### 2. Total Layoffs
```dax
Total Layoffs =
    SUM('Employee_Layoffs'[Total_Laid_Off])
```

### 3. Total Rows
```dax
Total Rows =
    COUNTROWS('Employee_Layoffs')
```

### 4. Valid Records
```dax
Valid Records =
    COUNTAX(
        'Employee_Layoffs',
        'Employee_Layoffs'[Company Name]
    )
```

### 5. Total Missing Values
```dax
Total Missing Values =
COUNTBLANK(Employee_Layoffs[Company Name]) +
COUNTBLANK(Employee_Layoffs[Location]) +
COUNTBLANK(Employee_Layoffs[Industry]) +
COUNTBLANK(Employee_Layoffs[Total_Laid_Off]) +
COUNTBLANK(Employee_Layoffs[Date]) +
COUNTBLANK(Employee_Layoffs[Year]) +
COUNTBLANK(Employee_Layoffs[Stage]) +
COUNTBLANK(Employee_Layoffs[Country]) +
COUNTBLANK(Employee_Layoffs[Funds_Raised])+
COUNTBLANK(Employee_Layoffs[Percentage_Laid_Off])
```

### 6. Minimum Layoffs
```dax
Minimum Layoffs =
    MIN('Employee_Layoffs'[Total_Laid_Off])
```

### 7. Maximum Layoffs
```dax
Maximum Layoffs =
    MAX('Employee_Layoffs'[Total_Laid_Off])
```

## Key Findings

| Analysis | Result |
|---|---|
| Highest order count by country | France – 991 orders |
| Customer order records | 699 |
| Distinct order dates | 473 |
| Highest recorded layoffs by location | SF Bay Area – 122,628 |
| Total recorded layoffs | 367,072 |
| Employee layoffs dataset rows | 2,273 |
| Valid records (nonblank company names) | 2,273 |
| Missing cells across 10 columns | 2,933 |
| Minimum recorded layoffs | 3 |
| Maximum recorded layoffs | 12,000 |

## Key Learnings
- Preparing data and assigning appropriate data types before analysis.
- Creating calculated columns and measures using DAX.
- Selecting suitable visualizations to communicate insights.
- Evaluating missing values and validating analytical results.
- Presenting key performance indicators through Power BI card visuals.

## Project Files
- `Power_BI_Second.pbix` – Power BI report.
- `Power_BI_Assignment_2_Documentation.docx` – Detailed assignment documentation, formulas, and step-by-step workflow.

## Conclusion
This assignment demonstrates the application of Power Query, DAX, and Power BI visualizations to transform raw datasets into structured analytical insights. It strengthened practical skills in data preparation, calculations, data quality assessment, and visual reporting.

**Course:** Program in AI-Driven Data Analytics  
