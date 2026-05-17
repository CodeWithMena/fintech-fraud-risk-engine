# FinTech Fraud & Real-Time Credit Risk Engine

## 📌 Project Overview
This project establishes a production-grade, backend transactional risk screening engine designed to intercept credit card fraud on a high-velocity financial network. Processing a massive dataset of 1.29M+ transactions with severe class imbalance (99.42% legitimate vs. 0.58% fraudulent), the engine deploys a class-weighted Random Forest classifier to identify structural fraud signatures, mitigate false alarms, and preserve capital.

## 🛠️ Tech Stack & Skills
* **Languages & Modules:** Python (Pandas, NumPy, Scikit-Learn) via Google Colab
* **Algorithmic Specializations:** Class-Imbalance Handling, Cost-Benefit Loss Matrices, Feature Importance Extraction, Stratified Pipeline Testing

---

## 🔍 Core Engineering Metrics & Audit Log

### 1. Backend Confusion Matrix Audit (Test Split)
* **True Negatives (Legitimate Approvals):** 308,816
* **True Positives (Successfully Deflected Fraud):** 1,579
* **False Positives (False Alarms / User Friction):** 13,476
* **False Negatives (Slipped Fraud Incidents):** 298

### 2. Operational Evaluation
* **Fraud Recall Rate (84.12%):** The engine successfully intercepts the overwhelming majority of fraud patterns, stopping financial leaks before clearing the network.
* **Precision Profile (10.49%):** In real-world fraud infrastructure, precision is intentionally sacrificed to prioritize maximum detection coverage (Recall) over the cost of small internal security investigations.

### 3. Top Predictive Risk Signatures
The machine learning algorithm extracted exactly which transaction vectors correlate with illicit card behavior:
1. **Transaction Magnitude (`amt`):** Holds an overwhelming **86.76%** of the entire predictive signal strength.
2. **Temporal Velocity (`unix_time`):** Holds **3.18%** signal strength, capturing abnormal transaction frequencies.
3. **Demographic Footprint (`city_pop`):** Holds **1.80%**, checking if transaction size deviates from the spending patterns of local populations.

---

## 💵 Executive Financial Mitigation Impact
To evaluate real-world utility, a custom cost-benefit matrix was integrated into the pipeline, assigning a $5 operational cost to investigate false alarms and full liability costs to missed fraud:

* **Unprotected Potential Damage:** $281,550.00
* **Operating Cost with Risk Engine Active:** $112,080.00
* **💰 NET CAPITAL PRESERVED BY SCRIPT:** **$169,470.00**

---

## 🚀 Key Strategic Recommendations for Security Teams
1. **Implement Step-Up Authentication on `amt` Flags:** Since transaction magnitude dominates the predictive signal (86.76%), integrate real-time SMS/biometric verification constraints immediately when an account's transaction size exceeds historical baseline limits.
2. **Optimize Temporal Alert Thresholds:** Utilize the temporal variations captured by `unix_time` to auto-suspend card spending if multiple cross-border or rapid-succession purchases register within narrow intervals.
