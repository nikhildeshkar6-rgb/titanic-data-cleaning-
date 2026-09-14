# Titanic Dataset — Data Cleaning & Preparation

## Project
This project cleans and prepares a public Titanic passenger dataset for analysis.

## Dataset
**Dataset:** Titanic passenger dataset (commonly distributed as `titanic3.csv` / Titanic passenger data).

**Public source:** Vanderbilt University / OpenIntro Titanic dataset mirror:
https://hbiostat.org/data/repo/titanic3.csv

The raw file used for this project contains 1,309 passenger records and 14 fields.

## Cleaning performed

### 1. Missing values
- `age`: missing values were filled using the median age within `pclass` and `sex`; overall median was used as a fallback.
- `fare`: missing value was filled using the median fare for the passenger's class.
- `embarked`: missing values were filled with the most frequent embarkation port.
- `cabin`, `boat`, `home_dest`: missing values were replaced with `Not Recorded` because the absence of a value means the information was not recorded/not applicable.
- `body`: missing values were represented as `-1` and documented as "not recorded/not identified" rather than treating them as a real body number.

### 2. Duplicate records
- Exact duplicate rows were checked and removed.
- The raw dataset contained **0 exact duplicate rows**, so no passenger records were removed for duplication.

### 3. Data types
- Passenger class, survival, sibling/spouse count, parent/children count, and body number were converted to integer-compatible types.
- Age and fare were converted to numeric types.
- Text fields were standardized as strings.

### 4. Inconsistent values
- Column names were standardized to lowercase `snake_case`.
- `sex` values were standardized to `Male` / `Female`.
- `embarked` values were standardized to `S`, `C`, and `Q`.
- Leading/trailing whitespace was removed from text fields.
- Survival was validated as 0/1 and passenger class as 1/2/3.

## Output files
- `titanic_cleaned.csv` — cleaned dataset ready for analysis.
- `data_quality_report.csv` — post-cleaning data-quality summary.

## Tools
Python, pandas, and NumPy.

## Result
The cleaned dataset retains the original passenger records while making missing values explicit, standardizing fields, and correcting data types for analysis.
