# Customer Churn Analysis & Retention Strategy

## Project Overview
Comprehensive churn analysis combining RFM segmentation, cohort analysis, and predictive modeling to identify at-risk customers and design targeted retention strategies with 141% ROI.

## Business Problem
- Customer acquisition costs 5-7x more than retention
- 26.54% annual churn rate costs $777K in lost revenue
- Need to identify high-risk customers and optimize retention spending

## Dataset
- **Source:** Kaggle - Telco Customer Churn
- **Customers:** 7,043 telecom subscribers
- **Churn Rate:** 26.54% (1,869 churned customers)
- **Features:** Demographics, services, contract details, billing info
- **Revenue Impact:** $456K monthly revenue, $139K at risk from churn

## Methodology

### 1. Customer Profiling (60% of Analysis)
**Demographics & Behavior:**
- Analyzed churn patterns across demographics, services, and contracts
- **Key Finding:** Month-to-month contracts have 42.7% churn vs 2.8% for two-year
- **Payment Impact:** Electronic check users churn 3x more than auto-pay (45% vs 15%)

**Tenure Analysis:**
- Churned customers stay only 18 months vs 37.6 months for retained
- **Critical Period:** 47.7% churn in first 12 months
- Retention improves dramatically: 47% → 90% from 0-6 months to 48+ months cohort

### 2. RFM-Style Segmentation
Created 5 customer segments based on tenure, service adoption, and revenue:

| Segment | Count | Churn Rate | Avg CLV | Strategy |
|---------|-------|------------|---------|----------|
| **Champions** | ~1,200 | 18% | $5,500 | Upsell & referrals |
| **Loyal** | ~1,300 | 31% | $3,000 | Contract upgrades |
| **Potential** | ~1,500 | 32% | $1,500 | Engagement campaigns |
| **At Risk** | ~1,500 | 27% | $800 | Retention offers |
| **Lost** | ~400 | 18% | $200 | Win-back campaigns |

### 3. Cohort Retention Analysis
Tracked retention rates across tenure groups:
- 0-6 months: 47% retention (critical onboarding period)
- 12-24 months: 71% retention
- 48+ months: 90% retention (loyalty inflection point)

**Insight:** First year is make-or-break - customers who survive 12 months have 3x better retention

### 4. Predictive Model (20% of Analysis)
**Logistic Regression Model:**
- **Recall:** 80.7% (catching 8 out of 10 churners)
- **Precision:** 50%
- **ROC-AUC:** 0.833
- **Top Predictors:** Tenure (-), Monthly Charges (+), Contract Type (-)

## Key Findings

### Revenue Impact
- **Total Monthly Revenue:** $456,117
- **Revenue at Risk (Churn):** $139,131/month ($1.67M annually)
- **Revenue Lost to Churn:** 30.5% of total

### Churn Drivers (Ranked by Impact)
1. **Contract Type:** Month-to-month 15x more likely to churn
2. **Tenure:** New customers (<12 months) churn at 47.7%
3. **Payment Method:** Electronic check 3x higher churn
4. **Services:** Customers with 1-2 services churn 2x more
5. **Monthly Charges:** Higher charges correlate with churn

### Customer Lifetime Value
- **Champions:** $5,500 average CLV (27x more than Lost customers)
- **Churned Customers:** $1,532 avg CLV
- **Retained Customers:** $2,550 avg CLV
- **Gap:** $1,018 per customer retained

## Business Recommendations

### Immediate Actions (0-3 Months)
1. **Target At-Risk Segment (1,929 customers)**
   - Proactive outreach with 10-15% retention discount
   - Contract migration incentives
   - Expected ROI: 141%

2. **Fix Payment Method Issue**
   - Incentivize auto-pay adoption (reduce electronic check users)
   - Potential to reduce churn by 10-15 percentage points

3. **First-Year Focus**
   - Enhanced onboarding for 0-12 month customers
   - 90-day check-in calls
   - Early contract upgrade offers

### Medium-Term Strategy (3-12 Months)
1. **Segment-Specific Campaigns**
   - Champions: Referral program ($50 credit per referral)
   - Loyal: Bundle upgrades with 6-month price lock
   - Potential: Engagement campaigns + service optimization
   - At Risk: Aggressive retention (up to 25% discount)

2. **Contract Strategy**
   - Incentivize 1-year and 2-year contracts
   - Early renewal bonuses for month-to-month customers
   - Projected impact: 5-8% churn reduction

### Financial Projections
**Retention Campaign (High-Risk Customers):**
- Target: 1,929 at-risk customers
- Cost: $192,900 ($100/customer)
- Expected saves: 578 customers (30% success rate)
- Revenue saved (24 months): $465,467
- **Net benefit: $272,567 (141% ROI)**

**Annual Impact of Full Strategy:**
- Estimated churn reduction: 26.5% → 18-20%
- Revenue preserved: $400K-500K annually
- Customer acquisition savings: $200K-300K (reduced replacement needs)

## Project Structure
```
Customer_Churn_Analysis/
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── notebooks/
│   └── Churn_Analysis.ipynb
│
├── models/
│   ├── churn_prediction_model.pkl
│   └── scaler.pkl
│
├── results/
│   ├── feature_importance.csv
│   └── business_recommendations.csv
│
├── analysis/
│   └── cohort_analysis.csv
│
├── dashboard/
│   ├── churn_dashboard_data.csv
│   └── segment_summary.csv
│
├── images/
│   ├── 01_churn_distribution.png
│   ├── 02_customer_analysis.png
│   └── 03_segmentation_analysis.png
│
└── README.md
```

## Tools & Technologies
- **Python 3.12:** pandas, numpy, scikit-learn
- **Analysis:** RFM segmentation, cohort analysis, CLV calculation
- **Modeling:** Logistic Regression with class balancing
- **Visualization:** Matplotlib, Seaborn
- **Dashboard:** Power BI (in progress)

## Key Learnings
1. **Segmentation Drives Strategy:** Different customer segments need different retention approaches
2. **First Year Critical:** 47.7% churn rate in first 12 months requires focused onboarding
3. **Contract Type Matters Most:** Month-to-month customers are 15x more likely to churn
4. **Tenure is King:** Tenure was the strongest negative predictor of churn (-1.06 coefficient)
5. **ROI Focus:** Targeted retention (30% success) delivers 141% ROI vs broad campaigns

## Future Improvements
- Add customer satisfaction scores (NPS) as features
- Implement time-series analysis for churn prediction timing
- A/B test retention offers by segment
- Build real-time churn risk scoring dashboard
- Integrate with CRM for automated retention triggers

