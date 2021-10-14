# Explainable ML Classifier with LIME
Application of LIME in explaining the predictions of survival of patients with heart failure
# Background
LIME (Local Interpretable Model Agnostic Explanations), is an algorithm that can explain the predictions of any classifier or regressor in a faithful way, by approximating it locally with an interpretable model.Using LIME one can explain the predictions of any classifier for individual predictions, thus gaining the trust of the users for the model overall. LIME helps to not only generate quantitative results but also offers a great visualization which is intutive and straightforward to understand. 
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

Feature Selection output: Top 3 features identified: serum creatinine (7), age(0), and ejection fraction (4)
![image](https://user-images.githubusercontent.com/28870788/137401839-a19c6864-7242-48c9-b13f-9bdca7869ee4.png)

True positive prediction and negative predictions along with False positive/negative predictions from LIME on Logistic Regression Classifier are shown below. Similar analysis done on Random Forest Classifier, see notebook for the results.

True positive prediction form LIME on Logistic Regression Classifier
![image](https://user-images.githubusercontent.com/28870788/137401687-0776e417-7395-4696-8e20-5da540b864e3.png)
Explanation of True Positive Result from LIME: The serum creatinine, ejection fraction, and high blood pressure positively correlate with positive death event. Major contributors creatinine levels and ejection fraction are the indicators leading to a prediction that the patient will suffer a death event. 

True negative prediction form LIME on Logistic Regression Classifier
![image](https://user-images.githubusercontent.com/28870788/137404529-65a6e374-4a2a-48a5-93dd-108435ad885c.png)
Explanation of True Negative Result from LIME:For this case, the patient has higher serum creatinine levels and also falls in the age that correlates positively with the 'positive' death event. However, the ejection fraction has also similar correlation but with 'negative' death event along with contributions from other parameters such as high blood presssure therefore, the model predicts that it would not lead to death.

False positive prediction from LIME on Logistic Regression Classifier
![image](https://user-images.githubusercontent.com/28870788/137405070-62167ebb-4bb4-4af3-8c3a-62a801e7d391.png)
 Explaination of False Positive Result from LIME: Even though the ejection fraction is high but since the creatinine levels are also high (in the range of 'dead' class) the model predicts that it will result in death

False negative prediction from LIME on Logistic Regression Classifier
![image](https://user-images.githubusercontent.com/28870788/137405153-24e8dcd9-20b1-4050-be5e-299e4edb67b4.png)
Explanation of False Negative Result from LIME: Even though the ejection fraction is low but since the creatinine levels are low (in the range of 'alive' class) the model predicts that it will not result in death

# Conclusion
Using LIME we are able to explain why the model predicts that a given case will lead to a death event and what are the crucial parameters responsbile for resulting in a positive or negative prediction. 

# References
- “Why Should I Trust You?” Explaining the Predictions of Any Classifier (KDD2016) by Marco Tulio Ribeiro, Sameer Singh, and Carlos Guestrin
http://arxiv.org/pdf/1602.04938.pdf
- Explain Your Model with LIME, https://medium.com/dataman-in-ai/explain-your-model-with-lime-5a1a5867b423
- LIME: How to Interpret Machine Learning Models With Python, https://towardsdatascience.com/lime-how-to-interpret-machine-learning-models-with-python-94b0e7e4432e
- Dataset: https://archive.ics.uci.edu/ml/datasets/Heart+failure+clinical+records
