# (ProsperLoan Data Exploration)
## by (uthman)


## Dataset
Prosper a is platform that allow individual to post Loan request, and based on some criteria Prosper determine the risk of the request and provide such information for individual investors to access the listing and meet the requirment of the request/Listing.

The Dataset consist of  113,937 loan request/listing with 81 properties/features associated with each listing such as :

- ListingNumber    - The number that uniquely identifies the listing to the public as displayed on the website.
- Term             - The length of the loan expressed in months.
- LoanStatus       - The current status of the loan: Cancelled,  Chargedoff, Completed, Current, Defaulted, PastDue. 
- BorrowerRate     - The Borrower's interest rate for this loan. 
- Occupation       - The Borrower's Occupation.
- ListingCategory  - The category of the listing that the borrower selected when posting their listing: 0 - Not Available, 1 - Debt Consolidation, 2 - Home Improvement, 3 - Business, 4 - Personal Loan, 5 - Student Use, 6 - Auto, 7- Other, 8 - Baby&Adoption, 9 - Boat, 10 - Cosmetic Procedure, 11 - Engagement Ring, 12 - Green Loans, 13 - Household Expenses, 14 - Large Purchases, 15 - Medical/Dental, 16 - Motorcycle, 17 - RV, 18 - Taxes, 19 - Vacation, 20 - Wedding Loans

- Loan Original Amount - The origination amount of the loan


#### Some Data Wrangling performed

- I converted some date variable LoanCreationDate, LoanOriginationDate, DateCreditPulled from  object type to datetime type
- I split the data into two base on date; data before 2010 and data from 2010 onward
- I dropped excessive columns, outlier and replace some columns



## Summary of Findings

I examine the distribution of continous varible such as BorrowerRate, DebtToIncomeRatio. Also Oridinal variable such as CreditGrade, ratingAlpha e.tc. Borrower intrest rate distribution looks more of unimodal by setting bins boundaries between 0 and the max point plus 0.05, while setting the step to 0.025 for both data before 2010 and data from 2010 


Visualizing the heatmap of some discrete variable against continous variable, I found out that there is a little correlation between BorrowRate, and DebtToIncomeRatio. I tried using log transform on other discrete varible hoping that it helps with the correlation but instead the correlation stays the same.

In the exploration of BorrowerRate and LoanStatus, it is also observed that as BorrowerRate tends to increase, the tendency of the loan been Defaulted, Chargedoff or Cancelled tend to increase. Although there are exception where some loan with borrower rate of 45% were completed, also loans where borrower rate less than equal to 15% were cancelled or defaulted.

I further examine the relationship between loans that has high interest rate compared with those with low interest rate
it is observed that  loans with high loan original amount tends to have interest rate in the 10% -15% range. 
Suprisingly, loans with higher intrest rate has loan original amount within the range of 5k - 15k

## Key Insights for Presentation

For the presentation, I focus on Borrower interest rate and the LoanStatus. I start by introducing the Borrower intrest rate in both data, followed by distribution of Loan Status. 

Afterwards, I introduce each of the categorical variables one by one. To start, I use the violin plots of Borrower interest rate and the Loan Status for both data.
