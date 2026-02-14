# Census Bureau Income Classification & Customer Segmentation

## Project Overview
This project uses U.S. Census Bureau data (1994-95 Current Population Surveys) to:
1. **Classification** — Predict whether an individual earns above or below $50,000 based on 40 demographic and employment variables.
2. **Segmentation** — Identify distinct customer segments for targeted marketing strategies using K-Means clustering.

## Project Structure
```
JPMP/
├── data/
│   ├── census-bureau.data          # Raw dataset (~199K rows, 42 columns)
│   └── census-bureau.columns       # Column header definitions
├── notebook/
│   └── EDA_Prediction_Segmentation.ipynb   # Full analysis notebook
├── requirements.txt                # Python dependencies
└── Readme.MD                       # This file
```

## Setup & Installation

### Prerequisites
- Python 3.11+
- pip

### Steps
1. Clone or download this repository
2. Create a virtual environment:
```bash
   python -m venv .venv
   source .venv/bin/activate        # Mac/Linux
   .venv\Scripts\activate           # Windows
```
3. Install dependencies:
```bash
   pip install -r requirements.txt
```
4. Mac users — XGBoost requires OpenMP:
```bash
   brew install libomp
```

## Running the Code
1. Open the project in VS Code
2. Ensure the Jupyter extension is installed
3. Open `notebook/EDA_Prediction_Segmentation.ipynb`
4. Select the `.venv` Python interpreter
5. Run cells sequentially from top to bottom

## Notebook Workflow
The notebook is organized into the following sections:

| Section | Description |
|---------|-------------|
| **Step 1: Data Exploration** | Loading, inspection, column analysis, NIU analysis, feature-income relationships |
| **Step 2: Preprocessing** | Column dropping, encoding, feature selection, train/test split |
| **Step 3: Classification** | Logistic Regression baseline → XGBoost → Optuna hyperparameter tuning |
| **Step 4: Segmentation** | Feature preparation, scaling, elbow method, K-Means (k=5), cluster profiling |

## Key Results
- **Classification:** XGBoost achieved ROC-AUC of 0.956 with 88% recall on the >$50K class
- **Segmentation:** 5 distinct clusters identified — Working Professionals, Associate Degree Holders, Part-Time/Underemployed, Children/Minors, and Retirees

## Dependencies
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- optuna
