# medical-appointment-data-cleaning
Data cleaning of Kaggle's Medical Appointment No Shows dataset using Excel (handling missing values, duplicates, text standardization, dates, and headers).

Step 1: Handle Missing Values
Check if a column has missing values:
=COUNTBLANK(A2:A110528)
Or  Go to Home Tabe > Find & Select > Go to Special > Blank 

Step 2: Remove Duplicates
Go to Data → Remove Duplicates
OR with a formula to mark duplicates:   =IF(COUNTIF(A:A, A2)>1, "Duplicate", "Unique")

Step 3: Standardize Text Values
For example, gender may be "M, Male, F, Female" → make consistent:
=IF(OR(C2="M", C2="Male"), "Male", "Female")
For lowercase values:   =LOWER(A2)

Step 4: Convert Dates
Convert inconsistent date formats into one (say dd-mm-yyyy):   =TEXT(D2, "dd-mm-yyyy")

Step 5: Fix Data Types
For age (ensure integer):  =INT(F2)
For valid ages only:   =IF(AND(F2>=0, F2<=120), F2, "Check")

Step 6 : Use Excel Text to Columns
1.	Select the column with these values.
2.	Go to Data → Text to Columns.
3.	Choose Delimited → Other and type T as the delimiter.
o	This splits into two columns:
	2016-04-29
	18:38:08Z
4.	Remove the trailing Z with =SUBSTITUTE(B2,"Z","").

Step 7: Proper Case Formatting
=PROPER(H2)

