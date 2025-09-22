# medical-appointment-data-cleaning
 Project Overview
This project cleans and preprocesses Kaggle's **Medical Appointment No Shows** dataset using **Excel**.  
The dataset contains patient appointment records from Brazil and whether patients showed up for their scheduled visit.

 ## Objectives
- Handle missing values
- Remove duplicate rows
- Standardize text values (e.g., gender, neighbourhood, no_show)
- Convert date formats into `dd-mm-yyyy`
- Rename and clean column headers (lowercase, snake_case, corrected typos)
- Check and fix data types (age = integer, date = datetime)


## Tools Used
- Microsoft Excel  
- Excel formulas: `IF`, `COUNTBLANK`, `LOWER`, `PROPER`, `SUBSTITUTE`, `VLOOKUP`, `TEXT`, `TRIM`


## Cleaning Steps Applied
1. **Missing values** → replaced with `"Unknown"` where applicable  
2. **Duplicates** → removed using Excel’s “Remove Duplicates”  
3. **Standardization** → gender (`Male/Female`), no_show (`Yes/No`), neighbourhoods (`PROPER(TRIM())`)  
4. **Dates** → converted from ISO format (`2016-04-29T18:38:08Z`) to `dd-mm-yyyy`  
5. **Column headers** → renamed to lowercase + underscores, fixed typos (`hipertension → hypertension`, `handcap → handicap`)  
6. **Data types** → ensured ages are between 0 and 120, converted dates properly  

