# Advanced_Topic_Modeling Research

## Objectives: 
- For topic modeling, how do deep learning models perform against classic machine learning models?
    - How does a combination of deep learning + classic ML techniques (via BERTopic building block modeling perform and what optimizations perform best on the content?  
- Which model(s) bring the best human comprehension to the topics it defines? 
- Which model(s) can make us feel most confident that they're accurately defining the topics? 
- Can OpenAI create an improvement in model performance?
- What are the pros / cons that emerge through the process? 


## Methodology:
<ins>Algorithms being tested:</ins>

- Classic ML:
  - LSA with TF-IDF, 

- Deep Learning
  - Sentence Transformers + Classic ML:
    - BERTopic + keyBERT
    - BERTopic + OpenAI

How will model performance be determined? 
- Each model will be scored based on how humans interpret the coherence of the topics. 
- Within each model, a random sampling of content is taken from each topic. 'Intruder' content is randomly injected into this content. Humans are asked to identify the intruder content. Scoring is based on how many times humans can correctly identify the intruder content. This indicates the strength of coherence of a topic that an algorithm creates.   


