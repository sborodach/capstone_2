### Speeches of the United Nations General Assembly:
##### Predicting Pre/Post Cold War Era & Speech Topics

### Purpose
The United Nations General Assembly is the central deliberative, policy-making, and representative organ of the United Nations. The UNGA is responsible for the UN budget, appointing the non-permanent members to the Security Council, appointing the Secretary-General of the United Nations, receiving reports from other parts of the UN system,  making recommendations through resolutions, among other functions it serves. The UNGA is the only UN organ wherein all member states have equal representation. Annual sessions are held under its president or secretary-general in New York City, typically from September through January until all issues are addressed. The first session was in 1946 London, including representatives of the 51 founding nations. [Source: Wikipedia](https://en.wikipedia.org/wiki/United_Nations_General_Assembly)

_WordCount Vectorizer v. TFIDF Vectorizer_
    - The **Term Frequency** of a word in a document. There are several ways of calculating this frequency, with the simplest being a raw count of instances a word appears in a document. Then, there are ways to adjust the frequency, by length of a document, or by the raw frequency of the most frequent word in a document.  
    - The **Inverse Document Frequency** of the word across a set of documents. This means, how common or rare a word is in the entire document set. The closer it is to 0, the more common a word is. This metric can be calculated by taking the total number of documents, dividing it by the number of documents that contain a word, and calculating the logarithm. So, if the word is very common and appears in many documents, this number will approach 0. Otherwise, it will approach 1.  
    - _tf(term,document) * idf(term,corpus)_  

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
    - **Guido de Marco** Guido de Marco President of the UN General Assembly in 1990  
    - **Javier Pérez de Cuéllar** was the Secratary General of the UN from '82-'91  
    - **detente** Most often, the term is used for a phase of the Cold War. It was the policy of relaxing tensions between the Soviet Union and the West, as promoted by Richard Nixon, Henry Kissinger and Leonid Brezhnev, between 1969 and 1974.  
    - **Cyprus**  
    - **Waldheim** Kurt Waldheim, Secratary General of the UN from '72-'81  
    - **425, 435, & 1978** Security Council Resolution 425 and Resoltuion 435 both in 1978  
    - **Somalia**
    - **millennium**

_NLP predictions_  
    1. Models  
        a. _Logistic Regression_  
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
        b. _Decision Tree Classifier  
            i. The Decision Tree Classifier consistenyl performed poorer both the Random Forest and Gradient Boosting  
        c. _Random Forest Classifier_  
        d. _Gradient Boosting Classifier_  

        _ROC Curve_ + other evaulation metrics  
        
Unsupervised Learning  
    1. Kmeans  
        A. one outlier, turned out to be a document of symbols or encoded text. ditch it.  
    3. Topic Modelling  
  
NLP predicting on topics  
    - display elbow graph  
    - illustrate progression of increasing n_components  
  
Investigating incorrectly predicted documents  
  
