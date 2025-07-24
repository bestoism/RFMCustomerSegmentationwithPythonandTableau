# RFM Customer Segmentation Analysis

![Python](https://img.shields.io/badge/python-3.10-blue.svg)
![Pandas](https://img.shields.io/badge/pandas-2.0-yellow.svg)
![Tableau](https://img.shields.io/badge/tableau-Public-green.svg)

An end-to-end data analysis project that segments customers based on their purchasing behavior using the RFM model. The analysis is performed in Python, and the final insights are presented in an interactive Tableau dashboard.

---

## Project Overview

This project demonstrates a complete data analysis workflow, starting from a large, raw transactional dataset to a final, actionable business intelligence tool. The primary goal is to identify distinct customer groups to enable a company to run more effective, targeted marketing campaigns.

**Final Interactive Dashboard:** [[**Link ke Dashboard Tableau Public Anda di Sini**]](https://public.tableau.com/views/CustomerSegmentationAnalysisRFMModel/Dashboard1?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

## The Dataset

The data used for this project is the **Online Retail Dataset** from the UCI Machine Learning Repository.

*   **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/online+retail)
*   **Size:** Contains 541,909 transactions from a UK-based online retail company.
*   **Attributes:** `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.

---

## Tech Stack
*   **Data Manipulation & Analysis:** Python, Pandas
*   **Data Visualization (Initial):** Matplotlib, Seaborn
*   **Interactive Dashboard:** Tableau Public
*   **Development Environment:** Google Colab / Jupyter Notebook

---

## Project Workflow

The project followed these key steps:

**1. Data Cleaning & Preprocessing:**
   - Loaded the dataset from an Excel file.
   - Handled missing `CustomerID` values by removing them.
   - Filtered out negative `Quantity` records, which represent returns or canceled orders.
   - Corrected data types, specifically converting `InvoiceDate` to a datetime object.

**2. Feature Engineering:**
   - Created a `TotalPrice` column by multiplying `Quantity` and `UnitPrice`. This is essential for the Monetary calculation.

**3. RFM Metrics Calculation:**
   - Aggregated the data by `CustomerID` to calculate the three core RFM metrics:
     - **Recency:** Days since a customer's last purchase.
     - **Frequency:** The total number of unique invoices (transactions).
     - **Monetary:** The total amount of money spent by the customer.
   - This step transformed the dataset from over 397,000 transaction lines to 4,339 unique customer summaries.

**4. Scoring & Segmentation:**
   - Scored each customer from 1 to 5 for each RFM metric using quintiles (`pd.qcut`).
   - Implemented a rule-based mapping system to assign customers to descriptive segments like `Champions`, `At-Risk`, and `New Customers` based on their R and F scores.

**5. Data Export & Visualization:**
   - The final segmented DataFrame was exported to a `.csv` file.
   - This CSV was then used as the data source in Tableau to build the final interactive dashboard.

---

## Key Insights & Visualization

The final dashboard provides a clear overview of the customer base.

<img width="1827" height="710" alt="image" src="https://github.com/user-attachments/assets/621f4ad4-67ae-436b-bfe2-61f463952bd0" />

**Key Findings:**
*   **Largest Segments:** The "Potential Loyalists & Champions" and "Hibernating" groups are the largest, representing both the biggest opportunity and the biggest risk.
*   **Most Valuable Segments:** The Treemap shows that "Loyal Customers" and "Champions" contribute the most to revenue, highlighting their importance.
*   **Behavioral Patterns:** The scatter plot clearly distinguishes the behavior of high-value, recent customers from those who are dormant, providing a visual guide for marketing targeting.

---

## How to Run this Project

1.  **Clone the repository:**

2.  **Install dependencies:**
    ```bash
    pip install pandas matplotlib seaborn openpyxl
    ```
3.  **Run the notebook:** Open and run the `RFM_Analysis_Online_Retail.ipynb` file in a Jupyter or Google Colab environment. Ensure the `Online Retail.xlsx` dataset is in the same directory.
4.  **Explore the dashboard:** Use the generated `rfm_analysis_for_dashboard.csv` as a data source in Tableau Public to recreate or explore the dashboard.

---

