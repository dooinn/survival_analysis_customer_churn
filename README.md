# Exploring Customer Churn with Survival Analysis  

This project applies **survival analysis** techniques to explore and model **customer churn** in a subscription-based business. Unlike traditional classification approaches, survival analysis captures **when** customers churn, not just **if** they churn, making it a powerful tool for customer retention strategies.  

---

## Dataset  
- **Source:** [Kaggle Customer Churn Dataset](https://www.kaggle.com/datasets/muhammadshahidazeem/customer-churn-dataset)  
- **Size:** 440,832 customers  
- **Features:**  
  - **Demographics:** Age, Gender  
  - **Behavioral:** Usage Frequency, Support Calls, Payment Delay, Total Spend, Last Interaction  
  - **Contractual:** Tenure, Subscription Type, Contract Length  
  - **Outcome:** Churn (0 = Active, 1 = Churned)  

---

## Analysis Steps  

### 1. Exploratory Data Analysis (EDA)  
- **Churn rate:** ~56% (very high).  
- **Early churn:** Many customers drop out in the **first month**.  
- **Churn-prone:** Older, female, monthly contracts, low usage, frequent support calls, delayed payments.  
- **Loyal customers:** Younger, male, annual/quarterly contracts, higher spend, more engaged.  

### 2. Kaplan–Meier & Non-parametric Methods  
- Steep decline in survival probability during the **first month**.  
- **Gender effect:** Females churn earlier and more often.  
- **Contract effect:** Monthly contracts are the riskiest (near 100% churn).  
- **Subscription type:** No significant impact on churn.  

### 3. Cox Proportional Hazards Model  
- Significant predictors: gender, contract length, age, support calls, payment delays, usage frequency, total spend.  
- **C-index = 0.71** → good predictive accuracy.  
- PH assumption violations → informative but imperfect model.  

### 4. Accelerated Failure Time (AFT) Model  
- Compared **Weibull** vs **Log-normal**.  
- **Weibull AFT performed best (lowest AIC).**  
- Findings:  
  - Shorter survival: monthly contracts, more support calls, payment delays, inactivity, older customers.  
  - Longer survival: males, higher spend, higher usage.  

---

## Key Insights & Business Implications  
- **Target monthly customers** → encourage upgrades to quarterly/annual plans.  
- **Improve onboarding** → critical to reduce steep early churn (month 1).  
- **Monitor support calls** → frequent contact = dissatisfaction.  
- **Reward loyal/high-value users** → high spenders and engaged customers.  
- **Tailor by demographics** → females and older customers need focused retention strategies.  

---

## Methods Used  
- Kaplan–Meier Estimator  
- Nelson–Aalen Estimator & Hazard Analysis  
- Log-rank & Fleming–Harrington Tests  
- Cox Proportional Hazards (with stratification)  
- Weibull & Log-normal Accelerated Failure Time Models  

---

## Conclusion  
Survival analysis provides **richer insights than classification models** by modeling churn dynamics over time.  
The **Weibull AFT model** emerged as the most robust, highlighting:  
- Contract structure,  
- Customer engagement,  
- Behavioral signals (support calls, payment delays)  

as the strongest predictors of churn.  

---
