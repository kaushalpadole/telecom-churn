# Telecommunications ChurnQuest — Complete Excel Case Study Answers

## Project overview

This project uses Microsoft Excel to analyze customer churn in a telecommunications dataset. The case-study scenario is framed around Airtel. The goal is to describe churn, compare customer groups, identify patterns in usage and plan subscriptions, and suggest areas for further retention investigation.

**Workbook:** `Telecommunications_Churn_Analysis.xlsx`  
**Dataset size:** 4,250 customers  
**Tools:** Excel formulas, PivotTables, descriptive statistics, correlation, segmentation, charts, and cluster analysis  
**Dataset source named in the case study:** [Kaggle — Customer Churn Prediction 2020](https://www.kaggle.com/competitions/customer-churn-prediction-2020/data)

> **Interpretation note:** These are descriptive findings from this dataset. Associations do not prove that a characteristic causes churn. Results below follow the calculations already recorded in the workbook. Where a requested analysis was not completed or the necessary fields are absent, that is stated explicitly rather than inventing a result.

---

# 1. Basic-Level Questions

## Q1. How many customers churned, and what proportion of the customer base is that?

**Answer**
- Total customers: **4,250**
- Churned (`yes`): **598**, or **14.07%**
- Retained (`no`): **3,652**, or **85.93%**

**Explanation:** Divide the churned-customer count by the total customer count: 598 ÷ 4,250 = 14.07%. This is the baseline churn rate for comparisons with other customer groups.

**Excel approach:** `COUNTIF` counts the `yes` and `no` values in the `churn` column; divide each count by the total number of customers.

## Q2. What is the average account length for churned versus retained customers? Does tenure influence churn?

**Answer**
- Average account length for retained customers: **99.92 months**
- Average account length for churned customers: **102.14 months**
- Difference: approximately **2.21 months**
- Correlation between account length and numeric churn indicator: approximately **0.0194**

**Explanation:** Churned customers have a slightly higher average account length in this dataset, so the averages do not support the idea that churned customers are generally newer. The correlation is very weak, indicating little linear relationship between account length and churn. This does not establish a causal effect.

**Excel approach:** Use `AVERAGEIF` to calculate the mean account length separately for `churn = no` and `churn = yes`; use `CORREL` for the numeric churn indicator and account length.

## Q3. How does an international plan relate to churn?

**Answer**
- No international plan: **431 of 3,854 churned — 11.18%**
- International plan: **167 of 396 churned — 42.17%**

**Explanation:** The observed churn rate for international-plan subscribers is about 31 percentage points higher. This is a strong association in the workbook and suggests that the international-plan experience, pricing, or needs of these customers deserve further investigation. The comparison alone does not prove the plan causes churn.

## Q4. Is there a difference in customer-service calls between churned and retained customers?

**Answer**
- Retained customers: average **1.44** service calls
- Churned customers: average **2.28** service calls
- Difference: approximately **0.83** calls

**Explanation:** Churned customers contact customer service more often on average. Repeated calls may signal unresolved issues or dissatisfaction, but the dataset does not include the reason for each call.

## Q5. Do day, evening, and night call charges differ between churned and retained customers?

**Answer**

| Average charge | Retained | Churned | Difference (churned minus retained) |
|---|---:|---:|---:|
| Day | 29.84 | 35.53 | 5.69 |
| Evening | 16.88 | 17.85 | 0.97 |
| Night | 8.98 | 9.29 | 0.31 |

**Explanation:** The largest difference is in average daytime charges. Evening and night charge differences are smaller. These are descriptive comparisons; no statistical significance test is recorded in the workbook, so the result should be described as a difference in averages, not as a statistically significant effect.

## Q6. What is the relationship between total day minutes and churn?

**Answer**
- Retained customers: average **175.56** day minutes
- Churned customers: average **208.99** day minutes
- Difference: **33.44** minutes

**Explanation:** Churned customers use more daytime minutes on average. This may be associated with plan fit, usage needs, or charges, but the comparison does not identify the cause.

## Q7. How does having a voicemail plan relate to churn rates?

**Answer**
- No voicemail plan: **516 of 3,138 churned — 16.44%**
- Voicemail plan: **82 of 1,112 churned — 7.37%**

**Explanation:** Customers with a voicemail plan have a lower observed churn rate in this dataset. This may indicate that the feature is valuable or that these customers differ in other ways. The analysis does not prove that voicemail itself reduces churn.

## Q8. Compare international minutes and charges for churned versus retained customers. Are higher values associated with churn?

**Answer**

| Average metric | Retained | Churned |
|---|---:|---:|
| International minutes | 10.19 | 10.63 |
| International charge | 2.75 | 2.87 |

**Explanation:** Churned customers have slightly higher average international minutes and charges. The differences are small compared with the much larger churn-rate gap observed between international-plan subscribers and non-subscribers. Usage and charges alone do not establish why customers churn.

## Q9. Is there a correlation between total day calls and churn?

**Answer:** The workbook reports a correlation of approximately **0.01164** between total day calls and the numeric churn indicator.

**Explanation:** This is a negligible positive correlation. In this dataset, the number of daytime calls has almost no linear relationship with churn status. Correlation does not establish causation.

## Q10. Compare average evening charges for churned and retained customers.

**Answer**
- Retained customers: **16.88**
- Churned customers: **17.85**
- Difference: **0.97**

**Explanation:** Churned customers have a higher average evening charge, but the difference is modest. The workbook does not record a statistical significance test, so this should not be described as statistically significant.

---

# 2. Medium-Level Questions

## Q1. Does any area code have a higher churn rate?

**Answer**

| Area code | Customers | Churned | Churn rate |
|---|---:|---:|---:|
| 408 | 1,086 | 152 | 14.00% |
| 415 | 2,108 | 287 | 13.61% |
| 510 | 1,056 | 159 | 15.06% |

**Explanation:** Area code 510 has the highest observed churn rate, at about 15.06%, while area code 415 has the lowest, at about 13.61%. The gap is modest; the area-code result alone cannot tell us whether the difference is caused by network quality, pricing, demographics, or other factors.

## Q2. How does the number of customer-service calls relate to churn at different thresholds?

**Answer**
- **3 or fewer calls:** 428 churned out of 3,915 customers — **10.93%**
- **More than 3 calls:** 170 churned out of 335 customers — **50.75%**

**Explanation:** The churn rate is much higher among customers with more than three service calls. This is one of the clearest risk patterns in the workbook. A useful follow-up would be to examine the reasons for repeated contacts and whether the underlying problems were resolved.

## Q3. Is account length correlated with churn, and are newer customers more likely to churn?

**Answer**
- Correlation: approximately **0.01938**
- Churn rate by account-length quartile in the workbook:
  - Q1: **12.78%**
  - Q2: **14.33%**
  - Q3: **15.85%**
  - Q4: **13.35%**

**Explanation:** The correlation is very weak. Churn rises across the first three quartiles and then falls in Q4, so there is no consistent monotonic pattern showing that the newest customers are necessarily most likely to churn. The quartile groups show variation, but tenure alone is not a strong churn indicator here.

## Q4. Among international-plan subscribers, how do high and low international charges relate to churn?

**Answer — international-plan subscribers only**
- Low international-charge group: **67 of 199 churned — 33.67%**
- High international-charge group: **100 of 197 churned — 50.76%**

**Explanation:** The high-charge group has a churn rate about 17.09 percentage points higher than the low-charge group. This suggests that high international charges may be a useful segment for further investigation. The analysis does not prove price is the cause, and other customer characteristics may differ between the groups.

## Q5. How do evening usage patterns relate to churn?

**Answer**

| Evening usage group | Customers | Churned | Churn rate |
|---|---:|---:|---:|
| Low | 1,031 | 109 | 10.57% |
| Medium | 2,138 | 298 | 13.94% |
| High | 1,081 | 191 | 17.67% |

**Explanation:** Churn rate increases from the low-usage group to the high-usage group. High evening usage is associated with a higher churn rate in this dataset. A pie chart of churned-customer counts can show how the 598 churned customers are distributed across groups, but a bar chart of churn rates is better for comparing each group's risk because the group sizes differ.

## Q6. What do the customer clusters show about churn?

**Answer**

| Cluster | Customers | Churned | Churn rate |
|---|---:|---:|---:|
| Cluster 1 | 649 | 66 | 10.17% |
| Cluster 2 | 2,957 | 313 | 10.59% |
| Cluster 3 | 644 | 219 | 34.01% |

**Average usage by cluster**

| Cluster | Day minutes | Evening minutes | Night minutes | International minutes |
|---|---:|---:|---:|---:|
| Cluster 1 | 140.33 | 160.78 | 162.64 | 8.03 |
| Cluster 2 | 179.75 | 200.68 | 200.03 | 10.31 |
| Cluster 3 | 222.86 | 237.53 | 240.98 | 12.26 |

**Explanation:** Cluster 3 has a 34.01% churn rate, much higher than the approximately 10% rates in Clusters 1 and 2. It also has the highest average usage across all four listed usage measures. This makes Cluster 3 a priority for further investigation. Cluster labels are identifiers, not inherently meaningful customer types; the usage averages help describe them.

## Q7. How does voicemail-plan status interact with voicemail-message volume and churn?

**Answer from the workbook's PivotTable**
- No voicemail plan: **516 of 3,138 churned — 16.44%**; message volume is shown as “Not Applicable.”
- Voicemail plan, **0 messages**: **0 of 1 customer — 0.00%**
- Voicemail plan, **1–16 messages**: **2 of 58 customers — 3.45%**
- Voicemail plan, **more than 16 messages**: **80 of 1,053 customers — 7.60%**

**Explanation:** The workbook's voicemail-plan groups show lower churn rates for customers with a voicemail plan than for customers without one. Among plan subscribers, the recorded churn rate is higher in the more-than-16-message group than in the 1–16-message group. The zero-message group has only one customer, so its 0% rate is not a reliable basis for a general conclusion. These are observed associations, not proof that voicemail usage changes churn.

## Q8. Is there a point where higher day minutes or charges lead to higher churn?

**Answer:** The workbook includes a scatter plot of total day minutes versus total day charges, separated by churn status. The plotted points follow a near-linear relationship.

**Explanation:** Day charges closely track day minutes in the dataset, so the chart mainly shows the pricing relationship between those two measures. It does not demonstrate a clear tipping point where higher usage causes churn. A stronger test of a churn threshold would require analyzing churn rates across day-minute or charge bands, ideally with additional statistical analysis.

## Q9. Does the number of international calls affect churn differently for customers with and without an international plan?

**Answer from the workbook's combined segmentation table**

| International plan | International-call group | Customers | Churned | Churn rate |
|---|---|---:|---:|---:|
| No | High | 641 | 67 | 10.45% |
| No | Low | 1,574 | 181 | 11.50% |
| No | Medium | 1,639 | 183 | 11.17% |
| Yes | High | 69 | 27 | 39.13% |
| Yes | Low | 165 | 97 | 58.79% |
| Yes | Medium | 162 | 43 | 26.54% |

**Explanation:** For customers without an international plan, churn rates are relatively similar across the three groups, around 10–12%. Among customers with an international plan, churn rates are much higher and vary by group; the low group has the highest rate in this table. Group sizes differ, so the percentages should be read with their counts. These categories are the workbook's existing groupings; they do not by themselves prove that call frequency causes churn.

## Q10. Do particular customer-service call reasons predict churn?

**Answer:** **Not answerable with the supplied dataset.**

**Explanation:** The dataset records the number of customer-service calls but does not include a category or reason for each call. It is therefore not possible to compare churn by reason (for example, billing, technical support, or complaints) from this workbook. Additional call-reason data would be needed.

---

# 3. Advanced-Level Questions

## Q1. Can a logistic-regression model predict churn likelihood?

**Answer:** **Not completed in the workbook.** No logistic-regression model, coefficients, model evaluation, or predicted probabilities are recorded in the completed analysis.

**Explanation:** Logistic regression would model churn as a binary outcome (`yes`/`no`) using available predictors such as international-plan status, customer-service call count, usage, charges, and account length. A valid answer would require fitting the model and evaluating it; the existing descriptive comparisons cannot be presented as a completed predictive model.

## Q2. What churn trends or seasonality appear over time?

**Answer:** **Cannot be analyzed from the supplied workbook because there is no date or time-period field.**

**Explanation:** Time-series analysis needs observations associated with dates or periods to examine changes, trends, or seasonality. The workbook gives customer-level records without a time series, so no monthly or seasonal churn pattern can be calculated.

## Q3. Which customer clusters are more prone to churn?

**Answer:** This question is addressed by the cluster analysis in Medium Q6:
- Cluster 1: **10.17%** churn
- Cluster 2: **10.59%** churn
- Cluster 3: **34.01%** churn

**Explanation:** Cluster 3 is the highest-risk segment in the completed workbook. It also has the highest average day, evening, night, and international minutes. This is a segmentation result, not a prediction for any individual customer. The workbook's cluster summary does not establish whether demographic variables were included in clustering.

## Q4. How do international-plan status and international-minute groups interact with churn?

**Answer from the workbook's interaction table**

| International plan | International-minute group | Customers | Churned | Churn rate |
|---|---|---:|---:|---:|
| No | Q1 | 988 | 105 | 10.6% |
| No | Q2 | 955 | 108 | 11.3% |
| No | Q3 | 956 | 107 | 11.2% |
| No | Q4 | 955 | 111 | 11.6% |
| Yes | Q1 | 89 | 29 | 32.6% |
| Yes | Q2 | 96 | 35 | 36.5% |
| Yes | Q3 | 112 | 32 | 28.6% |
| Yes | Q4 | 99 | 71 | 71.7% |

Overall, the workbook shows **11.18%** churn among customers without an international plan and **42.17%** among customers with one.

**Explanation:** Churn is relatively stable across the four international-minute groups among customers without an international plan. Among international-plan subscribers, the Q4 group has the highest churn rate at 71.7%. This suggests that the combination of international-plan status and international-minute group is worth investigating. The groups are not equal in size, and the table is a descriptive interaction analysis—not a fitted multivariable model or proof of causation.

## Q5. What is the economic impact of churn, including ARPU and customer lifetime value?

**Answer:** **Not calculated in the workbook.**

**Explanation:** The workbook does not provide the revenue inputs needed to estimate ARPU, lost revenue, or customer lifetime value. Call charges in the dataset should not automatically be treated as total account revenue or profit. To calculate economic impact responsibly, additional billing/revenue data and an explicit CLV method would be required.

---

# 4. Overall Conclusions

The workbook identifies several patterns worth investigating:

1. Overall churn is **14.07%**.
2. International-plan subscribers have a much higher observed churn rate (**42.17%**) than non-subscribers (**11.18%**).
3. Customers with more than three customer-service calls have a much higher churn rate (**50.75%**) than those with three or fewer (**10.93%**).
4. Customers with a voicemail plan have a lower observed churn rate (**7.37%**) than those without one (**16.44%**).
5. Churn rates rise across the workbook's low, medium, and high evening-usage groups (**10.57%, 13.94%, 17.67%**).
6. Cluster 3 is the highest-churn segment (**34.01%**) and has the highest average usage across day, evening, night, and international minutes.
7. The correlation between account length and churn is very weak (**about 0.0194**), as is the correlation between total day calls and churn (**about 0.0116**).

## Suggested business actions

- Investigate recurring customer-service contacts, especially for customers with more than three calls.
- Review the international-plan customer experience, pricing, and fit with customer needs.
- Investigate Cluster 3 to understand its high usage and high churn rate.
- Examine higher evening-usage customers for plan-fit or pricing issues.
- Treat the voicemail-plan result as a lead for further analysis rather than proof that voicemail prevents churn.
- Collect call-reason, date/time, and revenue data to support the analyses that could not be completed.

## Limitations

- The analysis is descriptive; associations are not causal findings.
- No statistical significance tests are recorded for the mean differences.
- Logistic regression was not completed.
- Time-series analysis was not possible without date/time data.
- Customer-service call reasons were unavailable.
- ARPU, revenue loss, and CLV were not calculated due to missing financial inputs.
- The clustering output is treated as the existing workbook result; the README does not claim an independently validated clustering model.

## Suggested repository structure

```text
Telecommunications-Churn-Analysis/
├── Telecommunications_Churn_Analysis.xlsx
├── README.md
└── images/
    └── churn-dashboard.png
```

Add a dashboard screenshot to `images/churn-dashboard.png` and include this Markdown in the README where you want it displayed:

```markdown
![Telecommunications Churn Dashboard](images/churn-dashboard.png)
```
