# Online Retail: Customer Value & Retention Analysis

## Business Problem
A UK online retailer wants to know which customers drive its revenue, when sales peak, which markets matter, and how to retain its most valuable customers. This project turns 12 months of transaction data into practical recommendations for sales, retention and stock planning.

## Data
- Source: UCI Online Retail dataset (UK-based online retailer, 1 Dec 2010 to 9 Dec 2011), not included in this repo due to size
- 541,909 transaction rows across 8 variables
- Revenue is defined as Quantity x UnitPrice. No cost data is available, so revenue is not profit.

## Data Cleaning
- Removed 5,268 exact duplicate rows
- Found that 24.9% of rows had no customer ID: kept for sales, product and country totals, excluded from customer analysis
- Separated non-product codes (postage, fees, manual entries) and two bulk orders that were cancelled within minutes, which would otherwise have appeared as top products and top customers
- Split the data into genuine sales (522,535 rows), cancellations and adjustments, with validation checks that every row is accounted for

## Approach
- Framework: CRISP-DM
- Tools: R (tidyverse, ggplot2, lubridate), Power BI
- Analysis: monthly trends, product and country performance, customer behaviour, cancellations
- Segmentation: RFM (Recency, Frequency, Monetary) using quintile scores, applied to 4,333 identified customers

## Key Findings
- **Sales:** GBP 10.0M revenue from 19,771 invoices and 4,333 customers
- **Seasonality:** September to November generate 35.8% of revenue, peaking in November 2011 at GBP 1.45M
- **Customer concentration:** High Value customers are 21.7% of customers but generate 66.5% of revenue; the top 20% of customers generate 73.9%
- **Retention risk:** 653 At Risk customers worth GBP 0.8M; 34.7% of customers bought only once
- **Markets:** the UK generates 84.8% of revenue, and the next five markets together add only 10.8%
- **Cancellations:** 14.7% of invoices are cancellations, but they remove only 2.3% of sales value
- **Products:** 841 of 3,906 products (21.5%) generate 80% of revenue

## Recommendations
- Retain High Value customers with personalised offers and loyalty rewards
- Run a win-back campaign for the 653 At Risk customers
- Send follow-up offers to first-time buyers to convert them into repeat customers
- Plan stock, staffing and marketing around the autumn peak
- Test growth in the largest export markets (Netherlands, EIRE, Germany, France, Australia)
- Capture customer ID at every checkout so more sales can be linked to customers

## Limitations
- Only one year of data, so seasonality cannot be confirmed as an annual cycle, and December 2011 is incomplete
- Revenue is not profit, so the highest-revenue customers may not be the most profitable
- RFM segment rules are exploratory judgements, not externally validated labels

## How to Reproduce
1. Download the dataset from the UCI Machine Learning Repository (Online Retail)
2. Save it as OnlineRetail.csv in the same folder as the R Markdown file
3. Open the R Markdown file in RStudio, install the required packages and knit

## Note on AI Assistance
I used an AI assistant to review the cleaning code, suggest segment comparisons, and help structure recommendations. I wrote the analysis code, chose the segment rules and interpreted the results.

## Author
Harshita Nese | MSc Business Analytics, University of Bath
