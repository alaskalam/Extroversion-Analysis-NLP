# Module 5 Final Project

## Introduction

We are aiming to better understand possible differences in online writing style between introverts and extroverts, writing conversationally about themselves.

By creating a model that can accurately predict the level of extroversion/introversion based on text data, we can:

Create foundation for more comprehensive friendship-algorithm
Capitalize on marketing demographics and potentially A/B test different strategies

## Methodology
Analyze past text-data written on a forum for talking about your life experiences

### The dataset
We used the dataset from Personality Cafe.net, which contains the following datapoints.

#### personality_type = self reported MBTI personality type, ie "ENTJ"
#### posts = raw text of all of the posts a given user has made on this website

We also explored some OkCupid profile data.

You can view both original datasets + their revised versions here https://drive.google.com/drive/folders/1mQ_QgpIFihRzBzmXSw9Y-DH_7f-Xc8qZ?usp=sharing

## The Model

We decided to focus on optimizing weighted average of F-1 scores, as mislabelling one or the other seemed to be of equal importance in this context.

We conducted models using Naive Bayes and Random Forest, and then proceeded to run SMOTE and perform hyperparameter tuning.

We then did a further exploration of the data and the differences between common phrases used by introverts/extroverts.

The best result for the classification model is below: - if the link does not work, please see the Image - Test results entry in the repo.



![My screenshot](https://raw.githubusercontent.com/alaskalam/capstone-project/template-mvp/testresults.png)


Our finished model, includes a weighted F1 score average of .72, which is higher than our prior models which approached .68. 

# Conclusions

1) When comparing all top nouns, all top adverbs, all top adjectives and all top words for each group of introverts vs extroverts, we found that the most frequently used words were quite similar between the groups, with slight variations in order. However, when the introverts and extroverts are combined, the list of top words is significantly different than either of the 2 groups' separate lists - for all top words, top nouns, etc. 

2) Since all top words are similar when comparing introverts vs extroverts, do not attempt to create separate marketing campaigns at this point

3) We can see that many of the introverts' top mutual information scores contain literary references, more so than those of the extroverts'. 

4) There is some amount of similarity between bigrams of introverts vs extroverts; however there are several phrases that are unique to each group, that do not appear in the top 50 bigrams of the other group. For example, "too" with "!" shows up very frequently relatively in the extroverts, and does not appear in the top results of introverts at all.

# Future Work

1) Explore why there is such a difference between introvert/extroverts' combined top words as one group, versus only introverts or only extroverts' top words - especially when there isn't much difference between introverts' and extroverts' separate group results.

2) Investigate further regarding the higher proportion of introverts' top mutual information scores containing literary references, as there have been prior claims of correlation between introversion and significant literary interest, though it's important to note that this is not causation. This may lead into another confounding variable.

3) Create a formula that takes into account how often each person uses introvert and extrovert's separate groups of top bigrams or bigrams with top mutual information scores, and use these numbers on further unlabelled datasets to predict their introversion / extroversion based on their texts. Particularly the OkCupid dating profile dataset from Kaggle - this contains many pieces of valuable demographic and special interest/hobby data as well that could be informative.

4) Incorporate this data as part of a larger project on building a friendship-prediction algorithm.