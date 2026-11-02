Student Performance Prediction & Fairness Analysis

Overview

This project predicts whether a student will pass or fail using machine learning and examines model performance across gender groups.

Dataset

- Source: UCI Student Performance Dataset
- File: "student-mat.csv"
- Target: Pass (G3 ≥ 10) or Fail (G3 < 10)

Technologies

- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- SHAP

Model

A Random Forest Classifier was trained to predict student performance.

- Accuracy: 86.08%
- Confusion Matrix: [[24, 2], [9, 44]]

Explainability

- Feature importance was used to identify influential features.
- SHAP was used to explain model predictions.
- Previous grades (G1 and G2) were among the most influential features.

Bias Analysis

The model was evaluated for potential gender-related bias by comparing its performance across female and male groups.

The following results were obtained:

Gender| Samples| Accuracy| Precision| Recall| F1 Score
Female| 47| 85.1%| 92.6%| 83.3%| 87.7%
Male| 32| 87.5%| 100%| 82.6%| 90.5%

The results show that the model achieved slightly higher accuracy and F1 score for the male group, while recall was nearly identical across both groups.

These differences indicate a potential performance disparity that should be investigated further. However, the sample sizes are relatively small, so the results alone are not sufficient to establish that the model is biased.

Bias Mitigation Recommendations

The following practical steps are recommended to improve model fairness:

1. Improve dataset representation: Collect additional data to ensure that different gender groups are adequately represented.
2. Evaluate fairness regularly: Monitor accuracy, precision, recall, and F1 score across sensitive groups.
3. Review influential features: Investigate whether sensitive attributes or proxy features disproportionately influence predictions.
4. Consider fairness-aware techniques: Evaluate methods such as reweighting training samples or adjusting model thresholds, where appropriate.
5. Conduct periodic audits: Reassess the model using new data to identify potential changes in fairness and performance.

Project Structure

Responsible_AI & Model_Interpretation/
├── .venv/
├── data/
│   └── student-mat.csv
├── notebooks/
│   └── responsible_ai_analysis.ipynb
├── reports/
│   └── responsible_ai_model_interpretation_report.docx
├── README.md
└── requirements.txt

Run the Project

Install the required libraries:

pip install -r requirements.txt

Open and run "notebooks/responsible_ai_analysis.ipynb" in Jupyter Notebook or VS Code.

Conclusion

The project demonstrates the use of feature importance, SHAP-based interpretation, and gender-wise performance evaluation to analyze model explainability and fairness.

Although the model achieved reasonably consistent performance across the evaluated gender groups, further testing with larger and more representative datasets is recommended before drawing strong conclusions about fairness.