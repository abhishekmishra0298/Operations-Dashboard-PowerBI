# Operations-Dashboard-PowerBI
Interactive Power BI dashboard for RCM Operations tracking with automated web data extraction using Power Query

📊 RCM Operations Dashboard — Power BI
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
---
📌 Project Overview
An end-to-end Power BI solution that automates data extraction from an internal web-based RCM (Remote Change Management) system and transforms raw HTML data into actionable operational insights.
This dashboard enables real-time tracking of activities, performance monitoring, and trend analysis—eliminating manual reporting and improving decision-making.
> ⚠️ **Note:** All sensitive data (customer names, site details, serial numbers, internal URLs) have been anonymized or removed.
---
🖼️ Dashboard Preview
📊 Overview
![Overview](screenshots/overview.png)
📋 Activity Details
![Activity Details](screenshots/activity_details.png)
👥 Team Performance
![Team Performance](screenshots/team_performance.png)
📈 Trend Analysis
![Trend Analysis](screenshots/trend_analysis.png)
---
🌟 Key Features
🔄 Automated Data Extraction
Dynamic data extraction using Power Query (M Language)
Parameterized date logic to fetch data for any time range
HTML table parsing via `Web.Contents()` and `Web.Page()`
Robust fallback handling for missing/invalid data sources
---
📊 Interactive 4-Page Dashboard
Page	Description
📊 Overview	KPIs, daily trends, status distribution, top activity types
📋 Activity Details	Drill-down table, monthly status matrix, slicers
👥 Team Performance	Contact-level insights, workload distribution, ranking
📈 Trend Analysis	Weekly patterns, weekday heatmap, completion trends
---
📅 Custom Fiscal Calendar
Fiscal Year starting February
Weeks starting from Saturday
Custom calculations:
Fiscal Year / Quarter / Month
FY Week & Week Number
Weekday sorting (Sat → Fri)
---
🎨 Data Visualization
Fully interactive cross-filtering
Conditional formatting (colors, icons, data bars)
Heatmaps for pattern analysis
KPI indicators with target benchmarks
Drill-down capabilities for detailed insights
---
⚙️ How It Works
Generate dynamic date list using Power Query
Invoke custom function to extract HTML data per date
Parse and consolidate multiple tables
Clean and transform scraped data
Build star schema data model
Create DAX measures for KPIs and analytics
Visualize insights via Power BI dashboard
---
🏗️ Architecture
🔄 Data Pipeline
```
RCM Web Tool (HTML)
        ↓
Power Query (Extraction & Transformation)
        ↓
Data Model (Star Schema)
        ↓
Power BI Dashboard (Visualization)
```
---
📐 DAX Measures (Key Examples)
```dax
Total Activities = COUNTA('Data Domain RCM Data'[RCM Id])

Total Completed =
CALCULATE(
    COUNTA('Data Domain RCM Data'[RCM Id]),
    'Data Domain RCM Data'[Status] IN {
        "Complete",
        "TC - Complete And Returned"
    }
)

Completion Rate =
DIVIDE([Total Completed], [Total Activities], 0)
```
---
🔄 Data Refresh
Requires access to internal network/VPN
Data refresh is triggered manually or via scheduled refresh (if deployed)
Dependent on availability of the RCM system
---
⚠️ Limitations
`.pbix` file cannot be shared publicly due to internal data source dependencies
Data extraction depends on authenticated internal systems
Sample dataset not included due to data confidentiality
---
📈 Impact
⏱️ Saved 2+ hours/day of manual tracking effort
📊 Enabled near real-time reporting
👁️ Improved visibility via centralized dashboard
👥 Introduced team performance tracking with KPIs
📉 Automated trend analysis (daily & weekly)
---
🛠️ Tools & Technologies
Power BI, DAX, Power Query, Data Analytics, Dashboard, Business Intelligence
---
👤 Author
Abhishek Mishra  
Senior Project Engineer  
📍 Hyderabad, India
🔗 https://www.linkedin.com/in/abhimishra936  
📧 abhishek.mishra0298@gmail.com
---
⭐ Final Note
This project demonstrates end-to-end ownership of a BI solution, from data extraction and transformation to modeling and visualization—focused on solving real-world operational challenges.
