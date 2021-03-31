_Feature Engineering_
- 80k features to 3k

Highest Frequency v. TFIDF
- What is TFIDF?
    - The **Term Frequency** of a word in a document. There are several ways of calculating this frequency, with the simplest being a raw count of instances a word appears in a document. Then, there are ways to adjust the frequency, by length of a document, or by the raw frequency of the most frequent word in a document.
    - The **Inverse Document Frequency** of the word across a set of documents. This means, how common or rare a word is in the entire document set. The closer it is to 0, the more common a word is. This metric can be calculated by taking the total number of documents, dividing it by the number of documents that contain a word, and calculating the logarithm. So, if the word is very common and appears in many documents, this number will approach 0. Otherwise, it will approach 1.
    - _tf(term,document) * idf(term,corpus)_

_EDA_
- Some of the most common words used:
    - international, economic, development, security, peace, nations, states, united, world, people 

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
- Hard v Soft classifiers

|  | Post-War | Pre-War |
| ----- | ----- | ----- |
| **True** | 1138 | 0 | 
| **False** | 788 | 0 | 

_ROC Curve_

_Decision Tree Classifier_
Grid Search: max depth: 10 (higher results were minimal for greater depth.

_Random Forest Classifier_
    - 5 most important features: Namibia, mankind, sustainable, apartheid, Soviet
        - others with high gini importance: kampuchea, challenges, powers, millennium, detente, racist, race
    - After removing Namibia, Soviet, and Kampuchea:
        - , these were the most relevant features for each class:
        - higherst tfidf: africa', 'sustainable', 'terrorism', 'african', 'nuclear', 'european',
       'republic', 'climate', 'europe', 'south', 'arab', 'reform'
       - Most common: 
        
- Post-war: sustainable      7.197204
terrorism        6.797736
millennium       5.469565
reform           5.468989
climate          5.326580
challenges       4.835129
global           4.616302
african          4.587272
island           4.523363
globalization    4.484994
        
- Pre-war: south           4.328527
arab            3.946033
africa          3.764856
independence    3.639942
disarmament     3.604269
delegation      3.508519
nuclear         3.498518
detente         3.348977
aggression      3.295697
peoples         3.256435


_Gradient Boosting Classifier_
