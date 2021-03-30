Highest Frequency v. TFIDF
- What is TFIDF?
    - The **Term Frequency** of a word in a document. There are several ways of calculating this frequency, with the simplest being a raw count of instances a word appears in a document. Then, there are ways to adjust the frequency, by length of a document, or by the raw frequency of the most frequent word in a document.
    - The **Inverse Document Frequency** of the word across a set of documents. This means, how common or rare a word is in the entire document set. The closer it is to 0, the more common a word is. This metric can be calculated by taking the total number of documents, dividing it by the number of documents that contain a word, and calculating the logarithm. So, if the word is very common and appears in many documents, this number will approach 0. Otherwise, it will approach 1.
    - _tf(term,document) * idf(term,corpus)_



_Logistic Regression_
1. Logistic regression is generally the first thing you try when building a classifier and is actually used in some production environments.
    A. Advantages:
        - Fast (for training and prediction)
        - Simple (few hyperparameters)
        - Interpretable
        - Provides good probabilities
    B. Disadvantages
        - Requires feature engineering to capture non-linear relationships
        - Doesn't work for p > n (more features than data points)

_ROC Curve_

_Decision Tree Classifier_

_Random Forest Classifier_

_Gradient Boosting Classifier_
