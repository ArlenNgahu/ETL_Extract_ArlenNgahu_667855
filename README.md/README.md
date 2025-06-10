
# 📊 ETL Full and Incremental Extraction

**Student Name:** Arlen Ngahu  
**Student ID:** 667855  

---

## 📖 Description

This project implements an ETL (Extract, Transform, Load) process in a Jupyter Notebook using a dataset of Breast Cancer Wisconsin (Diagnostic) records. 

The notebook performs two types of data extraction from a CSV file:
1. **Full Extraction** – Extracts and displays the entire dataset.
2. **Incremental Extraction** – Extracts only new records that were added since the last extraction time, which is tracked using a simple `last_extraction.txt` file.

The notebook uses a timestamp column in the dataset to determine new records for incremental extraction and updates the `last_extraction.txt` file with the latest extraction time after each incremental extraction.

---

## 🛠️ Tools Used

- Python 3.x  
- Jupyter Notebook (via Google Colab)  
- pandas  
- datetime  
- Breast Cancer Wisconsin (Diagnostic) dataset from Kaggle  

---

## 🚀 How to Reproduce

### a) How to Run the Notebook:

1. Upload the following files to your Google Colab `/content/` directory:
   - `data.csv` (Breast Cancer dataset)
   - `last_extraction.txt` (optional — the notebook will create it automatically if missing)

2. Open and run the `etl_extract.ipynb` notebook step-by-step in Google Colab.

3. The notebook will:
   - Perform a full extraction of all data
   - Perform an incremental extraction based on the last extraction timestamp
   - Update the `last_extraction.txt` file with the latest timestamp

4. You can view the extracted data outputs and updated timestamp in the notebook and Colab file directory.

---

### b) Where the Data Comes From:

The dataset used in this project is the **Breast Cancer Wisconsin (Diagnostic) dataset**, publicly available on [Kaggle](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data).

---

## 📂 Project Structure

```
ETL_Extract_ArlenNgahu_667855/
├── etl_extract.ipynb         # Jupyter notebook containing the ETL code
├── data.csv                  # Breast Cancer dataset from Kaggle
├── last_extraction.txt       # Text file storing last extraction timestamp
├── README.md                 # Project description and instructions
```

---

## 📌 Notes

- Incremental extraction requires a `timestamp` column in the dataset.  
- If your dataset lacks one, you may need to add or adjust a time-based field to use incremental extraction.
