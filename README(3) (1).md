# Power BI Superstore Data Cleaning & Transformation

## Project Overview

This project uses **Power BI Power Query Editor** to clean, transform, and prepare the Superstore dataset for analysis and visualization.

The query shown in the Power Query Editor is named **`superstore_raw`**.

## Dataset

The dataset contains Superstore sales information such as:

- Order Date
- Ship Date
- Discount
- Profit
- Sales
- Customer information
- Product information
- Category and Sub-Category
- Region and other fields

The transformation steps prepare the raw data by cleaning text values, correcting data types, and creating useful date-related columns.

## Power Query Transformation Steps

### 1. Source

The raw Superstore dataset is loaded into Power Query.

### 2. Promoted Headers

The first row of the dataset is promoted as the column header.

### 3. Changed Type with Locale

Data types are assigned to the required columns using the appropriate regional/locale settings. This helps Power Query correctly interpret values such as dates and numbers.

### 4. Trimmed Text

Extra spaces from text columns are removed using the **Trim** operation.

This improves data consistency and prevents problems caused by unwanted spaces.

### 5. Changed Type with Locale 1

The required columns are converted to their correct data types using locale settings.

### 6. Trimmed Text 1

Another set of text columns is cleaned by removing leading and trailing spaces.

### 7. Capitalized Each Word

Text values are formatted so that the first letter of each word is capitalized.

Example:

`john smith` → `John Smith`

This improves the readability and consistency of text data.

### 8. Changed Type with Locale 1

The data types of the transformed columns are checked and corrected again where required.

### 9. Capitalized Each Word 1

Additional text columns are formatted using **Capitalize Each Word** to maintain a consistent naming format.

### 10. Added Custom

A custom column is created to generate a useful date-related value from the existing date columns.

### 11. Added Custom 1

Another custom column is added for date analysis.

For example, an order-date component can be extracted from **Order Date**.

### 12. Added Custom 2

A further custom column is created from the date information.

The transformed dataset shown contains an **`orderDay`** column.

Example Power Query formula:

```powerquery
Date.Day([Order Date])
```

This extracts the day number from the Order Date.

### 13. Added Custom 3

A final custom column named **`shipDay`** is created from the Ship Date.

Formula:

```powerquery
Date.Day([Ship Date])
```

This extracts the day number from the Ship Date.

## Important Calculated Columns

The transformation creates useful date attributes such as:

| Column | Purpose |
|---|---|
| `OrderMonth` | Stores the month from Order Date |
| `orderYear` | Stores the year from Order Date |
| `orderDay` | Stores the day from Order Date |
| `shipDay` | Stores the day from Ship Date |

These columns make it easier to perform date-based analysis and create Power BI visuals.

## Example Transformation Logic

```powerquery
Date.Day([Order Date])
```

Extracts the day from the Order Date.

```powerquery
Date.Day([Ship Date])
```

Extracts the day from the Ship Date.

## Final Result

After completing the transformation steps, the raw Superstore data is cleaner, more consistent, and ready for analysis in Power BI.

The cleaned dataset can be used to create:

- Sales dashboards
- Profit analysis
- Order trend analysis
- Shipping analysis
- Category and product analysis
- Regional performance reports

## Tools Used

- **Power BI Desktop**
- **Power Query Editor**
- **Power Query (M) language**
- **Superstore Dataset**

## Conclusion

The Power Query transformations clean the Superstore dataset and create additional date-related columns. These preprocessing steps improve data quality and make the dataset suitable for building interactive Power BI dashboards and reports.
