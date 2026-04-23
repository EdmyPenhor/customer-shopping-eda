# Customer Shopping Behavior Analysis

This project is an end-to-end exploratory data analysis (EDA) of a customer shopping dataset.  
The main goal was not just to produce charts, but to take a messy dataset, clean it carefully, question its inconsistencies, and turn it into something useful for analysis and storytelling.

## Project highlights

- explored customer demographics and shopping patterns
- treated missing values using business-aware rules
- reviewed category inconsistencies between products and product classes
- standardized location and purchase-frequency labels
- checked semantic issues such as clothing sizes appearing in non-clothing categories
- built portfolio-ready visualizations and business insights

## Dataset

The dataset includes information such as:

- customer ID
- age
- gender
- item purchased
- product category
- purchase amount
- location
- size
- color
- season
- review rating
- subscription status
- shipping type
- discount applied
- previous purchases
- payment method
- frequency of purchases

## Questions explored

This analysis was built around a few practical questions:

- Which product categories generate the highest volume of purchases?
- Which categories bring the highest spending?
- Do subscribers spend more than non-subscribers?
- Does purchase frequency relate to basket value?
- How are reviews distributed across categories?
- Are numerical variables strongly related, or do categorical features explain more of the behavior?

## Data quality issues found

Before the analysis, the dataset showed several quality problems:

- missing values in key monetary fields
- inconsistent category assignments for some purchased items
- location values mixing **states** and **cities**
- duplicated meanings in `Frequency of Purchases`  
  - `Quarterly` and `Every 3 Months`
  - `Bi-Weekly` and `Fortnightly`
- clothing-style sizes (`S`, `M`, `L`, `XL`) appearing in categories where they do not apply
- exact repeated rows that needed careful interpretation because the dataset has no transaction timestamp

## Cleaning and preparation workflow

The notebook follows a structured cleaning process:

1. **Initial inspection**  
   Checked shape, data types, unique values, descriptive statistics, and missing values.

2. **Working copy creation**  
   Created a separate copy of the dataset to preserve the raw file.

3. **Missing value treatment**  
   - `Purchase Amount (USD)` was imputed with a hierarchical median-by-group strategy.
   - `Previous Purchases` was handled in a similar way because it is also monetary.
   - `Review Rating` was treated more carefully, since a missing review may mean the customer simply did not leave feedback.

4. **Semantic corrections**  
   - `Size` was recoded to `Not Applicable` where it did not make sense.
   - `Category` was reviewed against `Item Purchased` and aligned with business logic.
   - `Location` was standardized to the state level.
   - `Frequency of Purchases` labels were harmonized.

5. **Final conformity check**  
   Reviewed the dataset again to confirm that the main issues had been addressed before the final EDA.

## Main insights

Here are some of the strongest findings from the analysis:

- **Clothing** accounts for the largest share of records, but **Electronics** leads by a wide margin in average purchase amount.
- Customers with an **active subscription** spend noticeably more than non-subscribers.
- Customers who buy **weekly** or **monthly** tend to generate higher average purchase values.
- **Outerwear** has the highest average review score, while **Electronics** has the lowest.
- The main numerical variables show **very weak linear correlations**, suggesting that customer spending is driven more by categorical factors than by simple numerical relationships.

## Tools used

- Python
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook

## Repository structure

```text
customer-shopping-eda/
│
├── data/
│   └── customer_shopping_behavior.csv
│
├── notebooks/
│   └── customer_shopping_behavior_analysis_en_humanized.ipynb
│
├── images/
│   └── (exported charts, if added)
│
└── README.md
```

## Notebook

The main notebook for this project is:

`customer_shopping_behavior_analysis_en_humanized.ipynb`

It includes:

- inspection of the raw dataset
- cleaning and standardization steps
- exploratory visualizations
- written interpretations after each analysis block
- a final summary report

## Why this project matters

This project shows more than plotting skills. It reflects the kind of work that often happens before any model is built: checking assumptions, questioning labels, cleaning categories, treating missing values carefully, and making sure the story told by the data is actually credible.

## Next steps

This project can be extended in several directions:

- customer segmentation
- purchase amount prediction
- dashboard development in Power BI or Tableau
- deeper analysis of loyalty and customer retention

## Author

**Edmilson Penhor**  
Mathematician and Statistician  
Data analysis, survey data, and applied research
