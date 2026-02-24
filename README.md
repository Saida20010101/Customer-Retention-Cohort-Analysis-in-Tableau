# Customer-Retention-Cohort-Analysis-in-Tableau
This project focuses on analyzing customer loyalty and behavior over time using Cohort Analysis. By segmenting customers based on their first purchase date, I visualized the Retention Rate to understand how well the business retains its users across different quarters.
Key Insights
Segmented Behavior: Not all customers are the same; users acquired in 2021 Q1 showed a significantly higher retention rate (15.05%) compared to other cohorts.

Performance Benchmark: The heatmap reveals which specific periods had the most effective marketing campaigns or product updates based on customer stickiness.

Churn Identification: By calculating the elapsed quarters, I identified the exact points where customer drop-off (churn) is most prevalent, allowing for data-driven preventive strategies.

Technical Implementation (The "How-To")
To build this analysis, I utilized Advanced Tableau Techniques and specific calculation functions:

1. Defining Cohorts (LOD Expressions)
I used Level of Detail (LOD) expressions to "freeze" each customer's first-ever purchase date:


{ FIXED [Cust Id] : MIN([Order Date]) }
2. Time Intelligence (Elapsed Time)
To align all cohorts starting from "Quarter 0", I calculated the difference between the first purchase and subsequent orders:


DATEDIFF('quarter', [First Purchase Date], [Order Date])
3. Retention Rate Calculations
The retention percentage was calculated using Table Calculations:

Function: COUNTD([Cust Id]) to count unique customers per cell.

Calculation: Percent of Total computed along the table (Across) to normalize each row starting at 100%.
