# Explainable_ML_LIME
Application of LIME in explaining the predictions of survival of patients with heart failure
# Background
LIME, is an algorithm that can explain the predictions of any classifier or regressor in a faithful way, by approximating it locally with an interpretable model.
Using LIME one can explain the predictions of any classifier for individual predictions, thus gaining the trust of the users for the model overall. LIME helps to not only generate quantitative results but also offers great visualization which is intutive and straightforward to understand. 
# Methods
- Data pre-processing and visualization
- Train/Test split (80:20)
- Feature selection analysis 
- Classifier models with selected features: Logistic Regression and Random Forest Classifier
- LIME classifier models with all features
- Metrics: 
     - For conventional ML classifiers: recall, precision, F1-score, and accuracy,
     - LIME coefficients and predictions
 # Results
Similar to feature selection output, the top 2 key determinants for the "true" positives from LIME analysis were serum creatinine and ejection fraction where 
the serum creatinine levels have appeared to dominate the outcome as observed while analyzing the false positve and negative predictions.
# References
- “Why Should I Trust You?” Explaining the Predictions of Any Classifier (KDD2016) by Marco Tulio Ribeiro, Sameer Singh, and Carlos Guestrin
http://arxiv.org/pdf/1602.04938.pdf
- Explain Your Model with LIME, https://medium.com/dataman-in-ai/explain-your-model-with-lime-5a1a5867b423
- LIME: How to Interpret Machine Learning Models With Python, https://towardsdatascience.com/lime-how-to-interpret-machine-learning-models-with-python-94b0e7e4432e
- Dataset: https://archive.ics.uci.edu/ml/datasets/Heart+failure+clinical+records
