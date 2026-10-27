# Telecommunications ChurnQuest

This project is a business analytics and data-driven churn analysis case study focused on a telecommunications customer dataset. The goal is to identify why customers leave, measure churn behavior, segment high-risk groups, and provide data-backed recommendations to reduce customer attrition.

The analysis is built around a telecom dataset with 4,250 customers and uses Microsoft Excel as the primary tool for data exploration, segmentation, summary statistics, and dashboard creation.

## Dashboard

<img width="1821" height="732" alt="Telecommunications churn dashboard" src="https://github.com/user-attachments/assets/19208d38-e480-470b-8f59-47a4ad322b23" />

## Project Overview

Customer churn is one of the most important metrics for telecom companies because retaining existing customers is usually more cost-effective than acquiring new ones. In this project, I analyzed customer behavior to understand:

- How many customers churned
- Which customer groups are most likely to leave
- Which features or behaviors are associated with churn
- How different usage patterns and plan types influence retention
- What actions the business can take to reduce churn

The dataset used for this project is based on a telecom churn scenario inspired by the Kaggle customer churn prediction dataset, and the workbook was prepared as a case study for business and data analysis.

## Project Requirements

This project required the following analysis tasks:

- Clean and validate the customer dataset
- Measure churn rate and compare churned vs retained customers
- Analyze relationship between churn and plan type, service usage, and calls
- Segment customers based on behavior and usage profiles
- Create summary tables, charts, and a dashboard in Excel
- Interpret business insights and convert them into actionable recommendations

Key business questions addressed:

- What is the overall churn rate?
- Do international plan subscribers churn more than non-subscribers?
- Are customers with more service calls more likely to churn?
- Do high-usage customers have higher churn risk?
- Are some customer clusters more prone to churn than others?

## Tools and Technologies Used

- Microsoft Excel
  - Data analysis and summary calculations
  - Formulas such as COUNTIF, AVERAGEIF, CORREL, and conditional logic
  - PivotTables for segmenting and comparing churn groups
  - Charts and dashboard visuals
  - Data grouping and customer segmentation
  - Descriptive and comparative analysis

- Excel-based analytics features
  - Pivot tables
  - Data filtering and slicing
  - Statistical measures
  - Visual summaries and dashboard presentation

## Dataset Information

- Workbook: `Telecommunications_Churn_Analysis.xlsx`
- Total records: 4,250 customers
- Source: Kaggle customer churn dataset (case-study context)
- Main variables analyzed:
  - Churn status
  - Account length
  - International plan
  - Voicemail plan
  - Customer service calls
  - Day / evening / night usage and charges
  - Area code
  - Cluster-based customer segments

## Challenges Faced

A few important challenges were present during the project:

1. Data limitations
   - The dataset did not include date-based time series information, which prevented seasonality and temporal trend analysis.
   - There were no detailed reasons for customer-service calls, so call motives could not be tied directly to churn causes.

2. Interpreting associations vs. causation
   - Some patterns clearly suggest risk factors, but the data does not prove that one variable directly caused churn.
   - Example: international plan membership is strongly associated with churn, but it may also reflect a combination of customer behavior and pricing factors.

3. Segmentation complexity
   - Customer usage patterns differ across groups, so identifying which variables matter most required careful comparison and interpretation.

4. Dashboard design and communication
   - Turning raw statistics into a readable business story required proper chart selection, clean labeling, and meaningful summary tables.

## Key Insights and Findings

The analysis revealed several meaningful patterns:

- Overall churn rate: 14.07%
- International-plan subscribers had a much higher churn rate than non-subscribers
- Customers with more than three service calls had a much higher churn risk
- High-usage evening customers showed increasing churn risk
- One customer cluster had a significantly higher churn rate than the others
- Churn was strongly associated with customer dissatisfaction signals, especially service interactions and plan fit

Important findings:

- International plan customers churned at a much higher rate than non-customers, suggesting a need to review plan value and user experience.
- Customers contacting support more than three times were much more likely to leave.
- Service issues, plan dissatisfaction, and usage mismatches appear to be major churn drivers.
- The high-usage segment is a high-risk group and should be prioritized for retention strategies.

## Business Implications

The results suggest that customer churn is not random. It is influenced by several operational and behavioral factors, including:

- low satisfaction with service experience
- mismatch between customer expectations and plan features
- high usage intensity with poor plan fit
- issues related to international calling and billing perception

This makes churn prevention a strategic business problem rather than just a reporting task.

## Recommendations for Improvement

Based on the findings, the following improvements are recommended:

1. Improve customer-support follow-up
   - Investigate why customers contact support repeatedly
   - Train customer service teams to resolve issues faster and more effectively
   - Use proactive outreach for customers showing repeated service calls

2. Review international plan design
   - Assess pricing, customer benefit, and satisfaction among international plan users
   - Offer better plan matching or personalized recommendations for heavy international users

3. Focus retention efforts on high-risk segments
   - Prioritize customers in the cluster with the highest churn rate
   - Launch win-back or retention campaigns for at-risk high-usage customers

4. Improve data collection for deeper analysis
   - Add date/time tracking
   - Track call reasons and complaint categories
   - Capture revenue and retention outcomes to calculate real business impact

5. Build predictive churn models in the future
   - Use logistic regression or machine learning to predict churn probabilities
   - Combine descriptive analysis with a forecasting model for proactive interventions

6. Strengthen customer communication and plan guidance
   - Provide better onboarding and plan recommendation for customers with heavy usage patterns
   - Clarify costs, benefits, and value of telecom plans

## Lessons Learned

This project helped build a practical understanding of how data analysis can support business decision-making. Key lessons include:

- Customer churn analysis is valuable when it connects data patterns to customer experience and business operations
- Excel can be highly effective for exploratory analysis and dashboarding without requiring advanced programming tools
- Descriptive analytics is useful for identifying risk signals, but deeper insights require richer data and predictive modeling
- Clear communication of findings is essential for turning analysis into action

## Project Files

- `Telecommunications_Churn_Analysis.xlsx` — main workbook containing the dataset, tables, charts, and analysis
- `DACS07 - Telecommunications ChurnQuest.pdf` — supporting case-study document
- `README.md` — project summary and insights
- `screenshots/` — images related to the dashboard and visuals

## Conclusion

This project demonstrates how a structured Excel-based analysis can highlight churn risks, reveal business patterns, and support retention strategies. Although the dataset has limitations, it still provides strong evidence that churn is tied to customer experience, international plan behavior, service-call intensity, and usage patterns.

The project is a strong example of how business analytics can help a telecom company understand customer behavior and take preventive action before churn becomes a larger financial problem.

---

This repository is suitable for academic, portfolio, and business-analysis purposes and can be expanded in the future with predictive modeling, customer segmentation, and dashboard automation.
