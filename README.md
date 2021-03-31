_Feature Engineering_
After starting out with over 80k features, those features that were included for modelling were only those that had tfidf scores1 above a certain threshold. This process limited the number of features to just over 3k. 
Further, k-means clustering resulted in identifying a single outlier that appeared consistently in its own cluster, regardless of the number of clusters. Upon inspection, this document consisted of random symbols and was thus discarded. This is actually a pleasing discovery as the total number of speeches according to the dataset documentation was 7001 and when reading in the various CSV's there were 7002. Thus we then had the correct amount of documents.
From the Random Forest, feature importances were collected. After removing the features with greatest importance due to concern that the underlying distinctions between the two classes was being overwritten by select dominant features, the models still performed very well.
    - **Namibia**  
    - **Kampuchea**  
    - **apartheid**   
    - **Soviet** Dissolution of the Soviet Union at the end of 1991  
    - **Boutros Ghali** was the secratary general of the UN from 1992-1996  
    - **Bosnia & Herzegovnia** decalared independence in 1992  
    - **thirty** refers to session numbers (thirty-eight, thirty-nine) strong influencer for classification of pre-war era  
    - **Korea**  
    - **Vietnam**  
    - **Marco** Guido de Marco President of the UN General Assembly in 1990  
    - **Cueller** Javier Pérez de Cuéllar was the Secratary General of the UN from '82-'91  
    - **detente** Most often, the term is used for a phase of the Cold War. It was the policy of relaxing tensions between the Soviet Union and the West, as promoted by Richard Nixon, Henry Kissinger and Leonid Brezhnev, between 1969 and 1974.  
    - **Cyprus**  
    - **Waldheim** Kurt Waldheim, Secratary General of the UN from '72-'81  
    - **425 & 1978** Security Council Resolution 425 in 1978  
    - 

racist, domination,
sustainable, 

1. TFIDF
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

after knocking out 1600+ speeches from the post CW era to balance out the classes, the Logistic Regression performed very well:
|  | Post-War | Pre-War |
| ----- | ----- | ----- |
| **True** | 722 | 740 | 
| **False** | 7 | 53 | 

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


_Unsuperviosed Learning_ 
- kmeans: one outlier, turned out to be a document of symbols or encoded text. ditch it. 
