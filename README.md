# OLA-Analytics-dashboard

# Ola Ride-Booking End-to-End Performance Analysis

## Project Overview
This project presents an end-to-end data analytics solution analyzing Ola's ride-booking data over a 30-day period (July 1st, 2024 to July 30th, 2024). Moving beyond basic visualization, this project demonstrates a complete data pipeline: extracting and auditing raw data using **SQL**, cleaning and validating anomalies in **Microsoft Excel**, and building a highly interactive, enterprise-grade executive dashboard in **Power BI**. 

The ultimate goal of this analysis is to diagnose operational bottlenecks (such as high cancellation rates), evaluate revenue distribution channels, map vehicle segment performance, and provide actionable, data-driven recommendations to maximize ride success rates.

1. **Exploration & Querying (SQL):** Conducted initial data audits to inspect null counts, isolate extreme outliers in ride distances, and understand table schemas.
2. **Data Cleaning & Preparation (Microsoft Excel):** Handled structural anomalies, formatted inconsistencies, and removed duplicates. Used Excel functions to verify text normalization (e.g., standardizing text strings for cancellation reasons) before visualization.
3. **Data Modeling & Visualization (Power BI):** Developed a dynamic star-schema data model, engineered tailored DAX calculations, and built an interactive user interface featuring custom navigation panel elements.

## Technical Deep Dive & Tooling

### 1. SQL Data Exploration
Before creating any charts, I executed targeted SQL queries against the raw database to gain a deep understanding of the transactional data layer. Key exploratory tasks included:
* **Ride Status Volumes:** Evaluated the macro-ratio of successful rides against cancellations to check underlying data integrity.
* **Driver vs. Customer Cancellations:** Segmented categorical cancellation data to establish primary keys for downstream dimension tables.
* **Outlier Detection:** Queried minimum and maximum travel distances to flag and filter out faulty GPS tracking anomalies (e.g., negative distances or extreme impossibilities).

### 2. Excel Data Cleaning Workflow
To guarantee a "single source of truth" before visualization, Excel was utilized to process and refine the data:
* **Data Formatting:** Standardized date formats to a uniform `DD-MM-YYYY` schema and verified numerical values for financial data types.
* **Handling Missing Values:** Audited and resolved empty data cells within the customer and driver rating columns, converting blanks into reportable formats without skewing baseline averages.
* **Text Standardization:** Utilized text functions and column filters to eliminate typos, stray spaces, or inconsistent naming conventions in categorical attributes like payment methods.

### 3. Power BI Modeling & DAX
* **Data Modeling:** Established relationships to cleanly separate transactional booking facts from date dimensions and category filters.
* **DAX (Data Analysis Expressions):** Engineered custom measures for tracking complex KPIs like `Success Booking Value`, `Cancellation Rate %`, and moving averages for ride volume.
* **UI/UX Design:** Implemented a dark/light contrasted left navigation panel utilizing bookmarks to allow seamless page-to-page transitions resembling an actual enterprise software application.

## 📊 Key Insights & Dashboard Architecture

The dashboard is structured into 5 specialized modules for dynamic, deep-dive exploration:

### Module 1: Executive Summary / Overall Performance
* **Total Bookings:** Managed a volume of **40.54K** bookings within the month, generating a **Total Booking Value of 14M**.
* **Booking Status Breakdown:** Successfully fulfilled **62.18% (25.21K)** of total bookings. The remaining volume consists of cancellations by drivers, cancellations by customers, and cases where a driver was not found.
* **Daily Ride Volume:** Tracks daily operational volatility, highlighting recurring peaks and valleys in customer demand over the 30-day timeline.
* *Visual Reference:* `Snapshot of page 5.png`

### Module 2: Vehicle Type Breakdown
* Evaluates metrics across **7 distinct vehicle segments** (Prime Sedan, Prime SUV, Prime Plus, Mini, Auto, Bike, and E-Bike).
* Tracks consistent transactional performance across most four-wheeler and two-wheeler categories, averaging around **3M in total booking value** and **2M in successful booking value** per segment.
* Highlights differences in average travel distance, showing that conventional formats maintain roughly a **25 km average distance**, while the Auto segment operates closer to a shorter **10 km trip average**.
* *Visual Reference:* `Snapshot of page1.png`

### Module 3: Revenue Analysis
* **Preferred Payment Methods:** Cash is the dominant revenue channel bringing in **7.5M**, closely followed by UPI at **5.6M**. Digital options like Credit Cards (0.5M) and Debit Cards (0.1M) represent minor shares.
* **Daily Revenue Distribution:** Demonstrates stable day-to-day financial health, consistently averaging between **15K to 20K+** in daily collections.
* **Customer Leaderboard:** Isolates high-value customers by order value (e.g., top customers surpassing 3,700 to 4,400 in booking value).
* *Visual Reference:* `Snapshot of page 2.png`

### Module 4: Cancellation Deep-Dive
* **Overall Cancellation Rate:** Stands at a significant **27.85%**, representing **7.212K** dropped bookings.
* **Customer Cancellations:** The top driver of customer-side cancellations is **"Driver is not moving to pickup location" (29.88%)**, followed closely by **"Driver asked to cancel" (25.94%)**.
* **Driver Cancellations:** The primary reasons drivers cancel are **"Personal & Car-related issues" (34.66%)** and **"Customer related issues" (29.45%)**.
* *Visual Reference:* `Snapshot of page 3.png`

### Module 5: Ratings Evaluation
* **System-wide Trust:** Scores remain highly stable across all ride classes.
* **Driver Ratings:** Average between **3.98 and 4.02**, showing strong service quality.
* **Customer Ratings:** Range tightly between **3.98 and 4.01**, demonstrating mutual satisfaction metrics between the supply and demand sides.
* *Visual Reference:* `Snapshot of page 4.png`

##  Data-Driven Business Recommendations

1. **Reduce Customer Pickup Pain Points:** Since nearly 30% of customer cancellations happen because a driver isn't moving, operational teams should optimize matching algorithms or tighten ETAs to ensure active driver movement toward pickup locations.
2. **Optimize Digital Wallet Incentives:** UPI and Cash make up the overwhelming majority of transactions. Introducing credit/debit card promotional cashbacks could diversify payment channels and reduce cash-handling friction for drivers.
3. **Address Driver Cancellation Drivers:** Over a third of driver cancellations are linked to personal/car issues. Introducing flexible vehicle maintenance scheduling or local fleet support hubs could lower these operational drops.

## Skills Showcase
* **SQL:** Database Querying, Data Auditing, Exploratory Data Analysis (EDA).
* **Excel:** Data Formatting, Text Normalization, Quality Verification.
* **Power BI Desktop:** Star Schema Data Modeling, Advanced DAX Measures, UX/UI Layout Design, Interactive Bookmarks.
