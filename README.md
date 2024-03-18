# Advanced_Topic_Modeling Research

## Background:
This advanced topic modeling research project is an expansion of a classic NLP [project](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/NLP_Presentation.pdf) that I conducted that uncovered the key topics amongst 34,000 tweets. At that time, LSA with TF-IDF was  the best performing of the traditional NLP models. Given the rapid pace of NLP advancements it was important to test newer, more modern algorithms. Various sentence transformers and LLMs were also tested.

## Objectives: 
- Increase confidence in business decision making when using topic modeling algorithms to understand consumers. 
- Conduct research on topic modeling algorithms to determine which can best uncover topics and deliver high human coherency. 

#### Algorithms Tested Against Each Other:
- LSA with TF-IDF
- [BERTopic + GPT4](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/BERTopic_GPT4_retweets_copy.ipynb)
- BERTopic + Llama 2
- Sentence Transformers Tested
  - all-MiniLM-L6-v2
  - BAII/bge-small-en

#### How will performance of each model be determined?</ins>
- LSA vs BERTopic will be quantitatively scored based on how well humans interpret the coherence of topics.
- For each model, a random sampling of content is taken from each topic. 'Intruder' content is randomly injected into each topic. Humans are asked to identify the intruder content. Scoring is based correctly identify the intruder content. This indicates the strength of coherence of a topic that an algorithm creates.
  - [BERTopic Scoring](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/BERTopic_Scoring_WITH_RETWEETS.ipynb)
  - [LSA Scoring](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/LSA_Scoring_WITH_RETWEETS_Intruders.ipynb)
- The results can be found in this case [case study](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Tweets%20Case%20Study%20Tech.pdf)




