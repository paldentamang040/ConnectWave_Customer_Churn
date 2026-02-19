# 🌊 ConnectWave: Proactive Customer Churn Prediction & Alert System

## 📌 Project Overview
ConnectWave is a telecommunications provider currently experiencing an increasing churn rate among its 50,000 customers. This project transitions the company from a **reactive** approach to a **proactive** data-driven strategy by predicting churn risk and notifying the retention team in real-time.

### Business Objectives:
* **Analyze:** Identify behavioral patterns and service gaps that drive customer attrition.
* **Predict:** Utilize a Machine Learning model to calculate the churn probability for every customer.
* **Automate:** Trigger instant Slack notifications for at-risk customers (Risk > 75%).
* **Retain:** Implement HR and operational strategies to improve long-term loyalty.

---

## 📊 Key Data Insights
Based on the analysis of 7,043 customers:
* **Current Churn Rate:** 26.54%.
* **High-Risk Segment:** Customers on **Month-to-Month** contracts with high **Monthly Charges** (~$64.76).
* **Loyalty Factor:** Churn decreases significantly as **Tenure** increases, highlighting the importance of the first 6–12 months.

---

## 🛠️ Technical Implementation

### 1. Machine Learning Model
* **Algorithm:** Random Forest Classifier.
* **Input Features:** Tenure, Monthly Charges, Contract Type, Payment Method, and Service Add-ons (Security, Tech Support).
* **Performance:** Evaluated using ROC-AUC and Classification Reports.
* **Persistence:** Model exported as `churn_model.pkl`.

### 2. Automated Slack Integration
The system includes a custom Python integration with the Slack API.
* **Workflow:** The model scores test data → identifies customers with >0.75 risk → sends a JSON payload to a Slack Webhook.
* **Outcome:** The retention team receives an instant alert containing the Customer ID and their specific Risk Score.

---

🚀 Key Features
1. Predictive Model
We utilized a Random Forest Classifier to predict churn. The model is exported as churn_model.pkl for production use.

2. Automated Slack Integration
The system includes a send_slack_alert function. When the model identifies a customer with a churn probability > 75%, it automatically sends a JSON payload to a Slack webhook.

Alert Format:

⚠️ High Churn Risk Detected!

Customer ID: [ID]
Risk Score: [Score]

---

## 💡 Actionable Recommendations

1.  **90-Day "White-Glove" Onboarding:** Target new customers with proactive check-ins to navigate the high-risk early tenure period.
2.  **Contract Migration Strategy:** Incentivize month-to-month users to switch to 1-year or 2-year contracts through "Stability Discounts."
3.  **Value-Added Bundling:** Proactively offer free "Online Security" or "Tech Support" to high-risk customers to increase "stickiness."
4.  **The "Retention Strike Team":** Formalize an operational workflow where Slack alerts are assigned to specialists for personal outreach within 24 hours.

---

## 📂 Project Structure
```text
├── ConnectWave_Churn_Prediction.ipynb  
├── churn_model.pkl                     
├── Slack alert                    
└── README.md                           
