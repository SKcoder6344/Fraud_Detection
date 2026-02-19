# Fraud Detection Machine Learning Project

A comprehensive machine learning solution for detecting fraudulent financial transactions using XGBoost classifier on a highly imbalanced dataset of 6.3+ million transactions.

## 🔗 Quick Access

**Google Colab Notebook:** [View & Run in Colab](https://colab.research.google.com/drive/1g3_pP3GWfzC9aG6kDIUbEWG6qS4NloZJ?usp=sharing)

## 📊 Project Overview

This project implements a fraud detection system that analyzes financial transaction patterns to identify fraudulent activities with 99.99% ROC-AUC accuracy. The model processes transaction data including balance changes, transaction types, and engineered features to detect fraud in real-time scenarios.

### Key Statistics
- **Dataset Size:** 6,362,620 transactions
- **Fraud Rate:** 0.129% (highly imbalanced)
- **Time Period:** 30 days (744 hours)
- **Model Accuracy:** 99.99% ROC-AUC Score

## 🎯 Features

### Data Analysis
- Comprehensive exploratory data analysis (EDA)
- Missing values and outlier analysis
- Transaction type distribution analysis
- Fraud pattern visualization

### Feature Engineering
- **errorBalanceOrig:** Balance discrepancy detection on sender side
- **errorBalanceDest:** Balance discrepancy detection on receiver side
- **isHighRiskType:** Flags TRANSFER and CASH_OUT transactions
- **isOriginDrained:** Identifies completely emptied accounts
- **isDestEmpty:** Detects transactions to new/empty accounts

### Machine Learning Model
- **Algorithm:** XGBoost Classifier
- **Handling Imbalance:** Strategic undersampling (10:1 ratio)
- **Performance Metrics:**
  - ROC-AUC Score: 0.9999
  - Average Precision: 0.9985
  - Fraud Recall: 99.75%
  - Fraud Precision: 87%
  - F1-Score: 0.93

## 🔍 Key Findings

### Top Fraud Indicators
1. **errorBalanceOrig (50.44%)** - Balance inconsistencies on sender side
2. **isOriginDrained (46.09%)** - Complete account drainage
3. **Transaction Amount (1.32%)** - Avg fraud: ₹1.46M vs normal: ₹178K
4. **Transaction Type** - Only TRANSFER and CASH_OUT show fraud activity

### Fraud Patterns Discovered
- 98.1% of fraud cases completely drain the origin account
- 65.2% of fraud destinations are empty accounts
- Fraudulent transactions average 8x higher amounts
- Only TRANSFER and CASH_OUT transaction types exhibit fraud

## 🛠️ Technologies Used

- **Python 3.x**
- **Data Processing:** NumPy, Pandas
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn, XGBoost
- **Environment:** Google Colab

## 📁 Project Structure

```
Fraud-Detection-ML/
│
├── accredian_python_file.ipynb    # Main Jupyter notebook
├── Data_Dictionary.txt             # Dataset documentation
├── README.md                       # Project documentation
└── requirements.txt                # Python dependencies (if applicable)
```

## 📈 Model Performance

### Confusion Matrix Results
- **True Negatives:** 1,270,642
- **False Positives:** 239
- **False Negatives:** 4
- **True Positives:** 1,639

### Classification Report
- **Non-Fraud Precision:** 1.00
- **Fraud Recall:** 1.00
- **Overall Accuracy:** 99.98%

## 💡 Business Applications

### Prevention Strategies
1. **Real-time Transaction Scoring** - Deploy model as API endpoint
2. **Velocity Checks** - Monitor rapid account drainage patterns
3. **Destination Verification** - Enhanced KYC for new accounts
4. **Transaction Limits** - Smart thresholds based on model predictions
5. **Behavioral Analytics** - Customer baseline profiling
6. **Time-based Monitoring** - Increased sensitivity during off-peak hours

### Success Metrics
- Reduction in fraud detection time
- Decreased false positive rates
- Lower financial losses from fraud
- Improved customer satisfaction through reduced friction

## 🚀 Getting Started

### Prerequisites
```bash
numpy
pandas
matplotlib
seaborn
scikit-learn
xgboost
```

### Running the Notebook
1. Open the [Google Colab link](https://colab.research.google.com/drive/1g3_pP3GWfzC9aG6kDIUbEWG6qS4NloZJ?usp=sharing)
2. Run all cells sequentially
3. Review visualizations and model performance metrics

## 📊 Dataset Information

The dataset contains synthetic financial transaction data with the following features:

- **step:** Time unit (1 step = 1 hour)
- **type:** Transaction type (CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER)
- **amount:** Transaction amount in local currency
- **nameOrig:** Customer initiating the transaction
- **oldbalanceOrg:** Initial balance before transaction
- **newbalanceOrig:** New balance after transaction
- **nameDest:** Recipient of the transaction
- **oldbalanceDest:** Recipient's initial balance
- **newbalanceDest:** Recipient's new balance
- **isFraud:** Fraud indicator (target variable)
- **isFlaggedFraud:** Business rule-based flag (>200K transactions)

## 📝 Analysis Questions Answered

The project comprehensively addresses:
1. Data cleaning methodology (missing values, outliers, multicollinearity)
2. Model selection and justification (XGBoost)
3. Variable selection process and feature engineering
4. Model performance evaluation
5. Key fraud prediction factors
6. Logical validation of predictive features
7. Prevention strategies and recommendations
8. Effectiveness measurement frameworks

## 👤 Author

**Sujal Kumar Nayak**

- LinkedIn: [linkedin.com/in/sujal-kumar-nayak](https://www.linkedin.com/in/sujal-kumar-nayak/)
- Email: nayaksujalkumar@gmail.com

## 📄 License

This project is created for educational and portfolio purposes.

## 🙏 Acknowledgments

- Dataset: Synthetic financial transaction data
- Inspiration: Real-world fraud detection systems used by PayPal, Stripe, and major banks
- Tools: Google Colab for cloud computing resources

---

**Note:** This project demonstrates advanced machine learning techniques for fraud detection. The model achieves near-perfect performance on the test set and provides actionable insights for real-world fraud prevention systems.
