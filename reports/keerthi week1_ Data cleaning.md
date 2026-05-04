
## Week 1: Data Cleaning & Preparation

### Objective
To clean and prepare the hotel booking dataset for further analysis.

---

### Dataset
- Dataset: Hotel Booking Dataset  
- Records: ~119,390 rows  
- Columns: 32 features  
- Source: CSV file  

---

### Data Cleaning Performed

#### 1. Dataset Overview
- Checked dataset structure using `df.info()` and `df.shape()`  

**Insight:**  
Dataset contains 32 columns with mixed data types  

---

#### 2. Missing Values Handling
- Identified missing values in columns like:
  - children  
  - country  
  - agent  
  - company  

- Filled missing values:
  - children → 0  
  - country → "Unknown"  
  - agent → 0  
  - company → 0  

**Insight:**  
Missing values handled to avoid errors during analysis  

---

#### 3. Data Type Correction
- Verified correct data types for all columns  

**Insight:**  
Ensured numerical and categorical columns are properly formatted  

---

#### 4. Duplicate Check
- Checked for duplicate records  

**Insight:**  
No major duplicate issues found  

---

#### 5. Data Consistency
- Ensured consistent values across dataset  
- Removed inconsistencies if any  

**Insight:**  
Dataset is clean and structured  

---

### Tools Used
- Python  
- Pandas  

---

### Outcome
- Clean dataset ready for analysis  
- No critical missing values  
- Structured and usable data  

---

### Conclusion
Data cleaning improved data quality and ensured accurate analysis in the next phase (EDA).
