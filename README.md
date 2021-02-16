# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Capstone Project - Amazon Reviews


### Problem Statement

User reviews on products and services can often provide potentially valuable feedback to sellers and service providers on various business related areas.  At the very least, for instance, the reviews could signal potential problems with the manufacture of goods, a dip in the quality of services, or some issues with deliveries.  Additionally, they could also provide business owners with many ideas on how to improve products and services.  Better than that, they could even sometimes provide them with ideas of new products or services that already have a demand.

The goal is to build a classification model to categorize reviews into meaningful multi-classes, and help inform on the multiple product aspects that customers find below par, meet expectations or lacking in certain regards.

Sentiment analysis merely attempts to see if a review is positive or negative.  While this is helpful, it only tells business owners the proportion of buyers who were happy or unsatisfied with their purchases.  This model will help the business owner gain more meaningful insights about their products and more.

---


### Executive Summary

In order for the website to stay ahead of the pack and be the number one online sports hub, it needs to keep abreast with the sports fans and subscribers and stay informed on the latest trending news and updates in the sports world.  Extracting such information from social media sites, forums and communities is essential for any company that wants to stay ahead of the competition.  Unfortunately, many firms lacked efficient support systems to fulfill this requirement.  Your company has been paying a high price trying to fill this gap with less efficient methods, which to be honest, is not sustainable.

Fortunately, you have come to your senses and is ready to make changes to improve the situation and increase earnings.  We have the unique solution that you have been seeking to improve operations and processes.  We can help you solve the problem of not being able to deliver the latest information to your creative teams and help them produce quality content for your subscribers faster and keep them for longer.

We have the ideal solution for you in the form of a machine learning model.  This model would enable your operations team to automate the data extraction and classifcation process at a much faster pace and accuracy.  Allowing them to deliver the valuable information to where it is most needed, and allow your other departments to collaborate better in working towards your company's goals.

We are an establish company that has been specializing in what we do over the past decade at helping companies like yours to be in the forefront of the competition.  We deliver solutions that benefit companies and produce significant results.

---


### Conclusions and Recommendations


At the end, the findings and modelling results turned out much better than expected.  Looking at the findings during EDA, it became quite clear that the results would be good.  This was upon the discovery that there were a sufficent number of words that were unique to each forum.  Basketball player names in the NBA forum and football club names in the Premier League forum.  For this reason alone, it would be hard to imagine that the classification models would perform poorly.

One area in which the number of unique words for each forum can be increased would be to improve the tokenization algorithm.  Acronyms and abbreviated words,  especially if hyphenated, can be better handled during tokenization.  When creating regular expressions, I faced difficulty in creating an expression that would allow the tokenizer to tokenize hyphenated words.

Another way that could improve generalisation results, would be to increase the level of the n-grams parameter to the CountVectorizer.  The default is one.  Even after grid search optimization it remained at one.  This was very likely due to the fact that the model was already getting very good results given the dataset.  We could try to make the model more robust by scraping data from forums that are more closely related and less likely to have unique words specific to each forum.

The module that could do with the greatest improvement would be the web scraping API calls.  The current method is a very primitive way to get the job done.  There are already better APIs and libraries available without the 1000 record limitation.

In summary, both models compared produced very good results and would serve the intended purpose very well.  It would be interesting to try to adapt the models to become a multi-class classifier and work with data from more than two forums.

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
|   |__ 02-topic-modelling.ipynb
|   |__ 03-transformers.ipynb
|__ data
|   |__ Tools_and_Home_Improvement_5.json.gz
|   |__ meta_Tools_and_Home_Improvement.json.gz
|__ Amazon Review Classification.pdf
|__ README.md

```
