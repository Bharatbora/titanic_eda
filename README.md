# Titanic Survival Analysis Dashboard

This project explores survival outcomes on the RMS Titanic using passenger demographics, ticket classes, fares, and embarkation details. Using Python for data cleaning and exploratory analysis (EDA), the dashboard-style insights highlight who survived and why across class, sex, and boarding port patterns.

---

## Project Objective

The goal of this project is to:  
- Analyze survival patterns by sex, class, age, family size, fare, cabin availability, and embarkation port.  
- Build a clean, consistent dataset ready for modeling and dashboarding.  
- Visualize key relationships (e.g., survival by sex/class, distribution of ages/fare, missingness) to surface actionable insights.  

---

## Dataset Overview


| Field     | Description |
|-----------|-------------|
| Survived  | 0 = No, 1 = Yes |
| Pclass    | 1, 2, 3 passenger classes |
| Sex       | male/female |
| Age       | passenger age (years), missing values imputed |
| SibSp     | number of siblings/spouses aboard |
| Parch     | number of parents/children aboard |
| Ticket    | alphanumeric identifier |
| Fare      | numeric fare, right-skewed |
| Cabin     | mostly missing, set to “Unknown” if null |
| Embarked  | C = Cherbourg, Q = Queenstown, S = Southampton |

**Record counts and completeness:**  
- 1,309 rows  
- 12 columns  
- Notable missingness: Age (263 nulls), Fare (1 null), Cabin (1,014 nulls), Embarked (2 nulls)  

The dataset was inspected with `head()` and `info()`, and visual previews were created to verify schema and data integrity.

---

## Tools Used

- **Python** (pandas, numpy) for data wrangling and quality checks  
- **Matplotlib** and **Seaborn** for visualizations  
- **CSV file** for input data: `titanic_dataset.csv`  
- **Notebook** for workflow and outputs: `titanic.ipynb`  

--- 

Key findings from exploratory analysis:  
- **Survival rates** vary strongly by sex and class; females and first-class passengers have higher survival  
- **Age and Fare distributions** are skewed; fare outliers correspond to high-cabin and first-class tickets  
- **Embarked categories** are imbalanced; Southampton dominates the manifest  
- **Cabin** is mostly missing; using a “has_cabin” flag preserves information without dropping rows  

Visual insights were created via countplots for survival by sex, class, and embarkation, plus distribution plots for numeric fields.

---

## Data Cleaning Highlights (Python)

Key preparation steps in the notebook:  
- **Missing value treatment:**  
  - Filled `Cabin` nulls with `"Unknown"`  
  - Imputed `Age` with mean  
  - Dropped residual nulls post-targeted fills  
- **Integrity checks:**  
  - Verified zero duplicate rows  
  - Lowercased column names for consistency  
- **Type handling and summaries:**  
  - Confirmed dtypes and null counts  
  - Basic profiling via `df.info()` and value counts  

> Full cleaning logic is in the notebook cells using `df.isnull()`, targeted fills, `df.dropna()`, and duplicate checks.


---

## Folder Structure
 -  `titanic.ipynb`— primary analysis and visuals.-
 -    `titanic.csv` — input dataset.


## How to Run

1. Open `titanic.ipynb` in a Python environment with pandas, numpy, matplotlib, seaborn  
2. Load  `titanic.ipynb` and execute cells sequentially to reproduce cleaning, summaries, and plots  
3. Optionally export cleaned data and figures for downstream dashboards  

---

## Future improvements

- Build a baseline classifier (e.g., logistic regression) using engineered features (`Sex`, `Pclass`, `Age`, `Fare`, `Embarked`, `FamilySize`, `Title`)  
- Create an interactive dashboard (Power BI or Plotly Dash) for filtering by class, port, and demographics  

---





