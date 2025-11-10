# RFM Customer Lifetime Value Analysis

## 📖 What is This Project About?

This project demonstrates a complete **data analytics pipeline** for customer segmentation using **RFM (Recency, Frequency, Monetary) Analysis**. It analyzes over 500,000 retail transactions to identify customer behavior patterns and segment customers into actionable groups such as Champions, Loyal Customers, At Risk, and Lost customers.

The project showcases:
- **Data Analysis Skills**: Data cleaning, transformation, and statistical analysis using Python and SQL
- **Customer Analytics**: RFM methodology to quantify customer value and engagement
- **Data Visualization**: Interactive Tableau dashboard for business intelligence
- **End-to-End Pipeline**: From raw data to actionable insights ready for business decisions

### What is RFM Analysis?
RFM is a proven marketing analysis technique that segments customers based on three key metrics:
- **Recency (R)**: How recently did the customer make a purchase?
- **Frequency (F)**: How often do they purchase?
- **Monetary (M)**: How much money do they spend?

By scoring customers on these dimensions, businesses can identify their most valuable customers, detect churn risk early, and tailor marketing strategies for maximum ROI.

## 📈 Project Objective
To help businesses identify high-value, loyal, or at-risk customers using the RFM strategy, and visualize the findings in an executive-ready interactive dashboard for data-driven decision-making.

## ⚙️ Tools & Technologies Used
- **Python**: Data cleaning, transformation, and RFM calculation
  - `pandas`: Data manipulation and analysis
  - `sqlite3`: SQL database operations
- **SQLite**: SQL-based querying and data transformation
- **Excel**: Initial data inspection and validation
- **Tableau Public**: Interactive data visualization and dashboard creation
- **Jupyter Notebook**: Interactive development environment for analysis

## 📄 Dataset
- **Source:** [Online Retail Dataset (UCI Machine Learning Repository)](https://archive.ics.uci.edu/dataset/352/online+retail)
- Size: 500,000+ transactions
- Fields: Invoice No, Stock Code, Description, Quantity, Invoice Date, Unit Price, Customer ID, Country

## 🔄 Data Pipeline Summary

### 1. Data Cleaning & Preparation
- Handled malformed delimiters (commas inside text fields)
- Standardized column names (removed spaces, converted to lowercase)
- Removed rows with missing `CustomerID` values
- Converted `InvoiceDate` to proper datetime format
- Validated data types for all columns (int, float, datetime, string)

### 2. Database Creation (SQLite)
- Exported cleaned data to SQLite database (`retail.db`)
- Created `transactions` table with 541,910 records
- Optimized for SQL-based aggregation and analysis

### 3. RFM Calculation (SQL + Python)
- **Recency**: Days since last purchase (calculated from reference date: 2011-12-10)
- **Frequency**: Count of distinct invoices per customer
- **Monetary**: Total revenue per customer (Quantity × Price)
- Filtered out customers with zero or negative monetary values

### 4. Scoring & Segmentation (Python)
- Created quartile-based scores (1-4) for R, F, and M metrics
  - **R_score**: Lower recency → Higher score (4 = most recent)
  - **F_score**: Higher frequency → Higher score (4 = most frequent)
  - **M_score**: Higher monetary → Higher score (4 = highest spend)
- Combined into `RFM_Score` (e.g., "444" = Champion)
- Mapped RFM scores to business segments:
  - Champions
  - Loyal Customers
  - At Risk
  - Lost
  - Need More Attention
  - Others

### 5. Export & Visualization (Tableau)
- Exported final dataset as `rfm_segment.csv`
- Uploaded to Tableau Public for interactive visualization
- Created multi-dimensional dashboard with filters and KPIs


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
  - Created interactive KPIs to show Total Revenue, No of Customers and Total RFM Score

▶ **View it live:** [Tableau Public Dashboard (Bheki Mogola)](https://public.tableau.com/views/CustomerLifetimeValueAnalysisVisualization/InteractiveDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## 🔍 Key Insights & Business Value

### Customer Segmentation Results:
The analysis identifies distinct customer segments with specific characteristics:

- **Champions** (R=4, F=4, M=4): Top-tier customers with recent, frequent, high-value purchases
  - **Action**: Retain with VIP programs, exclusive offers, and loyalty rewards
  
- **Loyal Customers** (F≥4): Regular customers who purchase frequently
  - **Action**: Upsell premium products and encourage referrals
  
- **At Risk** (R≤2, F≥3): Previously engaged customers showing signs of churn
  - **Action**: Re-engage with targeted campaigns and personalized offers
  
- **Lost Customers** (R=1, F≤2, M≤2): Inactive customers who haven't returned
  - **Action**: Win-back campaigns with special incentives
  
- **Need More Attention** (R=2-3, F≤3): Moderate customers who need nurturing
  - **Action**: Increase engagement through targeted marketing

### Business Impact:
- **Identify** the top 20% of customers generating 80% of revenue
- **Reduce churn** by proactively targeting at-risk segments
- **Optimize marketing spend** by focusing resources on high-value segments
- **Improve customer lifetime value** through data-driven retention strategies

## 📁 Project Structure
```
RFM-Customer-Lifetime-Value-Analysis/
├── Customer Lifetime Value Analysis.ipynb  # Main analysis notebook
├── README.md                                # Project documentation
├── retail database.zip                      # Source dataset (zipped)
├── rfm_segment.csv                          # Generated output for Tableau
├── RFM Customer Lifetime Value Analysis Presentation.pptx  # Project presentation
├── Dataset Screenshort.png                  # Dataset preview
├── Interactive Dashboard screenshot.png     # Dashboard preview
└── Jupiter Notebook Screenshort.png         # Notebook preview
```

## 🛠️ Prerequisites & Dependencies

### Required Software:
- **Python 3.7+** (Anaconda distribution recommended)
- **Jupyter Notebook** or JupyterLab
- **Tableau Public** (for dashboard visualization)
- **Excel** (for initial data inspection, optional)

### Python Libraries:
```python
pandas         # Data manipulation and analysis
sqlite3        # SQL database operations (included in Python standard library)
```

### Installation:
```bash
# Install required Python packages
pip install pandas

# Or if using Anaconda:
conda install pandas
```

## 🚀 How to Reproduce This Project

### Step 1: Clone the Repository
```bash
git clone https://github.com/Bheki0987/RFM-Customer-Lifetime-Value-Analysis.git
cd RFM-Customer-Lifetime-Value-Analysis
```

### Step 2: Extract and Prepare the Dataset
1. Unzip `retail database.zip` to access the Excel file `online_retail_II.xlsx`
2. The dataset contains 500,000+ transactions from 2010-2011

### Step 3: Run the Analysis
1. Open Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Open `Customer Lifetime Value Analysis.ipynb`
3. Run all cells sequentially to:
   - Load and clean the data
   - Create SQLite database
   - Calculate RFM metrics
   - Generate customer segments
   - Export `rfm_segment.csv`

### Step 4: Visualize in Tableau
1. Download and install [Tableau Public](https://public.tableau.com/)
2. Open Tableau Public
3. Connect to `rfm_segment.csv`
4. Build your dashboard or import the existing design
5. Publish to Tableau Public

### Step 5: Explore the Interactive Dashboard
View the live dashboard here: [Tableau Public Dashboard](https://public.tableau.com/views/CustomerLifetimeValueAnalysisVisualization/InteractiveDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## 🚀 Future Enhancements & Roadmap
- **Predictive Analytics**: Add customer Lifetime Value (CLV) prediction using machine learning
- **Cohort Analysis**: Track customer behavior over time to identify trends
- **Churn Prediction**: Build ML models to predict which customers are likely to churn
- **Automated Pipeline**: Schedule monthly RFM updates using Apache Airflow or similar tools
- **Real-time Dashboard**: Connect Tableau to live database for real-time insights
- **A/B Testing Framework**: Test different retention strategies across segments

## 📢 Author
- Bheki Mogola
- 📧 bhekimogola123@gmail.com
- **👤 LinkedIn:** [Bheki Mogola](https://www.linkedin.com/in/bheki-mogola-8481122b7/)
- **📈 Tableau Public:** [Bheki Mogola](https://public.tableau.com/app/profile/bheki.mogola/vizzes)

## ℹ️ License
This project is licensed under the MIT License.
