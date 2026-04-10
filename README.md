# Company-Bankruptcy-Prediction
AI-powered bankruptcy prediction system — XGBoost ROC-AUC 0.9367 across 6,819 companies

📊 Project Overview:
-------------------
Bankruptcy causes massive financial losses for investors, creditors, and employees. Traditional analysis is slow, manual, and reactive — catching problems too late.
This project builds an AI-powered early warning system that:

Flags financially distressed companies months before collapse
Handles severe class imbalance (30:1 ratio)
Uses explainable AI to identify the most critical risk factors
Achieves production-ready ROC-AUC performance

<img width="650" height="321" alt="Screenshot 2026-04-10 at 7 33 44 AM" src="https://github.com/user-attachments/assets/c4e9e2ba-a448-4f74-82e2-27fa7a7b3d41" />

Key Achievement: Optimized decision threshold (0.5 → 0.365) boosted Recall from 42% → 49.1%, correctly flagging 109 out of 220 bankrupt companies.

📁 Dataset: 
----------

Source: Taiwan Economic Journal (TEJ) via UCI ML Repository
Companies: 6,819 total (220 bankrupt, 6,599 healthy)
Features: 94 numeric financial ratios
Class Imbalance: Severe — 30:1 ratio (bankrupt:healthy)
Missing Values: Zero — clean dataset

🛠 Methodology:
---------------

**Exploratory Data Analysis** 
Distribution analysis across 94 financial features
Class imbalance confirmation (3.22% bankruptcy rate)
Skewness check (max skewness: 82.6)
IQR-based outlier detection

**Feature Engineering**
Engineered 4 Altman Z-Score inspired financial ratios: 
Working Capital to Total Assets
Debt to Assets Ratio
Retained Earnings to Total Assets
Cash Flow to Total Debt

**Preprocessing Pipeline** 
IQR outlier clipping (upper/lower bounds)
StandardScaler normalization
Class weight balancing (scale_pos_weight = 30)

**Model Training** 
5-Fold Stratified Cross-Validation across all models
Models: Logistic Regression, XGBoost, LightGBM, CatBoost
Hyperparameter tuning for each model

**Ensemble Stacking** 
Base models: LR, XGBoost, LightGBM, CatBoost
Meta-learner: Logistic Regression on OOF predictions
Final stacked AUC: 0.923

**Threshold Optimization** 
Default threshold: 0.5 → Recall: 42%
Optimized threshold: 0.365 → Recall: 49.1%
Correctly flags 109/220 bankrupt companies

<img width="679" height="610" alt="Screenshot 2026-04-10 at 7 34 55 AM" src="https://github.com/user-attachments/assets/4bf1712c-2663-4186-9464-9217e46ed959" />

Business Insights:
------------------
**Companies at high bankruptcy risk typically show:**

❌ High Debt-to-Assets Ratio — over-leveraged balance sheet

❌ Negative / Low ROA — not generating returns on assets

❌ Poor Cash Flow to Liability coverage — unable to service debt

❌ Low Working Capital to Total Assets — liquidity shortage

❌ Thin or Negative Operating Margins — core business unprofitable

Recommended Actions:
-------------------- 
**Flag companies with predicted probability > 0.365 for immediate review**

**Monitor Debt Ratio & Cash Flow monthly for early-warning triggers**

**Apply model quarterly to re-rank credit/investment risk**

**Combine model output with qualitative analyst review before action**


<img width="594" height="324" alt="Screenshot 2026-04-10 at 7 44 26 AM" src="https://github.com/user-attachments/assets/a1cba6dd-56cb-412d-9aab-8efee4298ea0" /> 
 

👨‍💻 Author
Kumar Katariya

🏆 **Kaggle Expert — Top 4% Globally (#2,226 / 59,691) — Bronze Notebook Medal**

**💼 Upwork Top Rated Plus — $300K+ earned, 100% Job Success** 

📄 License
This project is licensed under the MIT License — see the LICENSE file for details.

⭐ If you found this project useful, please give it a star!

