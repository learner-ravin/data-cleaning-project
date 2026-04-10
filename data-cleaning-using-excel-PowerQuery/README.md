# Audiobook Data Cleaning using Excel Power Query

## Project Overview

This project focuses on cleaning the real-world audiobook dataset scraped from Audible. This messy dataset contains multiple inconsistencies such as wrong data types, redundant texts, mixed formats, and unstructured fields.

The objective of this project is to transform the dataset into a clean and structured format using **Excel Power Query**, making it suitable for further analysis and visualization.

The data is downloaded from [kaggle](https://www.kaggle.com/datasets/snehangsude/audible-dataset?select=audible_uncleaned.csv).

---

## Dataset Summary
* **Uncleaned dataset have 87489 rows and 8 columns.
* **Cleaned dataset have 10 columns.

### Key Features:

* `name` – Audiobook title
* `author` – Author name
* `narrator` – Narrator name
* `time` – Duration 
* `releasedate` – Release date
* `language` – Language of audiobook
* `stars` – rating of audiobook and number of ratings
* `price` – Price of audiobook

---

## Key Issues in the dataset:

1) **Redundant text in columns:**
  The `author` and `narrator` columns contain unnecessary prefixes such as *"Writtenby:"* and *"Narratedby:"*, which add no analytical value.

2) **Improper name formatting:**
  Author and narrator names have no space between first and last name, which reduce readability and consistency.

3) **Incorrect data type for duration:**
  The `time` column is stored as text ,It is not suitable for any further analysis.

4) **Ambiguous date format:**
  The `releasedate` column uses a short date format (*dd-mm-yy*), which is hard to interpret.

5) **Multiple values in the `stars` column:**
  The `stars` column combines two different pieces of information, **rating value** and the **number of ratings**.

---

## 🔧 Data Cleaning Process usin Power Query 

### 1. Text Cleaning

* Removed prefixes  `"Writtenby:"` and `"Narratedby:"` from author and narrator column.
* Standardized author and narrator names (added proper spacing).

### 2. Feature Engineering

* Extracted hour and mintue from text and converted it into numeric format `duration(mins)`, suitable for analysis.

### 3. Data Standardization

* Converted `releasedate` into standard format (`YYYY-MM-DD`)

### 3. Data Transformation
* Split `stars` column into:
  * `ratings` -> rating value
  * `numberofratings` -> number of ratings


---

## Data Transformation Flow

```
Raw Data
   ↓
Remove Redundant Text
   ↓
Fix Name Formatting
   ↓
Convert Time → Duration (mins)
   ↓
Standardize Date Format
   ↓
Split Ratings Column
   ↓
Cleaned Dataset
```

---

## 🛠 Tools Used

* Microsoft Excel
* Power Query

---

