  <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/052ccb4b-c54d-46e4-9b48-ecc4627db6aa" />

# 📊 HR Analytics Power BI Dashboard

This project presents an **HR Analytics Dashboard** developed using **Power BI**. The dashboard provides a comprehensive view of the organization’s workforce and focuses on **employee attrition trends**. It allows stakeholders to gain valuable insights into attrition by analyzing key dimensions such as **age, salary, tenure, gender, education level,** and **job role**.

---

## 📁 1. Data Import

The dataset is imported from a designated folder location into **Power BI Desktop** for further processing and analysis.

---

## 🧹 2. Data Cleaning and Preparation

Data cleaning and transformation steps were performed to ensure quality and consistency:

### a. Column Validation

* Verified the **data types** and ensured that each column contained relevant, expected data.

### b. Handling Missing Values

* Identified that one column had **\~4% missing entries**.
* Replaced missing values with `null` for standardization.

### c. Removing Duplicates

* Duplicates were removed using the **unique employee ID** to preserve data integrity.
* <img width="283" height="417" alt="image" src="https://github.com/user-attachments/assets/5cf45290-d928-4103-99f5-6765c20abe6f" />
<img width="395" height="319" alt="image" src="https://github.com/user-attachments/assets/69c96b6b-1f48-467c-a67f-b9407ca391b2" />



### d. Standardizing Categorical Values

* In the `BusinessTravel` column, inconsistent values such as `"Travel_Rarely"` and `"Travel Raely"` were standardized to `"TravelRarely"`.
<img width="395" height="319" alt="image" src="https://github.com/user-attachments/assets/a95e21d1-4e65-4e08-9c06-87d86d3ac758" />

---

## 🖥️ 3. Power BI Dashboard Design

The dashboard was designed with interactivity and clarity in mind, allowing users to filter and visualize attrition patterns dynamically.

### DAX Implementation

#### ➤ `Attrition_Count` (Calculated Column)

A new column was added to flag attrition cases:

```DAX
Attrition_Count = IF(Attrition = "Yes", 1, 0)
<img width="975" height="335" alt="image" src="https://github.com/user-attachments/assets/95dc806c-4a4c-4c84-a2a6-fce6dd45f12f" />

```

#### ➤ `Attrition_Rate` (Measure)

A DAX measure was created to calculate the overall attrition rate:

```DAX
Attrition_Rate = 
DIVIDE(SUM('EmployeeData'[Attrition_Count]), COUNT('EmployeeData'[EmployeeID]))
```

This metric represents the **proportion of employees who have left** the organization.

---

## 📌 Key Features

* Total employee count & attrition overview
* Interactive filters (age, gender, salary, etc.)
* Attrition breakdown by job role, education, and tenure
* Clean, standardized data ensuring reliable insights

---

## 📦 Technologies Used

* Power BI Desktop
* DAX (Data Analysis Expressions)
* Data Cleaning & Transformation

---

## 📍 Project Purpose

This dashboard is intended to help HR teams and decision-makers:

* Identify high-risk attrition segments
* Develop employee retention strategies
* Make data-informed organizational decisions
