# 🧹 Data Cleaning & Preprocessing – Elevate Labs Task 01

This Jupyter Notebook (`Elevate_Labs_Task_1.ipynb`) documents a comprehensive data cleaning and preprocessing pipeline. The goal is to transform raw, messy data into a structured, standardized, and analysis-ready dataset.

---

## 📋 Objectives

- Standardize and clean column names
- Convert object columns to appropriate data types
- Handle missing values and duplicates
- Normalize and encode categorical fields
- Prepare textual data for further analysis

---

## 🔧 Key Steps Performed

### ✅ 1. Column Name Standardization
- Trimmed whitespace from column names
- Converted all column names to lowercase
- Replaced spaces with underscores
- Removed special characters

```python
df.columns = df.columns.str.strip() \
                       .str.lower() \
                       .str.replace(' ', '_') \
                       .str.replace('[^0-9a-zA-Z_]', '', regex=True)

### ✅ 2. Data Type Conversion
- Converted object columns containing dates to datetime64 format using pd.to_datetime()

df['date_column'] = pd.to_datetime(df['date_column'], errors='coerce')


### ✅ 3. Handling Missing Values
- Identified missing values using .isnull().sum()
- Filled missing numeric values with mean/median
- Handled missing categorical values using mode or "Unknown"

### ✅ 4. Removing Duplicates
-Removed exact duplicates using:
df.drop_duplicates(inplace=True)


### ✅ 5. Standardizing Categorical Text
-Cleaned and mapped inconsistent text values (e.g., gender, country).
-Applied .str.lower(), .strip(), and mapping dictionaries.

### ✅ 6. Value Counts for Categorical Columns
- Analyzed frequency of values using:
df['gender'].value_counts()

### ✅ 7. Text Preprocessing (if applicable)
- Applied lowercase conversion, removed punctuation, and eliminated stopwords for text-based columns

### 💾 Output
The cleaned and preprocessed dataset is now ready for:
-Exploratory Data Analysis (EDA)
-Feature engineering
-Machine learning or NLP modeling











