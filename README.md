# Advanced_Topic_Modeling Research

## Background:
This advanced topic modeling research project is an expansion of a classic NLP [project](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/NLP_Presentation.pdf) that I conducted that uncovered topics for 34,000 tweets. At that time, LSA with TF-IDF was  the best performing of the traditional NLP models. Given the rapid pace of NLP advancements it was important to test newer, more modern algorithms. In addition, different sentence transformers and LLMs were tested.

## Objectives: 
- Conduct research on topic modeling algorithms to determine which can best uncover topics and deliver high human coherency. 
- Increase confidence in business decision making when using topic modeling algorithms to understand consumers. 

#### Algorithms Tested Against Each Other:
- LSA with TF-IDF  
- BERTopic tested with various Sentence Transformers
  - BAII/bge-small-en
  - BAII/bge-large-en-v1.5
  - all-mpnet-base-v2
- BERTopic + GPT4
- BERTopic + Llama 2 

<ins>How will performance of each model be determined?</ins>
- Each model will be scored based on how well humans interpret the coherence of the topics.
- Within each model, a random sampling of content is taken from each topic. 'Intruder' content is randomly injected into this content. Humans are asked to identify the intruder content. Scoring is based on how many times humans can correctly identify the intruder content. This indicates the strength of coherence of a topic that an algorithm creates.   





