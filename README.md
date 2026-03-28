# Microsoft Cyber Security Threat Prediction-Project

**> Project Overview**

This project focuses on analyzing and predicting cybersecurity threats using a large-scale security alert dataset (500,000 records). The goal is to identify patterns in security incidents and build machine learning models to classify threat levels effectively.

The dataset includes information such as:

Alert Categories
MITRE ATT&CK Techniques
Suspicion Levels
Threat Family
Entity Type
OS Family
Geographical Data (Country, State, City)
Timestamps
Final Verdicts (Malicious / Suspicious / Non-malicious)

This project combines Exploratory Data Analysis (EDA), Statistical Analysis, Feature Engineering, PCA, LDA, and Machine Learning models to detect and predict threats.

**> Problem Statement**

Organizations generate massive volumes of security alerts daily. Many of these alerts are marked as "Suspicious," but only a fraction are truly malicious.

The objective of this project is to:

Analyze alert patterns.
Identify dominant threat categories.
Reduce dimensionality.
Build predictive models.
Improve threat classification accuracy.

**> Dataset Description**

Total Records: 500,000
Total Columns: 46
--High-cardinality fields like:
1. IncidentId
2. AlertId
3. EmailClusterId
4. Sha256
-- Categorical features such as:
a. Category (18 types)
b. EntityType (26 types)
c. SuspicionLevel (2 types)
d. LastVerdict (5 types)

**> Exploratory Data Analysis (EDA)**

Key Insights
1️. Alert Categories
Suspicious Activity is the most frequent category.
Malware and Defense Evasion are also significant.

2️. MITRE Techniques
Large diversity (800+ unique techniques).
Certain techniques (e.g., T1078) dominate.

3️. Entity Types
CloudApplication is the most common entity.
IP-based alerts are highly frequent.

4️. Suspicion Level vs Verdict
Majority of alerts marked as Suspicious
Most final verdicts are Non-malicious
Indicates need for improved detection precision.

5️. Time-Based Patterns
Incidents distributed across hours and days
Certain peak activity hours observed
Some months show higher alert density

**> Data Cleaning & Preprocessing**

-- Columns Removed
Removed high-cardinality or irrelevant columns like:
1. Id
2. IncidentId
3. AlertId
4. DeviceId
5. FileName
6. URL
7. Registry Keys
8. Application IDs

-- Missing Value Treatment
1. Handled missing values appropriately
2. Dropped irrelevant sparse columns
3. Encoded categorical features

-- Feature Engineering
1. Extracted:
  a. Hour
  b. Day
  c. Month
2. Converted timestamps into useful time-based features

**> Feature Engineering & Scaling**
1. Label Encoding / Encoding of categorical variables
2. Feature Scaling applied
3. Dimensionality Reduction using:
  a. PCA (Principal Component Analysis)
  b. LDA (Linear Discriminant Analysis)

**> Machine Learning Models**
-- The following models were implemented and evaluated:

1. Logistic Regression
2. Random Forest
3. Decision Tree
4. Support Vector Machine
5. KNN
6. Naive Bayes
-- Evaluation Metrics Used
1. Accuracy
2. Precision
3. Recall
4. F1-Score
5. Cohen’s Kappa
6. ROC-AUC (where applicable)

-- Custom model validation function used for systematic evaluation.

**> Dimensionality Reduction**
1. PCA (Principal Component Analysis)
  a. Reduced feature space
  b. Improved model efficiency
  c. Removed multicollinearity

2. LDA (Linear Discriminant Analysis)
  a. Improved class separability
  b. Enhanced classification performance

**> Statistical Analysis**
1. Distribution Analysis
2. Bivariate & Multivariate Analysis
3. Box Plots
4. Violin Plots
5. Count Plots
6. Scatter Plots
7. Stacked Bar Charts

-- These helped identify:
1. Peak attack hours
2. Category-action relationships
3. Entity-category interaction
4. Suspicion level vs verdict patterns

**> Key Findings:**
1. Suspicious alerts dominate dataset
2. Most alerts are ultimately non-malicious
3. Cloud environments are highly targeted
4. Certain attack techniques are repeatedly used
5. OSFamily “5” is most affected
6. Time-based clustering suggests targeted attacks

**> Recommendations**
1. Improve suspicious-to-malicious filtering
2. Strengthen cloud application monitoring
3. Enhance detection of frequent MITRE techniques
4. Improve investigation workflow for suspicious alerts
5. Allocate resources during peak attack hours

**> Tech Stack**
1. Python
2. Pandas
3. NumPy
4. Matplotlib
5. Seaborn
6. Scikit-learn
7. PCA & LDA
8. Statistical Testing

**> Project Overflow**
1. Data Understanding
2. Data Cleaning
3. Exploratory Data Analysis
4. Feature Engineering
5. Encoding & Scaling
6. PCA & LDA
7. Model Building
8. Model Evaluation
9. Insights & Recommendations

**> Future Improvements**
1. Implement XGBoost / LightGBM
2. Deploy as a web application
3. Real-time threat prediction pipeline
4. Hyperparameter tuning using GridSearchCV
5. Model explainability using SHAP
