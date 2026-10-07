Will This Visitor Buy? 🛒
Predicting Online Shopper Purchase Intention with Machine Learning

A classification project that predicts whether an online-shop visitor will make a purchase, using the Online Shoppers Purchasing Intention Dataset.

Author: Anusha Darmi B.S

📌 Problem Statement

Each visit to an online shop is one session. For every session we know details like pages viewed and time spent, and whether the visitor bought something. The goal is to spot likely buyers early, so the shop can help them or target its ads better.

This is a binary classification task (buy / not buy).

📊 Dataset
Item	Value
Source	Online Shoppers Purchasing Intention Dataset (UCI Machine Learning Repository)
Raw shape	12,330 rows × 18 columns
Missing values	0
Duplicate rows	125
Shape after cleaning	12,205 rows × 18 columns
Target column	Revenue (True = bought, False = did not buy)

Feature groups

Numeric (10): Administrative, Administrative_Duration, Informational, Informational_Duration, ProductRelated, ProductRelated_Duration, BounceRates, ExitRates, PageValues, SpecialDay
Categorical (7): Month, VisitorType, Weekend, OperatingSystems, Browser, Region, TrafficType
Target (1): Revenue
🧹 Data Processing
Load the CSV file into a DataFrame
Check for missing values (none found)
Clean: remove 125 duplicate rows (12,330 → 12,205)
Encode text columns (e.g. Month, VisitorType) into numbers
Split into train and test sets (80% / 20%)

KNN and SVM additionally use scaled features.

🔍 Exploratory Data Analysis (EDA)
Target balance (buyers vs non-buyers)
Visitor type analysis
Month analysis (sessions per month, month vs Revenue)
Weekend vs weekday check
Outlier check (box plots)
Correlation heatmap

Key findings

Only 15.6% of sessions end in a purchase, so the data is imbalanced
About 85% of visitors are returning visitors
May and November are the busiest months
✂️ Train / Test Split
Set	Share	Sessions
Train	80%	9,764
Test	20%	2,441

All six models use the same split, so the comparison is fair.

🤖 Algorithms Used
Logistic Regression
Decision Tree
Random Forest
Gradient Boosting
K-Nearest Neighbors (KNN, k = 5)
Support Vector Machine (SVM)
📏 Evaluation Metrics
Metric	Meaning
Accuracy	How often the model is right overall
Precision	When it says "will buy", how often it is correct
Recall	Of all real buyers, how many it found
F1 Score	Balance of precision and recall

Recall and F1 matter most: missing a real buyer means a lost sale.

🏆 Results
Model	Accuracy	Precision	Recall	F1 Score
Logistic Regression	0.888	0.761	0.416	0.538
Decision Tree	0.871	0.587	0.599	0.593
Random Forest	0.906	0.749	0.602	0.668
Gradient Boosting	0.905	0.726	0.631	0.675
KNN	0.878	0.678	0.419	0.518
SVM	0.892	0.743	0.476	0.581

Better algorithm: Gradient Boosting, with the best F1 (0.675) and best recall (0.631), so it finds about 6 in 10 real buyers. Random Forest is a very close second (F1 0.668) and has the best accuracy (90.6%).

🚀 Future Improvements
Handle class imbalance (class weights or SMOTE)
Use cross-validation to settle the Gradient Boosting vs Random Forest tie
Tune model settings with grid search
Show which features matter most (feature importance)
🛠️ Tech Stack
Python
pandas, NumPy
Matplotlib, Seaborn
scikit-learn
▶️ How to Run
bash
# 1. Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# 3. Open the notebook
jupyter notebook

Make sure the dataset file (online_shoppers_intention.csv) is in the project folder (or update the path in the notebook).

📁 Project Structure
├── online_shoppers_intention.csv   # dataset
├── <your-notebook>.ipynb           # EDA + model training
├── Online_Shoppers_12_Slides.pptx  # presentation
└── README.md
👩‍💻 Author

Anusha Darmi B.S
