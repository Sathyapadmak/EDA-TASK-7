# Student Performance Data Analysis 📊

## Overview

This project performs exploratory data analysis and preprocessing on the **Students Performance** dataset. It examines student scores in mathematics, reading, and writing, standardizes categorical attributes, derives aggregate performance metrics, and identifies statistical outliers. The cleaned dataset is exported for further analysis or modelling.

## Dataset 📁

**File:** `StudentsPerformance.csv`

| Column | Description |
|---|---|
| `gender` | Gender of the student |
| `race/ethnicity` | Group classification of the student |
| `parental level of education` | Highest level of education attained by the parent(s) |
| `lunch` | Type of lunch received (standard or free/reduced) |
| `test preparation course` | Completion status of the test preparation course |
| `math score` | Score in mathematics |
| `reading score` | Score in reading |
| `writing score` | Score in writing |

## Objectives 🎯

1. Inspect the structure and quality of the dataset.
2. Standardize categorical variables for consistency.
3. Compute descriptive statistics for each subject.
4. Engineer aggregate features: total marks and percentage.
5. Detect outliers using the Interquartile Range (IQR) method.
6. Export the cleaned dataset.

## Methodology ⚙️

### 1. Data Inspection
- Preview of the first five records
- Dataset dimensions, column names, and data types
- Missing value and duplicate row checks
- Summary statistics for numerical columns

### 2. Data Cleaning
Categorical columns are converted to the string type, stripped of leading and trailing whitespace, and converted to lowercase. This ensures consistent category labels.

### 3. Descriptive Statistics
For each of the three score columns, the following are calculated:
- Mean, median, and standard deviation
- First quartile (Q1), second quartile (Q2), and third quartile (Q3)

### 4. Feature Engineering
- **Total marks:** sum of math, reading, and writing scores (out of 300)
- **Percentage:** total marks divided by 300, multiplied by 100

### 5. Outlier Detection
Outliers are identified for each subject using the IQR method:

- Lower bound = Q1 − 1.5 × IQR
- Upper bound = Q3 + 1.5 × IQR

Values outside these bounds are flagged as outliers, and their counts are reported per subject.

### 6. Export
The processed dataset is saved as `Student_Performance_Cleaned.csv`.

## Requirements 📦

- Python 3.8 or later
- pandas

Install the dependency with:

```bash
pip install pandas
```

## Usage ▶️

1. Place `StudentsPerformance.csv` in the same directory as the notebook.
2. Run the notebook cells sequentially.
3. The cleaned dataset will be generated as `Student_Performance_Cleaned.csv`.

## Project Structure

```
.
├── StudentsPerformance.csv          # Input dataset
├── Student_Performance_Cleaned.csv  # Output dataset (generated)
├── notebook.ipynb                   # Analysis notebook
└── README.md
```

## Output

The cleaned dataset contains all original columns with standardized categorical values, together with two additional columns:

- `total marks`
- `percentage`
