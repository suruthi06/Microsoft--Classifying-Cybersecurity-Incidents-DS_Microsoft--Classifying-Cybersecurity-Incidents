
# **Microsoft: Classifying Cybersecurity Incidents with Machine Learning**

## **1\. Introduction**

In this project, we aim to enhance the efficiency of **Security Operation Centers (SOC)** by developing a machine learning model capable of classifying cybersecurity incidents into three categories: **True Positive (TP)**, **Benign Positive (BP)**, and **False Positive (FP)**. This model aids SOC analysts by automating incident triage, leading to quicker identification of genuine threats and minimizing false positives. The model leverages the comprehensive **GUIDE dataset** provided by Microsoft, enriched with historical customer responses and evidence.

## **2\. Problem Statement**

Security incidents are regularly classified manually by SOC analysts, which is both time-consuming and error-prone. Misclassification (e.g., false positives) can delay response times and hinder overall security. The task is to build a machine learning model to automate this classification process, helping SOC analysts prioritize incidents efficiently.

## **3\. Dataset Overview**

The dataset used for this project is the **GUIDE dataset**, which consists of multiple levels of security data:

1. **Evidence**: Represents individual components like IP addresses, emails, and user details.  
2. **Alert**: Aggregates pieces of evidence.  
3. **Incident**: The highest level of data, representing potential security threats.

### **Key Features:**

* **45 features** including details related to the incident's context, customer responses, and metadata.  
* **Target variable**: Incident triage grade (TP, BP, FP).  
* **Data Size**: 1 million incidents, stratified into training and test sets (80%-20%).

## **4\. Project Objectives**

The main objectives of this project are:

* To develop a machine learning model capable of classifying cybersecurity incidents into the three target categories (TP, BP, FP).  
* To optimize the model's performance using appropriate preprocessing, feature engineering, and hyperparameter tuning.  
* To minimize the occurrence of false positives and ensure the model performs well on unseen test data.  
* To measure the model's effectiveness using metrics such as **Macro-F1 Score**, **Precision**,**Accuracy** and **Recall**.

## **5\. Methodology and Approach**

### **5.1 Data Preprocessing**

1. **Handling Missing Data**:  
   * Missing data was either imputed or removed based on the feature’s significance.  
2. **Feature Engineering**:  
   * Extracted the day, month, and year from timestamp features.  
   * Combined related features and generated new ones to improve predictive power.  
3. **Encoding**:  
   * Applied **Label Encoding** for categorical variables.  
4. **Scaling**:  
   * Numerical features were standardized using **StandardScaler** to ensure that values are comparable.

### **5.2 Model Selection**

1. **Baseline Models**:  
   * Started with **Decision Trees** to set performance benchmarks.  
2. **Advanced Models**:  
   * Explored **Random Forest** and **XGBoost** as advanced classifiers.  
3. **Cross-Validation**:  
   * Used **k-fold cross-validation** to ensure robust model evaluation and minimize overfitting.

### **5.3 Class Imbalance Handling**

The dataset showed class imbalances, leading to potential bias in predictions. The following techniques were employed:

* **SMOTE (Synthetic Minority Over-sampling Technique)**: Balanced the dataset by over-sampling the minority classes, which improved the model's ability to correctly predict the under-represented classes.

## 

## 

## **6\. Model Evaluation and Performance**

### 

### **6.1 Evaluation Metrics**

* **Macro-F1 Score**: Ensures equal weight is given to all classes (TP, BP, FP).  
* **Precision**: Focuses on the accuracy of positive predictions.  
* **Recall**: Emphasizes the model’s ability to detect true positives.

### **6.2 Results**

* **Training Set**:  
  * Macro-F1 Score: 95.36  
  * Precision and Recall: High across all classes.  
* **Validation Set**:  
  * Macro-F1 Score: 95.32  
  * Precision and Recall remained robust.  
* **Test Set**:  
  * After applying **SMOTE** to the **training set**, the model's performance on the **test set** decreased, with an accuracy of **72.52%**. Although SMOTE improved class balance in the training set, it introduced complexity, leading to a decline in performance on unseen data. This result suggests that while SMOTE helps with class imbalance, the model's performance without SMOTE was better on the test set.

  ### **6.3 Observations**

* The model performed well on the **training set** with a high accuracy of **95.75%**, demonstrating strong predictive capabilities across all classes.  
* On the **test set**, performance declined after applying class imbalance handling techniques, with accuracy dropping to **83.52%**. This suggests that handling class imbalance, while beneficial for addressing minority class representation, introduced additional complexity, resulting in lower performance compared to the model trained without these adjustments.


## 

## **7\. Feature Importance**

To gain insights into the model’s decision-making process, feature importance was analyzed. Method **Random Forest Classifier Feature importance** were used to identify the top features contributing to the model's predictions. The most critical features were related to incident context, customer response, and historical metadata.

### **8\. Business Impact**

Although the model shows strong performance on the training data, the decline in performance on the test set suggests that it may need further optimization before full integration into **SOC workflows**. However, the model still offers potential for improving incident classification through automation:

* **Incident Response Automation**: The model can assist SOC analysts by providing an initial automated classification of incidents. With further refinement, it could help reduce response times for critical threats by filtering out likely benign or false positives.  
* **Threat Intelligence**: While the current model shows potential, additional improvements are needed to ensure it consistently minimizes false positives and focuses on real threats. Once optimized, it can contribute to enhancing the overall security posture of enterprises.

## **9\. Conclusion**

This project successfully built a machine learning model that automates the triage process for cybersecurity incidents. By classifying incidents accurately into TP, BP, and FP, the model helps SOCs prioritize incidents, reduce false positives, and improve the security posture of organizations.

## **10\. Future Improvements**

* **Enhanced Feature Engineering**: Further exploration of derived features could improve performance.  
* **Real-time Feedback Loop**: Implementing a feedback loop with SOC analysts could help refine the model in production environments, enhancing accuracy.  
* **Additional Models**: Exploring deep learning models could further enhance prediction capabilities.

## **11\. Deliverables**

* **Source Code**: Complete codebase for data preprocessing, modeling, and evaluation.  
* **Trained Model**: The final model ready for deployment.  
* **Documentation**: Detailed project report covering methodology, performance, and business implications.

