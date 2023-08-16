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

- Deep Learning combined with Classic ML Techniques
  - [BERTopic](https://maartengr.github.io/BERTopic/algorithm/algorithm.html#visual-overview)
    - Embed Documents: Converts documents to numerical representations Default: Sentence Transformers = "all-MiniLM-L6-v2" 
    - Dimensionality Reduction: After creating numerical representations of docs dimensionality reduction needs to occur to deal with curse of dimensionality. Default: UMAP
    - Cluster Documents: HDBSCAN used because it can identify outliers and finds clusters of different shapes.  
    - Bag-of-Words: To get a topic representation technique that makes little to no assumption on the expected structure of the clusters. It combines all documents in a cluster into a single document and counts how often each word appears in each cluster. Default: CountVectorizer. 
    - Topic representation: From the generated bag-of-words representation, we want to know what makes one cluster different from another. Which words are typical for cluster 1 and not so much for all other clusters? TF-IDF is used, but modified so that it considers topics (i.e., clusters) instead of documents. 

- Fine Tune the Topic Representation (the c-TF-IDF topics)
Determine if/how this can be improved with these models:

    - BERTopic + keyBERTInspired: Can increase the coherence and reduces stopwords from the resulting topic representations
    - BERTopic + OpenAI: Can be a more powerful way to describe the clusters. ChatGPT or other models can generate lables, summaries, phrases, keywords and more. 

<ins>How will model performance be determined?</ins>
- Each model will be scored based on how humans interpret the coherence of the topics. 
- Within each model, a random sampling of content is taken from each topic. 'Intruder' content is randomly injected into this content. Humans are asked to identify the intruder content. Scoring is based on how many times humans can correctly identify the intruder content. This indicates the strength of coherence of a topic that an algorithm creates.   


