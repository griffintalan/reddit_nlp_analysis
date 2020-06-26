#  Campaign Selection by Reddit Comment Analysis

### Problem Statement

To use comment data from Reddit in order to classify posts as belonging to r/Conservative or r/Liberal.


### Overview

A local political donor wants to know which liberal political candidates are trending among reddit users in order to make effective donations. They want to know which are most prevelant in determining liberal vs conservative, and if there are any trends among these candidates.


### Data Preparation

Data was pulled from Reddit (r/Conservative and r/Liberal) through the Pushshift API. Word data was stripped of special characters, lower cased, lemmatized, and tokenized for analysis. [Removed], [Deleted], empty, and null posts were not collected for the analysis. 


---

### Data

|Feature|Type|Description|
|---|---|---|
|**title**|*object*|Title text from a post| 
|**selftext**|*object*|Post text|
|**all_text**|*object*|Combined title and selftext|
|**num_comments**|*int*|Number of comments on a post|
|**days_old**|*int*|Age of post in days from analysis|
|**score**|*int*|Upvote score|
|**all_text_length**|*int*|Length of all_text field|
|**title_length**|*int*|Length of title field|
|**selftext_length**|*int*|Length of selftext field|
|**log_all_text_length**|*float*|Logarithm of the all_text_length field|
|**is_liberal**|*boolean*|Boolean value of 1 for r/Liberal and 0 for r/Conservative|



These data were cleaned and engineered for analysis and exported as cleaned CSV files prior to analysis.

- [r/Conservative Data](./data/conservative_data.csv)
- [r/Liberal Data](./data/liberal_data.csv)
- [Combined Data](./data/combined_data.csv)


### Cleaning and EDA, Model Evaluation, and Outcomes

- [Data Wrangling and EDA](./code/1_data_wrangling_and_EDA.ipynb)
- [Language Processing and Model Selection](./code/2_language_processing_and_model_selection.ipynb)
- [Production Models and Outcomes](./code/3_production_model_outcomes.ipynb)



### Candidate Analysis and Conclusions

According to results from the coefficients of the Naive Baye's Bernoulli Model, the suggested candidate for funding would be Nabilah Islam. Her name has the highest association with the target variable 'is_liberal' and is an active candidate in the 2020 House of Representatives race in Georgia. A second suggestion is to focus on southern states. Five out of six of the top names associated with democrats were from the south. Only Tomas Ramos of New York didn't fit this description and he had the lowest Bernoulli coefficient of the group.

### Next Steps and Limitations of Analysis

The performance of the Bernoulli model was not ideal due to the correlation between features. Another model type, such as a decision tree classifier(random or extra) could be used to delineate these features for a better feature analysis.

---

### References

[Nabilah Islam - Ballotpedia](https://ballotpedia.org/Nabilah_Islam)

[Jensen Bohren - Ballotpedia](https://ballotpedia.org/Jensen_Bohren)

[Bob Moser - MacMillan Publishers](https://us.macmillan.com/author/bobmoser/)

[Claire McCaskill - Wikipedia](https://en.wikipedia.org/wiki/Claire_McCaskill)

[Darren Soto - Wikipedia](https://en.wikipedia.org/wiki/Darren_Soto)

[Tomas Ramos - Ballotpedia](https://ballotpedia.org/Tomas_Ramos)

[Michel Platini - Wikipedia](https://en.wikipedia.org/wiki/Michel_Platini)


