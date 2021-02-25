# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Capstone Project - Amazon Reviews


### Problem Statement

User reviews on products and services can often provide potentially valuable feedback to sellers and service providers on various business related areas.  At the very least, for instance, the reviews could signal potential problems with the manufacture of goods, a dip in the quality of services, or some issues with deliveries.  Additionally, they could also provide business owners with many ideas on how to improve products and services.  Better than that, they could even sometimes provide them with ideas of new products or services that already have a demand.

The goal is to build a classification model to categorize reviews into meaningful multi-classes, and help inform on the multiple product aspects that customers find below par, meet expectations or lacking in certain regards.

Sentiment analysis merely attempts to see if a review is positive or negative.  While this is helpful, it only tells business owners the proportion of buyers who were happy or unsatisfied with their purchases.  This model will help the business owner gain more meaningful insights about their products and more.

---


### Executive Summary

It seems thus far, that projects undertaken on the Amazon reviews dataset have mostly been about sentiment analysis.  Only recently, few have created recommender systems to recommend similar products to returning customers.  The objective of this undertaking is to try to classify the huge amount of review information, and to see if they lead to valuable insights that might aid business owners.

Some of the insights I hope to gain through this work include, easily interpreted details, such as, (i) if delays in deliveries were encountered, (ii) if defects or damage in products were found, and so on.  At a deeper level, this project would be considered extremely successful, if for instance, patterns or trends in demand of products can be inferred from the classified or categorized information.

The approach of this endeavour is as follows:

1. [Obtain and Preprocess Data](./code/01-obtain-preprocess.ipynb)
 - Inspect the Data
 - Identify Needed Data Items
 - Remove Duplicates
 - Remove Unwanted Text
 - Replace Missing Data
 - Remove Incomplete Records
 - Tokenize and Lemmatize
 - Remove Stop Words
2. [Model and Evaluate](./code/02-topic-modelling-lda.ipynb)
 - Identify LDA Model
 - Create Term ID Dictionary
 - Create Documents Corpus
 - Determine Number of Topics
 - Run Model
 - Run Comparison Model
 - Compute and Compare Coherence Score
 - Analyze Results
 - Plot Visualizations
 - Examine Topic and Document Keywords
3. [More Visualizations](03-visualizations.ipynb)
 - Plot and Analyze
4. [Transformer Demo](04-transformers-demo.ipynb)
 - Create Demo

---


### Conclusions and Recommendations

The results were promising, but further iterations of this work would be required if more meaningful insights are to be gained.  The biggest challenge of this project was the lack of computing power and hardware memory needed to process the huge amount of review data.  Not only did this delay the progress of the project, it also limited the amount of data that could be included in the topic modelling.  Data from over 200 million reviews from Amazon were available.  However, due to processing constraints, I could only work with about one percent of the data.

Key factors leading to a good segregation of topics include the following:

 - Quality of text processing
 - Variety of topics covered in the text
 - Choice of modelling algorithm
 - Number of topics parameter provided to the algorithm
 - Tunning parameters of the algorithm

Of the factors listed above, the lack of variety of topics covered in the available data contributed to the fair results.  Consequently, inferring meaningful insights from the classification results was less helpful that hoped.

The lack of processing power also prevented the tunning of hyperparameters because the time required to run the models multiple times would be unacceptable in meeting the deadline.

Utilizing and retraining pretrained models would be explored in future iterations

---


### Provided Data

The following data files were obtained from [this](http://deepyeti.ucsd.edu/jianmo/amazon/index.html) website:

- [Review data on Tools and Home Improvement](./data/Tools_and_Home_Improvement_5.json.gz)
- [Product data on Tools and Home Improvement](./data/meta_Tools_and_Home_Improvement.json.gz)

There are approximately 2 mil rows of review data and 570, 000 rows of product data.  However, a quarter of the review data were subsequently dropped due to duplicates or missing data.

---


### Data Dictionary

#### Review Data

|Column|Data Type|Description|
|:--|:--|:--|
|`overall`|float|Rating of the product|
|`verified`|object|If review has been verified|
|`reviewTime`|object|Time of the review (raw)|
|`reviewerID`|object|ID of the reviewer e.g. A2SUAM1J3GNN3B|
|`asin`|object|ID of the product e.g. 0000013714|
|`style`|object|Dictionary of the product metadata e.g. "Format" is "Hardcover"|
|`reviewerName`|object|Name of the reviewer|
|`reviewText`|object|Text of the review|
|`summary`|float|Summary of the review|
|`unixReviewTime`|integer|Time of the review (unix time)|
|`vote`|object|Helpful votes of the review|
|`image`|object|Images that users post after they have received the product|

#### Product Data

|Column|Data Type|Description|
|:--|:--|:--|
|`category`|object|List of categories the product belongs to|
|`tech1`|object|First technical detail table of the product|
|`description`|object|Description of the product|
|`fit`|object||
|`title`|object|Name of the product|
|`also_buy`|object|Related products (also bought, also viewed, bought together, buy after viewing)|
|`image`|object|url of the product image|
|`tech2`|object|Second technical detail table of the product|
|`brand`|object|Brand name|
|`feature`|object|Bullet-point format features of the product|
|`rank`|object|Sales rank information|
|`also_view`|object|images that users post after they have received the product|
|`main_cat`|object|Main category of the product|
|`similar_item`|object|similar product table|
|`date`|object|Date|
|`price`|object|Price in US dollars (at time of crawl)|
|`asin`|object|ID of the product, e.g. 0000031852|
|`details`|object|images that users post after they have received the product|

---


### Contents

Technical report submitted and hosted on Github Enterprise. Content structure as follows::

- A project README.md
- Three Jupyter notebooks with analysis in the **code** sub folder
- Presentation slides: _Amazon Review Classification.pdf_
- Data files in the **data** sub folder

```


capstone
|__ code
|   |__ 01-obtain-preprocess.ipynb
|   |__ 02-topic-modelling-lda.ipynb
|   |__ 03-visualizations.ipynb
|   |__ 04-transformers-demo.ipynb
|__ data
|   |__ Tools_and_Home_Improvement_5.json.gz
|   |__ meta_Tools_and_Home_Improvement.json.gz
|   |__ keywords_lda.csv
|   |__ reviews_clean.csv
|   |__ reviews_demo.csv
|   |__ reviews_lda.csv
|   |__ top3docs.csv
|   |__ topics_lda.csv
|__ ldavis
|   |__ ldavis_bigrams_30
|   |__ ldavis_bigrams_30.html
|__ Amazon Review Classification.pdf
|__ README.md

```

---


### References

[Topic Modeling with Gensim (Python) by Selva Prabhakaran](https://www.machinelearningplus.com/nlp/topic-modeling-gensim-python/)

[Topic modeling visualization – How to present the results of LDA models?
by Selva Prabhakaran](https://www.machinelearningplus.com/nlp/topic-modeling-visualization-how-to-present-results-lda-models/)

[Comparison of Variational Bayes and Gibbs Sampling in Reconstruction of Missing Values with  Probabilistic Principal Component Analysis](https://users.ics.aalto.fi/praiko/papers/step10.pdf)

[Evaluate Topic Models: Latent Dirichlet Allocation (LDA) - A step-by-step guide to building interpretable topic models](https://towardsdatascience.com/evaluate-topic-model-in-python-latent-dirichlet-allocation-lda-7d57484bb5d0)

[T-distributed Stochastic Neighbor Embedding(t-SNE) - Learn the basics of t-SNE, how it is different than PCA and how to apply t- SNE on MNIST dataset](https://towardsdatascience.com/t-distributed-stochastic-neighbor-embedding-t-sne-bb60ff109561)

[How do Transformers Work in NLP? A Guide to the Latest State-of-the-Art Models](https://www.analyticsvidhya.com/blog/2019/06/understanding-transformers-nlp-state-of-the-art-models/)

---
