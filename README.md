# Advanced_Topic_Modeling Research

## Objectives: 
- For topic modeling, how does deep learning perform against classic machine learning?
    - How does a combination of deep learning + classic ML techniques (via BERTopic building blocks) perform? What optimizations perform best given the specific content?  
- Which model(s) bring the best human comprehension to the topics it defines? 
- Which model(s) can make us feel most confident that they're accurately defining the topics? 
- Can OpenAI create an improvement in model performance?
- What are the pros / cons that emerge through the process? 


## Methodology:
<ins>Algorithms being tested:</ins>

- Classic ML:
  - LSA with TF-IDF

- Deep Learning:
  - Sentence Transformers + Classic ML:
    - BERTopic + keyBERT
        - [BERTopic Defaults](https://maartengr.github.io/BERTopic/algorithm/algorithm.html#visual-overview):
        - Embed Documents: Sentence Transformers = "all-MiniLM-L6-v2" Converts documents to numerical representations
        - Dimensionality Reduction: UMAP. After creating numerical representations of docs dimensionality reduction needs to occur to deal with curse of dimensionality. 
        - Cluster Documents: HDBSCAN used because it can identify outliers and finds clusters of different shapes.  
        - Bag-of-Words: CountVectorizer. This appproach used because it won't making any assumptions based on the expected structure of clusters. It combines all documents in a cluster into a single document. That, very long, document then represents the cluster. Count how often each word appears in each cluster. This bag-of-words representation is therefore on a cluster level and not on a document level.
        - Topic representation: c-TFIDF. From the generated bag-of-words representation, we want to know what makes one cluster different from another. Which words are typical for cluster 1 and not so much for all other clusters? To solve this, we need to modify TF-IDF such that it considers topics (i.e., clusters) instead of documents. 
- keyBERTInspired: Can increase the coherence and reduces stopwords from the resulting topic representations
- BERTopic + OpenAI: Can be a more powerful way to describe the clusters. ChatGPT or other models can generate lables, summaries, phrases, keywords and more. 

How will model performance be determined? 
- Each model will be scored based on how humans interpret the coherence of the topics. 
- Within each model, a random sampling of content is taken from each topic. 'Intruder' content is randomly injected into this content. Humans are asked to identify the intruder content. Scoring is based on how many times humans can correctly identify the intruder content. This indicates the strength of coherence of a topic that an algorithm creates.   


