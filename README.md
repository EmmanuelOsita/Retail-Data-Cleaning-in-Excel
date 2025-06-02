# Retail-Data-Cleaning-in-Excel

**Project Title**: Retail Data Cleaning in Excel

**Objective**: Clean and prepare a messy retail transaction dataset of 1000 records for analysis.

**Tools:** Microsoft Excel (or Google Sheets), Power Query, Excel Formulas, and built-in tools like Remove Duplicates, Text to Columns, etc.

**Steps Taken:**

* Removed duplicates based on customer details
* Standardized inconsistent name, product, and payment casing
* Normalized date formats to yyyy-mm-dd
* Removed currency symbols and ensured numeric values
* Flagged missing email addresses


**STEP 1 : Open & Inspect the Dataset**
I opened the dataset and had to skim through the file to observe:


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
Column	Formula (Example)
Name	=PROPER(A2)
Email	=LOWER(B2)
Product	=PROPER(D2)
Payment Method	=PROPER(F2)


**STEP 4: Unify Date Formats**
I realised that  the dates were inputed with different formats, hence to unify the dates I used in a new column:
=TEXT(C2, "yyyy-mm-dd")

![image](https://github.com/user-attachments/assets/2703954b-c301-47c5-812a-26b79a559d1b)

 *This action Normalized all purchase dates into the standard yyyy-mm-dd format using the TEXT() function*.

**STEP 5: Clean Currency from Amounts**

On checking the data, I realized that some had a dollar ($) sign while others didn’t, so the best option is to remove $ in other to unify the currency from amounts:
To do that I used

=VALUE(SUBSTITUTE(E2, "$", ""))

