# DSA2040A ETL Midterm – Ilham

**Name:** Ilham  
**Student ID (Last 3 Digits):** 123  
**Course:** Data Warehousing and Mining  
**Instructor:** Austin Odera  
**Semester:** US 2025



## 1. Project Overview
**Project Title:** ETL Lab – Customer Sales Data Pipeline 

**GitHub Repository:** [ETL Lab Repository](https://github.com/yourusername/etl-lab)  

**Project Description:**

This project is an ETL lab designed to simulate a real-world data pipeline scenario. It involves extracting customer sales data from CSV files, transforming it through various data cleaning and enrichment processes, and loading the final dataset into a database system. The project emphasizes best practices in ETL processes, including file management, documentation, and version control.  

The lab is structured into three main phases: Extract, Transform, and Load, each represented by a Jupyter Notebook. The project also includes visual elements to enhance understanding of the data transformations and distributions.

**Project Goals:**  
- To practice ETL processes using Python and Jupyter Notebooks
- To handle customer sales data effectively   
- To demonstrate data cleaning, transformation, and loading into a database
- To apply best practices in data management and documentation

**Project Context:**
This project is part of the Data Warehousing and Mining course, focusing on practical applications of ETL techniques. It simulates a scenario where customer sales data needs to be processed for analysis, highlighting the importance of data quality and structure in data engineering tasks.

**Project Scope:**
- Extract data from provided CSV files          
- Transform the data through cleaning and enrichment
- Load the transformed data into a SQL Server database or alternative format
- Document the process and results in Jupyter Notebooks

**Project Structure:**
```
etl-lab/      
├── data/                  # Folder for raw data files
├── transformed/           # Folder for transformed data files
├── etl_extract.ipynb      # Notebook for data extraction
├── etl_transform.ipynb    # Notebook for data transformation
├── etl_load.ipynb         # Notebook for data loading  
├── README.md              # Project documentation
└── requirements.txt       # Python dependencies
```       

**Data Files:**
- `raw_data.csv`: Contains initial customer sales data
- `incremental_data.csv`: Contains new sales data to be added
- Both files are located in the `data/` folder  
- The data includes columns such as `order_id`, `customer_id`, `order_date`, `quantity`, and `unit_price`.  
- The data is structured to allow for transformations such as calculating total prices and handling missing values. 
  

## 2. ETL Phases
This project is divided into three main Jupyter Notebooks, each representing a phase of the ETL process: Extract, Transform, and Load. Each notebook is designed to be run sequentially, with clear documentation and comments explaining each step.
### Requirements
Ensure you have the following Python packages installed:
```bash
pip install pandas pyodbc
```
### 1. Extract – `etl_extract.ipynb`
- Loads the initial data from `raw_data.csv` and `incremental_data.csv` 
- Displays the first few rows and information about the datasets using `.head()` and `.info()`
- Identifies:
  - Missing values
  - Duplicates
  - Unusual data types or columns
- Saves the data into the `data/` folder for further processing
- The extraction phase ensures that the data is ready for transformation, providing a clear overview of its structure and quality.

### 2. Transform – `etl_transform.ipynb`
- Applies at least four transformations to the extracted data:  
1. **Remove duplicates**: Ensures no repeated records exist in the dataset.
2. **Drop rows with missing values in key columns**: Cleans the dataset by removing incomplete records that could affect analysis.
3. **Add a calculated `total_price = quantity * unit_price` column**: Enriches the dataset with a new field that provides insights into customer spending.
4. **Convert `order_date` to datetime format**: Standardizes the date format for easier analysis and querying.
5. *(Optional)* Categorize spending level: Adds a new column to classify customers based on their spending habits, enhancing the dataset for further analysis.
- Saves the transformed data into the `transformed/` folder as:
  - `transformed_full.csv`: Contains the full dataset after transformations
  - `transformed_incremental.csv`: Contains the incremental data after transformations    
- Each transformation is clearly explained, with before-and-after views to illustrate the changes made to the dataset.

### 3. Load – `etl_load.ipynb`
- Loads the transformed data into a SQL Server database using `pyodbc`
- Connects to a local database and inserts rows into a `full_data` table
- Confirms success by previewing records in the database
- If SQL Server is unavailable, an alternative output format (e.g., Parquet) can be used to save the transformed data
- The loading phase ensures that the cleaned and enriched data is stored in a structured format, ready for analysis and reporting.    


## 3. Tools Used
This project utilizes various tools and technologies to facilitate the ETL process, data manipulation, and version control. The following tools are essential for running the project:
- **Python**: The primary programming language used for data manipulation and ETL processes.      
- **Jupyter Notebook**: An interactive environment for writing and executing Python code, allowing for step-by-step data processing and visualization.
- **Pandas**: A powerful data manipulation library in Python, used for reading, transforming, and writing data in various formats.
- **SQLite**: A lightweight database system used for storing the transformed data. It can be  replaced with SQL Server or another database system if preferred.
- **Git & GitHub**: Version control system and platform for hosting the project repository, allowing for collaboration, tracking changes, and sharing the project with others.  
- **pyodbc**: A Python library for connecting to SQL databases, used in the loading phase to insert data into the database.
- **Matplotlib/Seaborn**: Optional libraries for data visualization, used to create charts and graphs to support data profiling and analysis. 
- **CSV**: The format used for the raw and transformed data files, allowing for easy reading and writing of tabular data.

---

## 4. How to Run the Project
To run this project, follow these steps:
1. Clone the GitHub repository to your local machine. 
2. Ensure you have the required Python packages installed (as listed in `requirements.txt`).
3. Open each Jupyter Notebook in order: 
   - `etl_extract.ipynb` to load and inspect the raw data
   - `etl_transform.ipynb` to clean and transform the data
   - `etl_load.ipynb` to insert the transformed data into the database  
4. Check the outputs:
- The transformed data will be saved as CSV files in the `transformed/` folder.
- The data will be loaded into the specified database (SQL Server or SQLite). 

You can run the notebooks in Jupyter Notebook or JupyterLab. Each notebook contains detailed comments and explanations of the steps involved in the ETL process.


## 5. Visuals and Screenshots
The project includes two visual elements to support the transformation and provide a better understanding of the data:

### Preview of Transformed Data
A screenshot showing a few rows from transformed_full.csv, confirming that transformations such as total_price calculation and order_date formatting were successful.

### Total Price Distribution Chart
A histogram visualization of the total_price column, illustrating how customer spending varies across the dataset. This supports data profiling and meets the bonus requirement for including a visual.

## 6. Bonus Features      
- **Data Profiling**: The project includes a histogram of the `total_price` column, showing customer spending distribution.
- **Data Validation**: The transformation notebook checks for missing values and duplicates, ensuring data quality.
- **Documentation**: Each notebook contains detailed comments explaining the purpose and steps of each transformation.      
- **Version Control**: The project is managed using Git, with a clear commit history and organization in the repository.    
- **Error Handling**: The load notebook includes basic error handling to catch connection issues or SQL errors. 
- **Data Enrichment**: The transformation step includes a calculated field (`total_price`) to enhance the dataset.

## 7. Conclusion  
This ETL lab provides a comprehensive exercise in data extraction, transformation, and loading. By following the steps outlined in the notebooks, you can effectively manage customer sales data, ensuring it is clean, structured, and ready for analysis. The project demonstrates essential ETL skills applicable in real-world scenarios, preparing you for future data engineering tasks.
