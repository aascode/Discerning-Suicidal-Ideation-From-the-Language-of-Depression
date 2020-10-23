# Project 3 - Web Scraping and NLP

***Problem Statement***: Can Natural Language Processing be used to tell suicidal ideation apart from depression in a collection of electronic records?
***Target Audience***: A psychiatric treatment center is investigating the association of suicidal ideation and depression. There are a large number of incomplete health records available for clinical research on, but first they need to be encoded correctly. I have been hired to quantify the distinction between help them determine if they can automate the process.


EHR Electronic Health Records (EHR)
construction of a depression "lexicon"
Automation of text screening for depression, proactive screening for suicidality

Heightened:
### Datasets

#### Provided Data

* [`Reddit-API_Doc.html`](./data/Reddit-API_Doc.html): Pushshift API for  ([source](https://pushshift.io/) | [data dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt))

#### Additional Data
* [`depression.csv`](./data/datasets/test.csv): Subset of train.csv after cleaning in Notebook 01, saved for use in all notebooks.
* [`depression_6.csv`](./data/datasets/test.csv): Subset of data from categorical features included in Model 4, saved for Kaggle submission.
* [`depression_clean.csv`](./data/datasets/test.csv): Subset of data from categorical features included in Model 4, saved for Kaggle submission.
* [`subreddits_clean.csv`](./data/datasets/test.csv): Subset of data from categorical features included in Model 4, saved for Kaggle submission.* [`suicide_watch.csv`](./data/datasets/test.csv): Subset of data from categorical features included in Model 4, saved for Kaggle submission.* [`suicide_watch_6.csv`](./data/datasets/test.csv): Suicide data, but just the six columns of interest
 
 ### Notebook 01: Web Scraping
 
 Use the Pushshift API to scrape submissions off Reddit, specifically subreddits r/depression and r/SuicideWatch 
 
 ---
 ### Notebook 02: EDA and Data Cleaning
 
 ---
 ### Notebook 03: Model Benchmarks
 
 Main Takeaway: CountVectorizer was better at weighting the tokenized subreddit submission text than TF-IDF. 
 
 After loading the "clean" subreddit CSV from Notebook 02 into a DataFrame the data was test/train split and then after struggling to work with the entire dataset of over 200,000 rows all weekend, I took Hov's advice and broke off a random subset of the data to speed up the work flow.
 
 For no particular reason Multinomial Naive Bayes was the chosen estimator to score and hypertune the transformation of submission text in a pipline. Care was taken to identify stop-words and to analyze the most frequent words, both of the entire dataset as well as the individual subreddits.
 
 What was frustrating was no stop-words did worse then the standard 'english' CountVectorizer dictionary of stop-words, but the standard 'english' set did better than any set of words I chose. I tried to only set the top-1,000 words that were also standard stop-words and various alternatives, but they always performed worse.
 
 I think the most intersting discovery was that a direct comparison of the top 500 words in each subreddit revealed that 460 were common to both. In particular, out of the top 500 most frequent words, there were 40 that were unique to both. These 80 words I believe were primarily responsible for giving an accuracy of over 70% which, compared to the baseline null of 50% was a pretty good jump in predictive power. Lastly, I thought it was illuminating to observe that when comparing the top 1,000 words from each subreddit the ONLY word that in depression that wasn't a top 1,000 word in SuicideWatch was the word 'depression'.
 
 ---
 ### Notebook 04: Model Tuning
 In this Notebook a number of estimators were streamlined through a pipeline workflow seamlessly thanks to the help of lesson notes from the weeks prior, the notes posted on advanced piplines in the WCBC directory, and Stackoverflow. Random Forest Classifier, Logistic Regression Classifier, Support Vector Machine, and Multinomial Naive Bayes estimators are instantiated in a pipe with CountVectorizer tokenizing the subreddit text as it outperformed Termm Frequency-Inverse Document Frequency(TF-IDF) consistently, for several variations of hyperparameters.
 
 Run times were waay too long so features were limited to 1,000 with less than 20,000 randomly selected submissions. The so-called "smoothing parameter" in Naive Bayes helped a couple percent for alpha=0.01. I understand conceptually how it is necessary as a unit place holder because if a term in the test set is not in the train set, a value of zero would negate any other useful information provided by other words in the document (Reddit-submission/row). I understand how a number between 0 and 1 is appropriate but I do not know exaxclty why 0.01 is optimal.
 
 ---
 ### Notebook 05: Production Model
 
 The severity of suicidal ideation has been proposed by Beck et al. as an indicator of suicidal risk.
 
Resources:

1. Beck, A. T., Kovacs, M., & Weissman, A. (1979). Assessment of suicidal intention: The Scale for Suicide Ideation. Journal of Consulting and Clinical Psychology, 47(2), 343–352. https://doi.org/10.1037/0022-006X.47.2.343

 ---
