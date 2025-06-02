# Retail-Data-Cleaning-in-Excel

**Project Title**: Retail Data Cleaning in Excel

**Objective**: Clean and prepare a messy retail transaction dataset of 1,000 records for analysis.

**Tools:** Microsoft Excel (or Google Sheets), Power Query, Excel Formulas, and built-in tools like Remove Duplicates, Text to Columns, etc.

**Steps Taken:**

* Removed duplicates based on customer details
* Standardized inconsistent name, product, and payment casing
* Normalized date formats to yyyy-mm-dd
* Removed currency symbols and ensured numeric values
* Flagged missing email addresses


**STEP 1 : Open & Inspect the Dataset**

I opened the dataset and had to skim through the file to observe:

![image](https://github.com/user-attachments/assets/54c558c6-fb3d-4253-9468-86de4ecd2068)

* Duplicates
* Irregular date formats
* Missing emails
* Amounts with currency symbols
* Inconsistent product names and payment methods

**STEP 2: Remove Duplicates**

I discovered that the data had duplicates so I had to Go to:

Data > Remove Duplicates

Select all or key columns (Customer Name, Email, Purchase Date)

Click OK

![image](https://github.com/user-attachments/assets/b59d1b53-8772-433f-a587-bd2a02a5da0a)


*This action Removed duplicates based on customer name, email, and purchase date to avoid counting the same purchase more than once*

**STEP 3: Standardize Text Formatting**

I discovered that majority of the data especially those in the Name, email, product and payment method column weren’t standardized, a mixture of BLOCK letters and small ones. 

To solve the problem I used PROPER() and LOWER() to fix inconsistent casing in names, emails, products, and payment methods.”

In new columns, I used:
* Column	Formula (Example)
* Name	=PROPER(A2)
* Email	=LOWER(B2)
* Product	=PROPER(D2)
* Payment Method	=PROPER(F2)


**STEP 4: Unify Date Formats**

I realised that  the dates were inputed with different formats, hence to unify the dates I used in a new column:
=TEXT(C2, "yyyy-mm-dd")

![image](https://github.com/user-attachments/assets/2703954b-c301-47c5-812a-26b79a559d1b)

 *This action Normalized all purchase dates into the standard yyyy-mm-dd format using the TEXT() function*.

**STEP 5: Clean Currency from Amounts**

On checking the data, I realized that some had a dollar ($) sign while others didn’t, so the best option is to remove $ in other to unify the currency from amounts:

To do that I used =VALUE(SUBSTITUTE(E2, "$", ""))

![image](https://github.com/user-attachments/assets/3772544a-4755-427c-9157-d9eb1afcb5ec)

*Applying the function “Removed $ symbols from Amount column and converted values to numeric for calculations*


**STEP 6: Handle Missing Data**

Using the Filter and Search tool, I noticed that some of the customers had no email input in the email column. So I had to use the formula to flag the blank data
=IF(ISBLANK(B2), "Missing", B2) for emails

![image](https://github.com/user-attachments/assets/17f460ce-483a-4280-a782-c52b33bb954f)


*Applying this “Flagged missing emails with ‘Missing’ label for visibility* 

**STEP 7: Final Touches**
Rename headers clearly (e.g., “Customer Name” → “Full Name”)

Saved file as: clean_retail_cleaned_1,000.xlsx

## Key Improvements Delivered

![image](https://github.com/user-attachments/assets/8d59a312-e4ac-4514-9427-2df3a86a929e)

* Eliminated 11 duplicates transactions ($250 in value)
* Corrected 150 mis-formated dates enabling time-series analysis
* Reduced manual cleaning time by 90% (from 5hours to 30minutes)
* Automated future imports with Power Query templates


**Result: Produced a clean, analysis-ready dataset suitable for business intelligence, sales tracking, and reporting.**
