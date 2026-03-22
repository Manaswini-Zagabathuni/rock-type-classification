Rock Type Classification
---
A machine learning project that classifies rocks as Igneous, Metamorphic, or Sedimentary using visual features and compares model performance against human judgment.

---
Project Overview
This project applies and compares multiple classification algorithms to identify rock types based on observable geological features. It also includes a unique human vs. model comparison to evaluate how well ML models align with human perception.
Best Model: Ensemble (Logistic Regression + SVM + Random Forest)  
Key Metric: Accuracy, Precision, Recall, F1-Score

---
Project Structure
```
├── Hw2_Q1.ipynb                # Main Jupyter Notebook (full pipeline)
├── feature_presence540.txt     # Feature dataset (540 rock samples)
├── aggregateRockData.xlsx      # Rock type labels
├── trialData.csv               # Human trial data
└── README.md
```
---
Features Used
Feature	Description
Angular_fragments	Presence of angular rock fragments
Rounded_fragments	Presence of rounded rock fragments
Straight_stripes	Straight stripe patterns
Curved_stripes	Curved stripe patterns
Physical_layers	Visible physical layering
Veins	Presence of veins
Oily_Shimmery	Oily or shimmery surface
Splotchy	Splotchy appearance
Single_crystal	Single crystal structure
Multiple_crystals	Multiple crystal structures
Sandy_texture	Sandy surface texture
Target Classes: `1 = Igneous` | `2 = Metamorphic` | `3 = Sedimentary`

---
Methodology
1. Data Preparation
480 samples split into train (300), validation (90), and test (90)
Z-score normalization via `StandardScaler`
Balanced class representation across all splits
2. Statistical & Correlation Analysis
Descriptive statistics and feature distributions
Pearson Correlation Coefficient heatmap
Top correlated features: `Physical_layers`, `Single_crystal`, `Splotchy`
3. Models & Hyperparameter Tuning (GridSearchCV)
Model	Best Parameters	Test Accuracy
Logistic Regression	C=10, solver=lbfgs	~68%
SVM	kernel=linear, C=1	~68%
Random Forest	max_depth=15, n_estimators=100	~68%
Ensemble (Voting)	soft voting (all 3)	~72%
4. Human vs. Model Comparison
Human accuracy measured from participant trial data
Ensemble model achieved strongest correlation with human judgment (r = 0.58)
All models showed significant positive correlation with human accuracy
---
How to Run
Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy openpyxl jupyter
```
Run the Notebook
```bash
jupyter notebook Hw2_Q1.ipynb
```
> Make sure `feature_presence540.txt`, `aggregateRockData.xlsx`, and `trialData.csv` are in the same directory.
---
Human vs Model Correlation
Model	Correlation with Human Accuracy
Logistic Regression	r = 0.55
SVM	r = 0.53
Random Forest	r = 0.50
Ensemble	r = 0.58

---

Tech Stack
Python 3
pandas, NumPy, SciPy — data handling & statistics
matplotlib, seaborn — visualization
scikit-learn — modeling, tuning, evaluation

---
