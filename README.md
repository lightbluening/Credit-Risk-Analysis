# **Credit Card Fraud Detection**

> **Source:**https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?datasetId=310&sortBy=voteCount
![image](https://github.com/lightbluening/Credit-Risk-Analysis/assets/93415125/3a00a0f2-871c-47ea-ab4c-c1d28ba4cad7)


# **Background**
Credit card fraud can lead to financial losses for individuals and damage their credit scores. By analyzing fraud patterns, financial institutions can identify suspicious transactions and protect their customers from potential losses. Credit card fraud can have a significant impact on businesses, leading to lost revenue and damaged reputation. Fraud analysis helps businesses detect and prevent fraudulent activities, reducing financial risks.Analyzing credit card fraud helps financial institutions and merchants assess and manage risks associated with fraudulent transactions. This enables them to implement appropriate security measures and fraud prevention strategies.

#  **About Dataset**


It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.

The dataset in question comprises credit card transactions executed by European cardholders in September 2013. It encapsulates **284,807** transactions that transpired within a span of two days, of which only **492** were fraudulent. This dataset presents a substantial imbalance, as fraudulent transactions represent a mere **0.17%** of all the transactions.

The dataset incorporates numerical input variables that have been derived from a PCA transformation. The attributes V1, V2, ..., V28 are the primary components achieved through PCA, whereas 'Time' and 'Amount' remain as the untransformed original features. 'Time' denotes the seconds that have passed between each transaction and the inaugural transaction in the dataset, while 'Amount' corresponds to the value of the transaction. The 'Class' attribute serves as the response variable, assuming the value 1 in instances of fraud and 0 otherwise.

# Challenge of the Analysis

**Imbalanced Data**

The biggest challenge of this analysis is how to deal with **imbalanced data**, as the **fraudulent transaction only accounts for 0.17% of the dataset**. If we use the undersampling method, 99% of the majority data will be dropped, leading to potential inaccuracies in the training data. Therefore, we opt for the **SMOTE oversampling method**. SMOTE (Synthetic Minority Oversampling Technique) is employed to generate synthetic elements for the minority class. This technique works by selecting examples closely located in the feature space, creating a line between them, and generating new samples along that line. However, it is important to consider that the oversampling method may result in higher computation costs, so we should carefully consider which algorithms to use when building models.

**Evaluation Metrics to Choose**

In the context of imbalanced datasets, where the majority class (genuine transactions) heavily outweighs the minority class (fraudulent transactions), the overall accuracy can be misleading and not a reliable performance metric. Instead, it's crucial to focus on metrics that specifically evaluate the model's ability to correctly identify fraud instances.

The three main metrics that are commonly used in such cases are:

**Precision**: Precision measures the proportion of correctly identified fraud cases (true positives) out of all the cases predicted as fraud (true positives + false positives). It represents how well the model avoids false positives (misclassifying genuine transactions as fraud). Higher precision indicates that the model is more accurate in detecting fraud.

**Recall** (Sensitivity or True Positive Rate): Recall measures the proportion of correctly identified fraud cases (true positives) out of all the actual fraud cases (true positives + false negatives). It represents the model's ability to capture the majority of actual fraud cases. Higher recall indicates that the model is better at identifying fraud instances.

**F1-score**: The F1-score is the harmonic mean of precision and recall. It provides a single metric that balances both precision and recall. The F1-score is useful when you need a balance between precision and recall and want to assess the overall performance of the model.

In cases of imbalanced datasets, especially in credit card fraud analysis, where correctly identifying fraud is of utmost importance, precision, recall, and F1-score are more relevant and meaningful metrics compared to overall accuracy.
