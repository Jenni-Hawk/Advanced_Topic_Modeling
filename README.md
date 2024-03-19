# Advanced Topic Modeling Research: Tweets

## 📖 Background:
This advanced topic modeling research project is an expansion of a classic NLP [project](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/NLP_Presentation.pdf) that I conducted with the objective to uncover the key topics amongst 34,000 tweets. At that time, LSA with TF-IDF was the best performing of the traditional NLP models. Given the rapid pace of NLP advancements it was important to test newer, more modern algorithms and explore various sentence transformers and LLMs.

## 🎯 Primary Objectives: 
- Determine which topic modeling algorithms are more accurate to increase confidence when using them for business decisions.
- Test BERTopic versus LSA to determine, from a quantitative scoring perspective, which can deliver more accuracy.

#### Algorithms Tested Against Each Other:
- [LSA with TF-IDF](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling_Tweets/blob/main/LSA_TFIDF_TopicMod_WITH_RETWEETS.ipynb) vs [BERTopic vs KeyBERT](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling_Tweets/blob/main/BERTopic_and_KeyBERT_Model_WITH_RETWEETS.ipynb)
  - LSA: take top 75% of tweets based on probability
  - BERTopic: used all-MiniLM-L6-v2 sentence transformer
 
#### How will performance of the models be determined?</ins>
- LSA vs BERTopic will be quantitatively scored based on how well humans interpret the coherence of topics.
- For each model, a random sampling of content is taken from each topic. We'll call this "Intruder" content. "Intruder" content is randomly injected into each topic. Humans are asked to identify the intruder content. Scoring is based correctly identify the intruder content. This indicates the strength of coherence of a topic that an algorithm creates.
  - [BERTopic Scoring Code](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/BERTopic_Scoring_WITH_RETWEETS.ipynb)
  - [LSA Scoring Code](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/LSA_Scoring_WITH_RETWEETS_Intruders.ipynb)

## 🎯 Secondary Objectives: 
- Begin the exploration of how GPT4 can provide intuitive topic labels and begin to compare those labels to Llama2
  - [BERTopic + GPT4 Code](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling_Tweets/blob/main/BERTopic_GPT4_retweets_copy.ipynb)
  - [BERTopic + Llama 2 Code](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Llama2_retweets_BAAI.ipynb) (Llama-2-13b-chat-hf)
    - Begin to explore other sentence transformers: BAII/bge-small-en

## 🔍 Research Findings
- BERTopic greatly outperformed LSA on human topic [coherence scoring](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Test%20Summary.pdf)
- GPT4 appeared to be more accurate than Llama2 in delivering topic labels but Llama2 appears to be viable fallback for this use case if the OpenAI API isn't available.
  - It would be interesting to dive deeper into understanding LLM performance in topic labeling and get a quantitative understanding of this through a human preference scoring methodology. One issue arount this is the stochastic nature of OpenAI. While OpenAI promised developers a seed state for reproducibility it hadn't yet materialized when I last checked on it. 
- [Case Study: Business Audience](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Tweets%20Case%20Study%20Tech.pdf)
- [Test Summary Sheet](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Test%20Summary.pdf)

## 🎯 Additional Objective
- Determine the impact of including retweets versus removing retweets
- Findings: Given how people use Twitter to express themselves, removing duplicates does not provide an accurate understanding of what the top topics are from a volume perspective. This volume perspective is critically important for business people to understand the scale and influence of a topic. As a best practice for tweet analysis, I recommend removing duplicate tweets as a secondary step in the analysis process (not a first step) to double check that a latent topic doesn't exist when duplicates are removed. 

## 💡 Further Work
- Upon completing this project I was inspired to further expand this knowledge into areas of classic consumer research: The Survey.
- I wanted to challenge conventions that consumer researchers have about what's possible in analyzing responses to open ended questions, and I wanted to see how far I could push the length of text and gain accurate topic categorization.
- I was inspired to test more sentence transformers: all-mpnet-base-v2 and Cohere's Embed 3.
- I also wanted to explore further AI ecosystems that can provide ease of workflow but also give me advanced GPU power. 

