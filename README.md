# ChatGPT-as-a-Text-Summarisation-Tool-to-Remove-Bias
Code, datasets, and models for the paper "ChatGPT as a Text Summarisation Tool to Remove Bias"

This is the work for the paper submitted to LREC-Coling 2024. We generated a dataset of Dinseyland reviews summarised using different prompts that is released here, alongside the code used for model building and evaluation, as well as McNemar's Test.

The sample of reviews was taken from a Kaggle dataset here [Disneyland Reviews](https://www.kaggle.com/datasets/arushchillar/disneyland-reviews). Each review was summarised by [ChatGPT](https://chat.openai.com/) using the Google Sheets extension [Coefficient](https://coefficient.io/). The dataset is released here as [DinseylandReviews](DinseylandReviews.csv), and it contains the following features:

* `reviewerLocation`- The sensitive attribute which was country of origin of the reviewer. This was filtered to only have people from the either `Australia`, `United Kingdom`, or `United States`.
* `originalReview`- The original review text which was summarised.
* `summary`- The default summary output, where ChatGPT generated a summary of reasonable length
* `formal`- This is the output from ChatGPT using 'Formal' as the format input.
* `informal`- This is the output from ChatGPT using 'Informal' as the format input.
* `americanEnglish`- This is the output from ChatGPT using 'American English' as the format input.
* `britishEnglish`- This is the output from ChatGPT using 'British English' as the format input.
* `australianEnglish`- This is the output from ChatGPT using 'Australian English' as the format input.
* `yorkshire`- This is the output from ChatGPT using 'Yorkshire' as the format input.
* `factual`- This is the output from ChatGPT using 'Factual' as the format input.

A number of tests were completed on this data such as sentiment analysis to check the reviews kept the same meaning and classification of the reviews into one of the three protected characteristics (Australia, UK or US). The code used for model training and evaluation is seen in [DisneyDataModels](DisneyDataModels.ipynb). Text was preprocessed, and five machine learning models were used- Naïve Bayes, Logistic Regression, Support Vector Classifier, Random Forest, and XGBoost. Word Importance was also assessed within this notebook. The statistical tests were performed using the code seen in [DisneyDataMcNemarsTest](DisneyDataMcNemarsTest.ipynb). Code for importing of datasets and results dictionaries has been removed for anonymity.
