# Superstore Sales Data Analysis & Transformation using Power BI

## 📌 Project Overview

This project demonstrates the process of cleaning, transforming, and preparing the Superstore Sales dataset using Microsoft Power BI and Power Query.

The raw sales data was cleaned, formatted, and transformed into a structured dataset suitable for data analysis and visualization.

The project focuses mainly on data preprocessing, Power Query transformations, date-based calculations, and data preparation for further analysis.

## 🎯 Project Objectives

The main objectives of this project are:

- Import the Superstore Sales dataset into Power BI.
- Clean and organize the raw data.
- Correct inappropriate data types.
- Standardize categorical text values.
- Apply appropriate date and locale settings.
- Create calculated columns using Power Query.
- Perform date-based transformations.
- Remove unnecessary columns.
- Prepare the final dataset for Power BI reporting and visualization.

## 🛠️ Technologies & Tools

| Tool | Purpose |
|---|---|
| Microsoft Power BI Desktop | Data analysis and visualization |
| Power Query Editor | Data cleaning and transformation |
| Power Query M | Custom data transformations |
| CSV | Source data format |

## 📁 Dataset

The project uses the Superstore Sales CSV dataset, which contains information related to:

- Orders
- Customers
- Shipping
- Products
- Categories
- Sales
- Discounts
- Profit

The dataset contains both categorical and numerical fields that require preprocessing before analysis.

## 🔄 Data Transformation Process

### 1. Importing the CSV Dataset

The raw CSV file was imported into Power BI using the Text/CSV connector.

**Steps:**

```text
Power BI Desktop
       ↓
     Home
       ↓
    Get Data
       ↓
   Text/CSV
       ↓
Select Superstore Dataset
       ↓
  Transform Data
```

The dataset was opened in Power Query Editor for preprocessing and transformation.

### 2. Promoting Column Headers

The first row of the dataset was converted into column headers.

This makes the dataset easier to understand and allows each field to be referenced correctly during transformations.

**Power Query Operation:**

`Transform → Use First Row as Headers`

### 3. Correcting Data Types

Appropriate data types were assigned to the columns based on the information they contain.

| Column | Data Type |
|---|---|
| Order Date | Date |
| Ship Date | Date |
| Segment | Text |
| Category | Text |
| Sub-Category | Text |
| Sales | Decimal Number |
| Quantity | Whole Number |
| Discount | Decimal Number |
| Profit | Decimal Number |

Correct data types are important for accurate calculations, data analysis, and visualization.

### 4. Applying Date Locale

The date columns were converted using the appropriate locale settings to ensure that dates were interpreted correctly.

**Example:**

`Order Date → Change Type → Using Locale`

The appropriate regional date format was selected to prevent incorrect date interpretation.

### 5. Standardizing Categorical Data

The categorical columns were cleaned and standardized to maintain consistency throughout the dataset.

The following fields were processed:

- Segment
- Category
- Sub-Category

**Formatting Operations:**

- Trim
- Clean
- Capitalize Each Word

**Example:**

| Original Value | Standardized Value |
|---|---|
| consumer | Consumer |
| CONSUMER | Consumer |
| furniture | Furniture |
| office supplies | Office Supplies |
| technology | Technology |

This ensures that the same category is not treated as multiple different values because of inconsistent capitalization or unnecessary spaces.

### 6. Date-Based Transformation

Additional information was extracted from the date columns to support time-based analysis.

Examples include:

- Year
- Month
- Quarter
- Week of Year

These fields can be used to analyze sales trends across different time periods.

### 7. Creating Week of Year

A calculated column was created to identify the week number associated with each order date.

**Power Query M Expression:**

```powerquery
Date.WeekOfYear([Order Date])
```

This produces week numbers such as:

```text
1
2
3
4
...
52
```

**Applications:**

The Week of Year field can be used for:

- Weekly sales analysis
- Identifying sales trends
- Comparing weekly performance
- Creating time-based visualizations

### 8. Creating Custom Columns

Power Query's Custom Column feature was used to create additional calculated fields.

For example, shipping duration can be calculated using:

**Power Query M Expression:**

```powerquery
Duration.Days([Ship Date] - [Order Date])
```

This creates a new column named **Shipping Days**.

The calculated value represents the number of days between the order date and the shipping date.

### 9. Duplicating Columns

Some columns were duplicated before applying transformations.

This approach helps preserve the original data while allowing a modified version to be created.

**Example:**

```text
Order Date
     ↓
Duplicate Column
     ↓
Modified Date Column
```

The duplicated column can then be renamed and transformed according to the analysis requirements.

### 10. Renaming Columns

Newly created and duplicated columns were renamed with meaningful names.

**Examples:**

- Order Date.Year → Order Year
- Order Date.Month → Order Month
- WeekOfYear → Week of Year

Meaningful column names make the dataset easier to understand and use during analysis.

### 11. Removing Unnecessary Columns

Columns that were not required for the final analysis were removed.

This helps to:

- Reduce unnecessary data
- Improve dataset readability
- Simplify the Power BI data model
- Focus on relevant information

The final dataset focuses on the required fields for analysis and visualization.

## 🔗 Transformation Workflow

The complete transformation process can be summarized as follows:

```text
          Raw CSV Dataset
                 ↓
        Import into Power BI
                 ↓
        Power Query Editor
                 ↓
         Promote Headers
                 ↓
        Correct Data Types
                 ↓
        Apply Date Locale
                 ↓
      Clean & Standardize Text
                 ↓
      Create Calculated Columns
                 ↓
         Duplicate Columns
                 ↓
          Rename Columns
                 ↓
        Calculate Week Number
                 ↓
      Remove Unnecessary Fields
                 ↓
          Clean Dataset
                 ↓
          Close & Apply
                 ↓
      Power BI Data Analysis
```

## 📊 Final Dataset

After completing the transformations, the dataset is structured and ready for further analysis.

Important fields include:

| Field | Description |
|---|---|
| Order Date | Date when the order was placed |
| Ship Date | Date when the order was shipped |
| Segment | Customer segment |
| Category | Product category |
| Sub-Category | Product sub-category |
| Sales | Sales amount |
| Quantity | Number of products |
| Discount | Discount applied |
| Profit | Profit generated |
| Week of Year | Week number derived from Order Date |

## 📈 Possible Power BI Visualizations

The transformed dataset can be used to create several useful visualizations.

### Sales Analysis

- Total Sales
- Sales by Category
- Sales by Sub-Category
- Sales by Region

### Profit Analysis

- Total Profit
- Profit by Category
- Profit by Segment

### Time-Based Analysis

- Monthly Sales Trend
- Weekly Sales Trend
- Quarterly Sales Performance

### Customer Analysis

- Sales by Segment
- Orders by Customer
- Customer-wise Sales

## 🎓 Learning Outcomes

This project helped develop practical knowledge of:

- Importing CSV data into Power BI
- Working with Power Query Editor
- Promoting column headers
- Changing data types
- Applying date locale settings
- Cleaning and standardizing text data
- Creating custom columns
- Writing Power Query M expressions
- Extracting date information
- Calculating week numbers
- Duplicating and renaming columns
- Removing unnecessary data
- Preparing datasets for visualization

## ✅ Conclusion

The Superstore Sales dataset was successfully transformed from raw CSV data into a clean and structured dataset using Microsoft Power BI and Power Query.

The transformation process improved data quality, consistency, and usability.

The final dataset is now ready to be used for building interactive Power BI dashboards and performing meaningful sales, profit, customer, and time-based analysis.
