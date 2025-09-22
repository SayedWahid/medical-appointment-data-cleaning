# medical-appointment-data-cleaning
Project Overview
This project cleans and preprocesses the Medical Appointment No Shows dataset from Kaggle.  
The dataset contains information about patients’ medical appointments in Brazil and whether they showed up or not.  

The goal was to prepare a clean, standardized dataset using Excel only (no Python), fixing missing values, duplicates, inconsistent text, date formats, and column headers.

Objectives
- Handle missing values  
- Remove duplicate rows  
- Standardize text values (gender, neighbourhood, no_show, etc.)  
- Convert date formats into a consistent structure (`dd-mm-yyyy`)  
- Rename and clean column headers (lowercase, no spaces, snake_case)  
- Ensure correct data types (age = integer, date = datetime)  

Tools
- Excel 2024
- Excel formulas: `IF`, `COUNTBLANK`, `LOWER`, `PROPER`, `SUBSTITUTE`, `VLOOKUP`, `TEXT`, `TRIM`, etc.  

Cleaning Steps
1. Missing Values
   - Checked blanks with `=COUNTBLANK(A2:A1000)`  
   - Replaced missing entries with `"Unknown"` or corrected manually  

2. Remove Duplicates  
   - Used Excel’s Data → Remove Duplicates  
   - Formula check: `=IF(COUNTIF(A:A,A2)>1,"Duplicate","Unique")`  

3.  Standardize Text Values 
   - Gender → `Male / Female` only  
     =IF(OR(LOWER(C2)="m", LOWER(C2)="male"), "Male", "Female")
   - No-show → `Yes / No`  
     =IF(LOWER(C2)="yes","Yes","No")
   - Neighbourhood → Proper case  
     =PROPER(TRIM(H2))

4. Date Formatting
   - Converted `2016-04-29T18:38:08Z` into clean format  
     ```excel
     =TEXT(LEFT(D2,10),"dd-mm-yyyy")
     =MID(D2,12,8)
     ```  

5.  Column Headers 
   - Renamed to snake_case:  
     patient_id, appointment_id, gender, scheduled_day, appointment_day, 
     age, neighbourhood, scholarship, hypertension, diabetes, alcoholism, 
     handicap, sms_received, no_show

6. Data Types
   - Age → `=IF(AND(C2>=0,C2<=120),INT(C2),"Check")`  
   - Dates → formatted as `dd-mm-yyyy`  

