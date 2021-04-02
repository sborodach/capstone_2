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
    - **Shihabi** President of the UN General Assembly from '91-'91
    - **sustainable**

Word Counts v TFIDF
What is TFIDF? TFIDF is a score of each and every word in the corpus across all documents. It is tf * idf, or tf(term,document) * idf(term,corpus). The Term Frequency (TF) of a word in a document, simlpy a raw count of instances a word appears in a document. The Inverse Document Frequency (IDF) of a word across the set of documents. This means, how common or rare a word is in the entire document set. The closer it is to 0, the more common a word is. This metric is calculated by taking logarithm of the total number of documents divided by the number of documents that contain a word. So, if the word is very common and appears in many documents, this number will approach 0. Otherwise, it will approach 1.
SciKitLearn functions include both a WordCount Vectorizer and a TFIDF Vectorizer. The former is useful for displaying the distribution of words. However, when predicting on natural language, generating TFIDF values for the vectors provides relevance of words across documents, contextualizing them in terms of appearance in a given document, as well as across all documents in the corpus as whole.
