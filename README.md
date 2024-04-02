## FINDINGS

The target variable is highly imbalanced with 88% being 0(customers who did not sign up for the deposit). I used cross validation to distribute the classes evenly. GridSearchCV uses kfold for classification estimators. The most explainable models are those created by the Linear SVM classifier, Logistic regression classifier, and the Decision tree classifier where you can use coefficients or the feature importance to determine which features contribute the most strongly to the models' predictions. 
- For the Decision Tree classifier , "education" and "balance" are the two most important features. 
- For the Linear SVM classifier and a Logistic regression classifier , the two most important features are "education" and "pdays".

I have use Accuracy scores, Recall, and AUC Scores. Test Accuracy is about the same at 0.89 for all the classifiers

Why Recall? This is a marketing problem and I want to focus on optimizing by having more conversations with potential leads which ultimately converts (True Positives). I do not want to risk incorrectly assuming the customer will not convert. The Recall is highest for the Decision Tree (0.47), followed by KNN (0.26). Cross Validation scores are about 0.89 for all classifiers. Mean Fit time is the worst for an SVM classifier. The Decision Tree and the KNN performs well for fit times. 

Recall = TP / TP + FN

Finding more clients which have higher chances of saying yes to subscription of term deposit , will save a lot of manhours and efforts. Predicting as many positives as possible out of actual positives from dataset is the goal here, recall has been chosen as one of the performance matrices along with accuracy and AUC score.

The Decision Tree classifier is my choice of classification algorithm because of a better Recall value and good accuracy score and fit times. Because the training and test scores are similar, the models is not overfitted. 

<b>COMPARISON OF CLASSIFIERS</b>

|Classifier|Pros|Cons|
|---|---|---|
|Logistic Regression|Simple, Fast, Interpretable, scalable by using stochastic gradient descent|Linearity Assumption, Overfitting Risk when the number of features > data samples, Lack of Automatic Feature Interaction, Sensitivity to Outliers|
|Decision Trees|Capturing Complex Relationships, Easy Interpretation and Visualization|Overfitting and instability|
|KNN|Easy to Grasp ,Eliminates Training Phase,Versatility|Increasing Computational Demands, Sensitivity to Data Density|
|SVM|Suitable for Complex Data with high number of dimensions, Flexibility with both linear and non-linear data through the Control Overfitting with regularization parameters|Memory-intensive, particularly when dealing with large datasets. Sensitivity to Noisy Data|