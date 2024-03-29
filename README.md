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
- LSA vs BERTopic will be quantitatively scored based on how humans interpret the coherence of the content within the topics.
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
- From an intuitive perspective, BERTopic + GPT4 + all-MiniLM-L6-v2 appeared to deliver more accurate topic labels than Llama2 + BAII/bge-small-en. However Llama2 + BAII/bge-small-en seems to be a viable fallback for this use case if the OpenAI API isn't available.
  - A next evolution would be to implement a quantitative research study where humans determine which of the LLM topic labels are best.
    - One possible annoyance within this research workflow is the stochastic nature of OpenAI. While OpenAI promised developers a seed state for reproducibility it hadn't yet materialized when I last checked on it. 
- [Case Study: Business Audience](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Tweets%20Case%20Study%20Tech.pdf)
- [Test Summary Sheet](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Test%20Summary.pdf)

## 🎯 Additional Objective
- Determine the impact of including retweets versus removing retweets
- Findings:
  - [There's a low model coherence score](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling_Tweets/blob/main/Test%20Summary.pdf) when re-tweets are removed which means the content within each topic is not distinctly identified as belonging to a specific topic.
  - This makes sense given how people use Twitter to express themselves. Re-tweeting is a way to communicate support of an idea. Therefore, removing duplicates does not provide an accurate understanding of what the top topics are from a volume perspective. This volume perspective is critically important for business people to understand the scale and influence of a topic.
    - As a best practice for tweet analysis, I recommend removing duplicate tweets as a secondary step in the analysis process (not a first step) to double check that a latent topic doesn't exist when duplicates are removed.

## 💡 Further Work
- Upon completing this project I was inspired to further expand this knowledge and apply it to classic consumer research: The Survey.
- I wanted to challenge conventions that consumer researchers have about what's possible in analyzing responses to open ended questions, and I wanted to see how far I could push the length of text and gain accurate topic categorization.
- I was inspired to test more sentence transformers: all-mpnet-base-v2 and Cohere's Embed 3.
- I also needed to explore further AI ecosystems that can provide ease of workflow but also give me advanced GPU power
- This further work can be found [here](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling_2_Survey/blob/main/README.md)

