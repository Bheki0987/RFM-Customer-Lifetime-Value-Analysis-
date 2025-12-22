# 🛒 RFM Customer Segmentation & Lifetime Value Analysis

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=Tableau&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> **A strategic data analytics project that leverages the RFM (Recency, Frequency, Monetary) model to segment retail customers and visualize purchasing behaviors for targeted marketing campaigns.**

---

## 📊 Dashboard Preview

[![View on Tableau Public](https://img.shields.io/badge/View_Interactive_Dashboard-Tableau-E97627?style=for-the-badge&logo=tableau)](https://public.tableau.com/views/CustomerLifetimeValueAnalysisVisualization/InteractiveDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

*(Note: Click the button above to interact with the full dashboard, including filters for Country, RFM Score, and Customer Segments.)*

---

## 📖 Project Context

In the competitive retail landscape, treating all customers the same leads to wasted marketing budget and missed opportunities. This project solves that problem by implementing **RFM Analysis**—a proven marketing technique used to quantitatively rank and group customers based on:

1.  **Recency (R):** How recently did the customer purchase?
2.  **Frequency (F):** How often do they purchase?
3.  **Monetary Value (M):** How much do they spend?

**Goal:** To transform 500,000+ raw transaction rows into a clear "Customer Strategy Map" that identifies **Champions**, **At-Risk** clients, and **New Opportunities**.

---

## ⚙️ Tech Stack & Workflow

| Phase | Tool | Key Actions |
| :--- | :--- | :--- |
| **1. Ingestion** | **Excel** | Initial data inspection and delimiter handling. |
| **2. Cleaning** | **Python (Pandas)** | Handling missing `CustomerID`s, DateTime conversion, and type casting. |
| **3. Processing** | **SQLite (SQL)** | Querying raw data to calculate R, F, and M values per customer. |
| **4. Analysis** | **Python** | Scoring logic (1-4 scale) and customer segmentation mapping. |
| **5. Visualization** | **Tableau Public** | Dashboard design, parameter creation, and interactivity. |

---

## 🔍 Methodology

### 1. Data Preprocessing
Used Python to clean the [UCI Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail). Key steps included:
* Removal of null CustomerIDs (crucial for per-customer analysis).
* Sanitization of text columns (stripping whitespace).
* Date normalization to ensure accurate "Recency" calculations.

### 2. The RFM Logic
Customers were assigned a score from **1 to 4** for each metric:
* **Recency:** 4 = Most recent purchase (Best), 1 = Oldest purchase.
* **Frequency:** 4 = Most frequent buyer, 1 = One-time buyer.
* **Monetary:** 4 = Highest spender, 1 = Lowest spender.

### 3. Segmentation Strategy
Based on the combined RFM scores, customers were grouped into actionable cohorts:
* 🏆 **Champions:** High R, High F, High M (Reward them).
* 💍 **Loyal Customers:** Good F and M, moderate R (Upsell them).
* ⚠️ **At Risk:** High past value, but low Recency (Re-engage them).
* 💤 **Lost:** Low across all metrics (Ignore or low-cost outreach).

---

## 📉 Key Insights

* **Revenue Concentration:** A small percentage of "Champion" customers contribute a disproportionately high amount of total revenue (Pareto Principle validation).
* **Churn Risks:** The "At Risk" segment shows high monetary history but low recency, indicating an urgent need for win-back campaigns (e.g., "We miss you" coupons).
* **Growth Potential:** The "Need Attention" group shows promise but lacks frequency; they are prime targets for loyalty program onboarding.

---

## 🚀 How to Run Locally

1.  **Clone the Repo:**
    ```bash
    git clone [https://github.com/Bheki0987/RFM-Customer-Lifetime-Value-Analysis.git](https://github.com/Bheki0987/RFM-Customer-Lifetime-Value-Analysis.git)
    ```
2.  **Explore the Code:**
    Open `rfm_analysis.ipynb` in Jupyter Notebook or VS Code to see the Python and SQL logic step-by-step.
3.  **View the Data:**
    The processed dataset is available as `rfm_segment.csv`.
4.  **Visualize:**
    Connect the CSV to Tableau (or open the link above) to replicate the visuals.

---

## 👤 Author

**Bheki Mogola**
*Data Analyst | Python & Tableau Enthusiast*

* 📧 **Email:** [bhekimogola123@gmail.com](mailto:bhekimogola123@gmail.com)
* 🔗 **LinkedIn:** [Bheki Mogola](https://www.linkedin.com/in/bheki-mogola-8481122b7/)
* 📈 **Tableau Portfolio:** [View my Vizzes](https://public.tableau.com/app/profile/bheki.mogola/vizzes)

---

## ℹ️ License
This project is open-source and licensed under the MIT License.
