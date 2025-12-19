# Cyclistic Bikeshare: SQL Data Engineering & Analysis
### Project Overview
This project analyzes over 5.8 million records of historical trip data from Cyclistic, a bike-share company in Chicago. The objective is to identify behavioral differences between annual members and casual riders to help design a marketing strategy aimed at converting casual riders into annual members.

### Technical SQL Process
1. ### Data Cleaning & Integrity.
* **Duplicate Removal**: Utilized **SELECT DISTINCT** to ensure data uniqueness across all monthly datasets.   

* **Schema Standardization**: Standardized disparate columns, such as **casting end_station_id** to STRING to ensure compatibility during table merging.   

* **Handling Nulls**: Implemented strict **IS NOT NULL** filters across 9 key attributes to maintain data quality.   

2. ### Data Engineering & Transformation.
* **Ride Length Calculation**: Created a custom temporal feature using **TIMESTAMP_DIFF** to determine exact trip durations.
  
* **Outlier Filtering**: Developed logic to exclude "noise" data, specifically rides shorter than 60 seconds or longer than 24 hours.   

* **Temporal Extraction**: Used **FORMAT_DATE** to extract the week_day and month from timestamps for seasonal and weekly trend analysis.   

* **Large-Scale Consolidation**: Executed a massive **UNION ALL** operation to unify 12 individual monthly tables into a single master dataset for year-over-year analysis.   

3. ### Data Aggregation & Analysis.
* **Numerical Transformation**: Converted ride lengths into a total **ride_length_seconds** field to allow for advanced mathematical aggregation like average and max trip durations.   

* **Usage Distribution**: Calculated the total rider volume to compare the market share of members versus casual riders.   

* **Behavioral Trends**: Created comparative queries to analyze average trip lengths by month and day of the week for both rider types.   

### Key Insights from Analysis.

* **Duration Patterns**: Casual riders consistently exhibit significantly longer average ride durations compared to members, particularly on weekends.   

* **Station Traffic**: Identified the top-performing start and end stations for both groups, revealing distinct geographic preferences for casual recreational use versus member commuting.   

* **Seasonal Trends**: Analyzed ridership volume by month to identify peak seasons for casual ridership, providing a timeline for marketing campaigns.
 
## Final Conclusion & Strategic Recommendations
The analysis reveals clear behavioral distinctions between the two groups. **Annual Members** use Cyclistic primarily as a reliable commuting tool with stable, shorter trips throughout the work week . In contrast, **Casual Riders** utilize the service for leisure, evidenced by significantly longer ride durations and increased activity on weekends and during summer months.

### Strategic Marketing Recommendations

**Weekend-Only Memberships**: Introduce a "Weekend Pass" or a discounted weekend-only annual membership specifically targeting the casual riders who currently dominate weekend traffic.  

**Seasonal Conversion Campaigns**: Launch high-intensity digital marketing campaigns at top-performing casual stations during the peak summer months when casual volume is at its highest. 

**Commuter Incentives**: Provide casual riders with "Commuter Trial" memberships during the week to demonstrate the efficiency of using Cyclistic for daily transportation.  

**Targeted Station Advertisements**: Prioritize ad placement and physical marketing at the specific "start stations" most frequented by casual riders, as identified in the high-traffic query results 

### Data Visualization

The following visualizations were created in Tableau to identify key differences between casual riders and annual members.

**Ridership Trends**: Casual ridership peaks significantly during summer months and on weekends, suggesting recreational use.

**Trip Duration**: While members have a higher volume of rides, casual riders spend significantly more time per trip.

**Preference**: Both groups show a strong preference for classic docked bikes over electric options.

### **Interactive Analysis**
[![Cyclistic Bike-Share Tableau Dashboard](https://raw.githubusercontent.com/NnekaE/Cyclistic-Bikeshare-SQL-Analysis./main/dashboard_screenshot.png)](https://public.tableau.com/app/profile/nneka.ekwemuka/viz/DivvyTripdata_17002928690700/Dashboard2)

*Click the image above to view the full interactive dashboard.*
