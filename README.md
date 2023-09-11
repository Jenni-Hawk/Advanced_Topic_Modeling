# Advanced_Topic_Modeling Research

## Objectives: 
- Conducting research on topic modeling algorithms to determine which can best uncover topics while delivering high human coherency. 
- Goal is to increase confidence in business decision making when using topic modeling algorithms to understand consumers. 
- Algorithms being tested: BERTopic, keyBERT, BERTopic + OpenAI, BERTopic + Llama 2, and classic LSA with TF-IDF
- What are the pros / cons that emerge through the process? 

## Methodology:
This advanced topic modeling research project is an expansion of a classic NLP [project](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/NLP_Presentation.pdf) that was conducted last year. LSA with TF-IDF was intuitively the best performing of the traditional NLP models and will be in this research study as a starting point to compare more advanced modeling techniques. 

<ins>How will performance of each model be determined?</ins>
- Each model will be scored based on how well humans interpret the coherence of the topics.
- Within each model, a random sampling of content is taken from each topic. 'Intruder' content is randomly injected into this content. Humans are asked to identify the intruder content. Scoring is based on how many times humans can correctly identify the intruder content. This indicates the strength of coherence of a topic that an algorithm creates.   

#### Algorithms Researched:
- LSA with TF-IDF  
- [BERTopic](https://maartengr.github.io/BERTopic/algorithm/algorithm.html#visual-overview) with Sentence Transformers 
- BERTopic with [keyBERTInspired](https://maartengr.github.io/BERTopic/api/representation/keybert.html#bertopic.representation._keybert.KeyBERTInspired.__init__) Can increase the coherence and reduces stopwords from the resulting topic representations
- BERTopic + OpenAI: Can be a more powerful way to describe the clusters. ChatGPT or other models can generate lables, summaries, phrases, keywords and more.
- BERTopic + Llama 2




