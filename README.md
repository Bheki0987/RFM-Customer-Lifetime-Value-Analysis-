# RFM-Customer-Lifetime-Value-Analysis-

This project performs RFM (Recency, Frequency, Monetary) analysis on retail transaction data to segment customers based on their purchase behavior. The final result is a fully interactive and modern Tableau dashboard that reveals actionable customer insights.

## 📈 Project Objective
To help businesses identify high-value, loyal, or lost customers using the RFM strategy, and visualize the findings in an executive-ready dashboard for stakeholder decision-making.

## ⚙️ Tools & Technologies Used
- Python: Data Cleaning, Data analysis and RFM calculation
- SQLite: SQL-based querying and data transformation
- Excel: Initial data clean up
- Tableau Public: Final data visualization

## 📄 Dataset
- **Source:** [Online Retail Dataset (UCI Machine Learning Repository)](https://archive.ics.uci.edu/dataset/352/online+retail)
- Size: 500,000+ transactions
- Fields: Invoice No, Stock Code, Description, Quantity, Invoice Date, Unit Price, Customer ID, Country

## 🔄 Data Pipeline Summary
1. Data Cleaning
 - Handled malformed delimiters (commas inside text)
 - Cleaned the columns by removing spaces
 - Droped a row with missing customerID
 - Converted Date(invoicedate) Column to Datetime
 - Doubled check to ensure correct data types

2. Export to SQLite
 - Converted cleaned Excel data to a structured SQLite table
 - Ran SQL queries to compute Recency, Frequency, and Monetary values

3. RFM Calculation in Python
 - Created R_score, F_score, M_score (scale 1 to 4)
 - Combined into one RFM_Score
 - Mapped customers to realistic segments:
   - Champions
   - Loyal Customers
   - At Risk
   - Lost
   - Need More Attention, etc.

4. Export to Tableau
 - Final dataset saved as rfm_segment.csv
 - Uploaded into Tableau Public for visualization

## 🌎 Tableau Dashboard Overview
The dashboard offers:
- Customer Segment Distribution
  - Pie chart showing each customer segment distribution

- High-Value Customer Matrix
  - Heatmap of RFM scores by Recency & Monetary

- RFM Score vs Revenue
  - Bubble chart highlighting high-spending segments

- Total Revenue by Segment
  - Bar chart showing total monetary value per segment

- Filters
  - Interactive filters for recency, frequency, and segment

▶ **View it live:** [Tableau Public Dashboard (Bheki Mogola)](https://public.tableau.com/views/CustomerLifetimeValueAnalysisVisualization/InteractiveDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## 🔍 Key Insights
- Champions are contributing the highest revenue and should be retained with loyalty programs.
- At Risk customers show declining engagement and may need reactivation strategies.
- Lost customers present potential for win-back campaigns.
- Need More Attention could be upsold or nurtured for future value.

## 🚀 How to Reproduce
1. Clone this repository:
```
git clone https://github.com/Bheki0987/RFM-Customer-Lifetime-Value-Analysis.git
```
2. Open rfm_analysis.ipynb to explore the full analysis.
3. Upload rfm_segment.csv into Tableau Public.
4. Customize and publish your dashboard.

## 🚀 Possible Enhancements
- Add cohort and churn analysis
- Automate monthly updates
- Add customer Lifetime Value (CLTV) prediction

## 📢 Author
- Bheki Mogola
- 📧 bhekimogola123@gmail.com
- **👤 LinkedIn:** [Bheki Mogola](https://www.linkedin.com/in/bheki-mogola-8481122b7/)
- **📈 Tableau Public:** [Bheki Mogola](https://public.tableau.com/app/profile/bheki.mogola/vizzes)

## ℹ️ License
This project is licensed under the MIT License.
