# Online Retail EDA

This is where I worked on the first sheet of the Online Retail II dataset (2009-2010). I practised EDA step by step using Pandas, Matplotlib and Seaborn.

## What I Did

- Checked the rows, columns, data types and basic statistics.
- Checked missing values and their percentages.
- Looked at rows with missing Description and Customer ID.
- Checked exact duplicate rows and removed them from the working copy.
- Changed InvoiceDate to datetime.
- Checked negative quantities and zero-price rows.
- Created a sales DataFrame using rows where Quantity > 0 and Price > 0.
- Created LineValue using Quantity * Price.
- Analysed monthly transaction value.
- Found the top products by quantity and transaction value.
- Found the top countries by transaction value.
- Made line and bar charts to understand the results.

## What I Found

- The original dataset had 525,461 rows and 8 columns.
- Description had 2,928 missing values (0.56%).
- Customer ID had 107,927 missing values (20.54%).
- All rows with a missing Description had Price = 0.
- There were 6,865 exact duplicate rows. After removing them from the working copy, 518,596 rows remained.
- InvoiceDate was converted to datetime, and there were 0 missing or invalid dates after conversion.
- There were 12,302 rows with negative Quantity. Of these, 10,181 had invoice numbers starting with C. The other 2,121 had Price = 0.
- There were 3,681 rows with Price = 0, and 1,560 of those had a positive Quantity.
- November 2010 had the highest monthly transaction value, about £1,464,293.
- December was much lower at about £437,631, but the dataset ends on 9 December 2010, so it is not a full month.
- WHITE HANGING HEART T-LIGHT HOLDER had the highest quantity, with 58,691 units.
- The United Kingdom had the highest transaction value, about £8,812,685.
- Manual was the highest description by transaction value, about £262,963, but I should not treat it as a normal product without checking what it means.

## Notes

For the sales analysis, I used rows where Quantity > 0 and Price > 0, then calculated LineValue = Quantity * Price. These are filtered transaction values, not final net revenue.

I kept the original df unchanged and did the cleaning in a separate DataFrame.

The notebook reads Year_2009-2010.csv using my local Windows file path. If you run it somewhere else, change the path in the first loading cell to where you saved the CSV file.

## Notebook

[Online_Retail_EDA.ipynb](Online_Retail_EDA.ipynb)
