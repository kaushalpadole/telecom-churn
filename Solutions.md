# Telecom Churn Analysis: Organized Solutions

This document organizes the workbook findings into a cleaner structure by increasing complexity. It highlights the main descriptive patterns, key risk segments, and the limitations of the current analysis.

## Quick Summary

- Overall churn rate: 14.07%
- International-plan subscribers churn at 42.17% vs. 11.18% for non-subscribers.
- Customers with more than 3 service calls churn at 50.75% vs. 10.93% for those with 3 or fewer.
- Customers with a voicemail plan churn at 7.37% vs. 16.44% for those without one.
- Cluster 3 is the highest-risk segment with a churn rate of 34.01%.
- Account length and total day calls show very weak correlation with churn.

---

## 1. Basic-Level Questions

### Q1. How many customers churned, and what proportion of the customer base is that?

**Answer:**
- Total customers: 4,250
- Churned (yes): 598
- Retained (no): 3,652
- Churn rate: 14.07%
- Retention rate: 85.93%

**Explanation:**
The churn rate is calculated as 598 ÷ 4,250 = 14.07%. This is the baseline churn rate used for comparisons across customer groups.

**Excel approach:**
Use `COUNTIF` on the churn column to count yes and no values, then divide each count by the total customer count.

---

### Q2. What is the average account length for churned versus retained customers? Does tenure influence churn?

**Answer:**
- Retained customers: 99.92 months
- Churned customers: 102.14 months
- Difference: about 2.21 months
- Correlation between account length and churn indicator: approx. 0.0194

**Explanation:**
Churned customers have a slightly longer average account length, so the data does not suggest that churned customers are generally newer. The correlation is very weak, indicating little linear relationship between account length and churn.

**Excel approach:**
Use `AVERAGEIF` to compare mean account length by churn status, and `CORREL` for the numeric churn indicator versus account length.

---

### Q3. How does an international plan relate to churn?

**Answer:**
- No international plan: 431 of 3,854 churned = 11.18%
- International plan: 167 of 396 churned = 42.17%

**Explanation:**
The churn rate among international-plan subscribers is about 31 percentage points higher. This is a strong association and suggests that international-plan customers may face a different experience or pricing burden.

---

### Q4. Is there a difference in customer-service calls between churned and retained customers?

**Answer:**
- Retained customers: average 1.44 calls
- Churned customers: average 2.28 calls
- Difference: about 0.83 calls

**Explanation:**
Churned customers contact customer service more often on average. Repeated service contacts may reflect unresolved problems or dissatisfaction, though the dataset does not include the reason for each call.

---

### Q5. Do day, evening, and night call charges differ between churned and retained customers?

**Answer:**

| Charge type | Retained | Churned | Difference (Churned - Retained) |
|---|---:|---:|---:|
| Day | 29.84 | 35.53 | 5.69 |
| Evening | 16.88 | 17.85 | 0.97 |
| Night | 8.98 | 9.29 | 0.31 |

**Explanation:**
The largest difference is in daytime charges. Evening and night differences are much smaller. These are descriptive comparisons only; no statistical significance test is shown in the workbook.

---

### Q6. What is the relationship between total day minutes and churn?

**Answer:**
- Retained customers: average 175.56 day minutes
- Churned customers: average 208.99 day minutes
- Difference: 33.44 minutes

**Explanation:**
Churned customers use more daytime minutes on average. This may reflect plan fit, usage intensity, or other factors, but the comparison alone does not identify the cause.

---

### Q7. How does having a voicemail plan relate to churn rates?

**Answer:**
- No voicemail plan: 516 of 3,138 churned = 16.44%
- Voicemail plan: 82 of 1,112 churned = 7.37%

**Explanation:**
Customers with a voicemail plan have a lower observed churn rate. This may indicate that voicemail is valued, or that these customers differ in other ways. It is a lead for further investigation rather than proof of causation.

---

### Q8. Compare international minutes and charges for churned versus retained customers. Are higher values associated with churn?

**Answer:**

| Metric | Retained | Churned |
|---|---:|---:|
| International minutes | 10.19 | 10.63 |
| International charge | 2.75 | 2.87 |

**Explanation:**
Churned customers have slightly higher average international minutes and charges, but the differences are small compared with the much larger churn-rate gap associated with international-plan status.

---

### Q9. Is there a correlation between total day calls and churn?

**Answer:**
The workbook reports a correlation of approximately 0.01164 between total day calls and the numeric churn indicator.

**Explanation:**
This is a negligible positive correlation. In this dataset, the number of daytime calls has almost no linear relationship with churn status.

---

### Q10. Compare average evening charges for churned and retained customers.

**Answer:**
- Retained customers: 16.88
- Churned customers: 17.85
- Difference: 0.97

**Explanation:**
Churned customers have a higher average evening charge, but the difference is modest. The workbook does not include a statistical test, so this should not be described as statistically significant.

---

## 2. Medium-Level Questions

### Q1. Does any area code have a higher churn rate?

**Answer:**

| Area code | Customers | Churned | Churn rate |
|---|---:|---:|---:|
| 408 | 1,086 | 152 | 14.00% |
| 415 | 2,108 | 287 | 13.61% |
| 510 | 1,056 | 159 | 15.06% |

**Explanation:**
Area code 510 has the highest observed churn rate at about 15.06%, while 415 is the lowest at 13.61%. The gap is modest, so the area-code result alone cannot explain churn patterns.

---

### Q2. How does the number of customer-service calls relate to churn at different thresholds?

**Answer:**
- 3 or fewer calls: 428 churned out of 3,915 customers = 10.93%
- More than 3 calls: 170 churned out of 335 customers = 50.75%

**Explanation:**
The churn rate is much higher among customers with more than three service calls. This is one of the clearest risk patterns in the workbook.

---

### Q3. Is account length correlated with churn, and are newer customers more likely to churn?

**Answer:**
- Correlation: approximately 0.01938
- Churn rate by account-length quartile:
  - Q1: 12.78%
  - Q2: 14.33%
  - Q3: 15.85%
  - Q4: 13.35%

**Explanation:**
The correlation is very weak. Churn rises across the first three quartiles and then falls in Q4, so there is no consistent pattern indicating that newer customers are necessarily more likely to churn.

---

### Q4. Among international-plan subscribers, how do high and low international charges relate to churn?

**Answer:**
- Low international-charge group: 67 of 199 churned = 33.67%
- High international-charge group: 100 of 197 churned = 50.76%

**Explanation:**
The high-charge group has a churn rate about 17.09 percentage points higher than the low-charge group. This suggests that high international charges may warrant further business review.

---

### Q5. How do evening usage patterns relate to churn?

**Answer:**

| Evening usage group | Customers | Churned | Churn rate |
|---|---:|---:|---:|
| Low | 1,031 | 109 | 10.57% |
| Medium | 2,138 | 298 | 13.94% |
| High | 1,081 | 191 | 17.67% |

**Explanation:**
Churn rate increases from the low-usage group to the high-usage group. Higher evening usage is associated with higher churn in this dataset.

---

### Q6. What do the customer clusters show about churn?

**Answer:**

| Cluster | Customers | Churned | Churn rate |
|---|---:|---:|---:|
| Cluster 1 | 649 | 66 | 10.17% |
| Cluster 2 | 2,957 | 313 | 10.59% |
| Cluster 3 | 644 | 219 | 34.01% |

**Average usage by cluster:**

| Cluster | Day minutes | Evening minutes | Night minutes | International minutes |
|---|---:|---:|---:|---:|
| Cluster 1 | 140.33 | 160.78 | 162.64 | 8.03 |
| Cluster 2 | 179.75 | 200.68 | 200.03 | 10.31 |
| Cluster 3 | 222.86 | 237.53 | 240.98 | 12.26 |

**Explanation:**
Cluster 3 has a churn rate of 34.01%, much higher than the approximately 10% rates in Clusters 1 and 2. It also has the highest average usage across day, evening, night, and international minutes.

---

### Q7. How does voicemail-plan status interact with voicemail-message volume and churn?

**Answer:**
- No voicemail plan: 516 of 3,138 churned = 16.44%; message volume is not applicable.
- Voicemail plan with 0 messages: 0 of 1 customer = 0.00%
- Voicemail plan with 1–16 messages: 2 of 58 customers = 3.45%
- Voicemail plan with more than 16 messages: 80 of 1,053 customers = 7.60%

**Explanation:**
Customers with a voicemail plan generally show lower churn rates than customers without one. Among plan subscribers, churn is higher in the group with many voicemail messages, but the pattern is still much lower than the no-plan group.

---

### Q8. Is there a point where higher day minutes or charges lead to higher churn?

**Answer:**
The workbook includes a scatter plot of total day minutes versus total day charges, separated by churn status. The points follow a near-linear relationship.

**Explanation:**
Day charges closely track day minutes in the dataset, so the chart mainly reflects the pricing relationship between the two variables. It does not show a clear tipping point where higher usage automatically drives higher churn.

---

### Q9. Does the number of international calls affect churn differently for customers with and without an international plan?

**Answer:**

| International plan | International-call group | Customers | Churned | Churn rate |
|---|---|---:|---:|---:|
| No | High | 641 | 67 | 10.45% |
| No | Low | 1,574 | 181 | 11.50% |
| No | Medium | 1,639 | 183 | 11.17% |
| Yes | High | 69 | 27 | 39.13% |
| Yes | Low | 165 | 97 | 58.79% |
| Yes | Medium | 162 | 43 | 26.54% |

**Explanation:**
For customers without an international plan, churn rates are similar across all three groups. Among customers with an international plan, churn varies widely, and the low-call group shows the highest churn rate.

---

### Q10. Do particular customer-service call reasons predict churn?

**Answer:**
Not answerable with the supplied dataset.

**Explanation:**
The dataset records the number of customer-service calls but does not include the reason for each call. It is therefore not possible to compare churn by reason such as billing or technical issues.

---

## 3. Advanced-Level Questions

### Q1. Can a logistic-regression model predict churn likelihood?

**Answer:**
Not completed in the workbook. No logistic-regression model, coefficients, evaluation metrics, or predicted probabilities are recorded.

**Explanation:**
Logistic regression would model churn as a binary outcome using predictors such as international-plan status, service-call count, usage, charges, and account length. The workbook does not include this model.

---

### Q2. What churn trends or seasonality appear over time?

**Answer:**
Cannot be analyzed from the supplied workbook because there is no date or time-period field.

**Explanation:**
Time-series analysis needs observation dates or periods. The workbook contains customer-level records without a time dimension, so no trend or seasonality can be assessed.

---

### Q3. Which customer clusters are more prone to churn?

**Answer:**
- Cluster 1: 10.17% churn
- Cluster 2: 10.59% churn
- Cluster 3: 34.01% churn

**Explanation:**
Cluster 3 is the highest-risk segment in the workbook. It also has the highest average day, evening, night, and international minutes, which suggests a usage-heavy customer segment with elevated churn risk.

---

### Q4. How do international-plan status and international-minute groups interact with churn?

**Answer:**

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

**Explanation:**
Among customers without an international plan, churn is relatively stable across the four minute groups. Among international-plan subscribers, the Q4 group has a much higher churn rate, indicating a potentially important interaction between plan status and usage intensity.

---

### Q5. What is the economic impact of churn, including ARPU and customer lifetime value?

**Answer:**
Not calculated in the workbook.

**Explanation:**
The workbook does not provide the revenue inputs needed to estimate ARPU, lost revenue, or customer lifetime value. Call charges in the dataset should not be treated automatically as total revenue.

---

## 4. Overall Conclusions

The workbook identifies several patterns worth investigating:

- Overall churn is 14.07%.
- International-plan subscribers churn at 42.17% compared with 11.18% for non-subscribers.
- Customers with more than three service calls churn at 50.75% compared with 10.93% for those with three or fewer calls.
- Customers with a voicemail plan churn at 7.37% compared with 16.44% for those without one.
- Churn rates rise across low, medium, and high evening-usage groups (10.57%, 13.94%, 17.67%).
- Cluster 3 is the highest-churn segment at 34.01% and has the highest average usage across day, evening, night, and international minutes.
- Account length and total day calls show weak correlations with churn, at approximately 0.0194 and 0.0116 respectively.

### Suggested business actions

1. Investigate recurring customer-service contacts, especially for customers with more than three calls.
2. Review the international-plan customer experience, pricing, and fit with customer needs.
3. Investigate Cluster 3 to understand its high usage and elevated churn rate.
4. Examine higher evening-usage customers for possible pricing or plan-fit issues.
5. Treat the voicemail-plan result as a lead for further analysis rather than proof that voicemail prevents churn.
6. Collect call-reason, date/time, and revenue data to support deeper analysis.

### Limitations

- The analysis is descriptive; associations are not causal findings.
- No statistical significance tests are recorded for the mean differences.
- Logistic regression was not completed.
- Time-series analysis was not possible without date/time data.
- Customer-service call reasons were unavailable.
- ARPU, revenue loss, and customer lifetime value were not calculated due to missing financial inputs.
- The clustering output is treated as the result already contained in the workbook; the README does not claim an independently validated clustering model.

---

## Final Note

This analysis offers a strong starting point for churn diagnostics. The most actionable signals are concentrated around international-plan usage, customer-service contact frequency, and high-usage customer segments. A more complete business response would require richer operational and financial data.
