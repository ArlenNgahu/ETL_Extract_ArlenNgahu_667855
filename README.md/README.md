
# ETL Full and Incremental Extraction

# Student Name: Arlen Ngahu  
# Student ID: 667855  



# Description

This project implements an ETL (Extract, Transform, Load) process in a Jupyter Notebook using a dataset of Breast Cancer Wisconsin (Diagnostic) records. 

The notebook performs two types of data extraction from a CSV file:
1. **Full Extraction** – Extracts and displays the entire dataset.
2. **Incremental Extraction** – Extracts only new records that were added since the last extraction time, which is tracked using a simple `last_extraction.txt` file.

The notebook uses a timestamp column in the dataset to determine new records for incremental extraction and updates the `last_extraction.txt` file with the latest extraction time after each incremental extraction.



# Tools Used

- Python 3.x  
- Jupyter Notebook (via Google Colab)  
- pandas  
- datetime  
- Breast Cancer Wisconsin (Diagnostic) dataset from Kaggle  
- sqlite3



# How to Reproduce

# a) How to Run the Notebook:

1. Upload the following files to your Google Colab `/content/` directory:
   - `data.csv` (Breast Cancer dataset)
   - `last_extraction.txt` (optional — the notebook will create it automatically if missing)

2. Open and run the `etl_extract.ipynb` notebook step-by-step in Google Colab.

3. The notebook will:
   - Perform a full extraction of all data
   - Perform an incremental extraction based on the last extraction timestamp
   - Update the `last_extraction.txt` file with the latest timestamp

4. You can view the extracted data outputs and updated timestamp in the notebook and Colab file directory.



# b) Where the Data Comes From:

The dataset used in this project is the **Breast Cancer Wisconsin (Diagnostic) dataset**, publicly available on [Kaggle](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data).


# Project Structure

```
ETL_Extract_ArlenNgahu_667855/
├── etl_extract.ipynb # Data extraction notebook
├── etl_transform.ipynb # Data transformation notebook
├── etl_load.ipynb # Data loading notebook
├── data.csv # Breast Cancer dataset from Kaggle
├── last_extraction.txt # Text file storing last extraction timestamp
├── transformed_full.csv # Full transformed data
├── transformed_incremental.csv # Incrementally transformed data
├── loaded_data/ # Directory for loaded SQLite DBs
│ ├── full_data.db
│ └── incremental_data.db
├── README.md # Project description and instructions
└── .gitignore # Git ignore rules
```



# Notes

- Incremental extraction requires a `timestamp` column in the dataset but I used the 'id' column since I lacked any similar column.  
- If your dataset lacks one, you may need to add or adjust a time-based field to use incremental extraction.

# New in Lab 4: Data Transformation

Added new transformation steps:
- Removed duplicates
- Handled missing values by filling with mean
- Added a new calculated column: 'radius_texture_product' (mean_radius * mean_texture)
- Converted 'diagnosis' codes to full labels (Malignant/Benign)

New outputs:
- transformed_full.csv
- transformed_incremental.csv

# Loading Method:  
- Loaded both `transformed_full.csv` and `transformed_incremental.csv` into SQLite databases using `pandas.to_sql()`.

# Sample Code:
```python
import sqlite3
conn = sqlite3.connect('full_data.db')
df.to_sql('full_data', conn, if_exists='replace', index=False)

New outputs: 
- full_data.db
- incremental_data.db


