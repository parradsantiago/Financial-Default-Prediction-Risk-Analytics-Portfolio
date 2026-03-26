# 📊 Credit Risk Scoring Model: Financial Default Prediction

This repository features an end-to-end **Machine Learning** project developed to predict the probability of loan default. By leveraging financial ratios and Gradient Boosting, this model serves as a decision-support tool for Risk Management and Treasury departments to optimize credit approval processes.

---

## 🎯 Business Case
The primary goal is to automate credit evaluation to minimize delinquency rates. In a corporate or banking context, identifying a "High Risk" profile before disbursement is critical to saving capital in provisions and reducing recovery costs. This project demonstrates how data-driven insights can enhance traditional financial analysis.

---

## 🛠️ Methodology & Technical Stack

### 1. Data Preprocessing & Cleaning
* **Outlier Management:** Filtered inconsistent records (e.g., ages > 100) to prevent model distortion.
* **Missing Value Imputation:** Applied **Median** imputation for employment length and **Mean** for interest rates, ensuring dataset integrity without losing valuable observations.

### 2. Financial Feature Engineering
I developed specific ratios to capture "repayment capacity" beyond raw income:
* **Debt-to-Income Ratio:** A key banking metric representing the percentage of annual income committed to the loan.
* **Loan-to-Income Ratio:** Measures the burden of the requested amount relative to the user's earnings.
* **One-Hot Encoding:** Transformed categorical variables (Home Ownership, Loan Intent) into binary vectors for algorithmic processing.

### 3. Model Development (XGBoost)
* **Algorithm:** Selected **XGBoost** (Extreme Gradient Boosting) for its superior performance on tabular financial data.
* **Handling Class Imbalance:** Since defaults are less frequent than successful payments, I utilized the `scale_pos_weight` parameter to prioritize the detection of "Bad Loans."
* **Validation:** Implemented a **Train/Test split (80/20)** to validate the model on unseen data and ensure robust generalization.

---

## 📈 Analysis of Results

### Performance Metrics
The model was evaluated using metrics aligned with financial risk priorities:
* **ROC-AUC Score:** High performance in distinguishing between "Good" and "Bad" payers.
* **Recall (Sensitivity):** We prioritized high Recall to capture the maximum number of potential defaults, as the cost of a defaulted loan far outweighs the lost opportunity of a rejected application.

### Model Interpretability (Permutation Importance)
To ensure transparency (avoiding "Black Box" models), I used **Permutation Importance** to identify risk drivers:
1. **Debt-to-Income Ratio:** Confirmed as the strongest predictor of default.
2. **Historical Default:** Previous credit issues show a significantly higher risk correlation.
3. **Person Income:** Higher income levels inversely correlate with default probability.

---

## 🚀 Business Impact & Conclusions
* **CAPEX & Liquidity Optimization:** By filtering high-risk clients automatically, the firm can allocate capital toward more secure and profitable credit lines.
* **Regulatory Compliance:** Using interpretability techniques provides a clear "Audit Trail" for credit decisions, which is essential for financial auditing and transparency.

---

## 💻 How to Run
1. Clone this repository.
2. Create a virtual environment and install dependencies:
   ```bash
   pip install -r requirements.txt