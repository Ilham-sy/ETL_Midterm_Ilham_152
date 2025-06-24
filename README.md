# DSA2040A ETL Midterm – Ilham

**Name:** Ilham  
**Student ID (Last 3 Digits):** 123  
**Course:** Data Warehousing and Mining  
**Instructor:** Austin Odera  
**Semester:** US 2025



## 1. Project Overview

This ETL (Extract → Transform → Load) lab involves building a data pipeline to handle customer sales data. The goal is to extract data from CSV files, transform it by cleaning, enriching, and converting the structure, and load it into a database system (SQL Server or file format like Parquet).

The lab simulates real-world ETL tasks, focusing on proper file management, notebook organization, and professional documentation.



## 2. ETL Phases

### Extract – `etl_extract.ipynb`

- Loads `raw_data.csv` and `incremental_data.csv`
- Displays `.head()` and `.info()` for both
- Identifies:
  - Missing values
  - Duplicates
  - Unusual data types or columns
- Saves the data into the `data/` folder



### Transform – `etl_transform.ipynb`

Applies at least four transformations:
1. **Remove duplicates**
2. **Drop rows with missing values in key columns**
3. **Add a calculated `total_price = quantity * unit_price` column**
4. **Convert `order_date` to datetime format**
5. *(Optional)* Categorize spending level

Saves the transformed files to the `transformed/` folder:
- `transformed_full.csv`
- `transformed_incremental.csv`

Each transformation is clearly explained, with before-and-after views.



### Load – `etl_load.ipynb`

- Loads the transformed files into **SQL Server**
- Uses `pyodbc` to connect to a local database
- Inserts rows into a `full_data` table
- Confirms success by previewing records
- Alternative output (e.g., Parquet) can be used if SQL is unavailable



## 3. Tools Used

- Python 3.x
- Jupyter Notebook
- Pandas
- SQLite 
- Git & GitHub

---

## 4. How to Run the Project

```bash
# 1. Clone the GitHub repository

# 2. Run notebooks in order:
etl_extract.ipynb – Load and inspect raw data
etl_transform.ipynb – Clean and transform
etl_load.ipynb – Insert into database

# 3. Check your outputs:
- CSVs saved in /transformed/
- Data loaded into database (SQL Server or SQLite)
```
# Screenshots   
