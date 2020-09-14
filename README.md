# Airbnb-DC-analysis

A simple eda exploration of Airbnb reviews and listing details to gain understand what factors are important to customer. 

## Introduction
AirBnB is a platform economy that facilitate digital interactions between real estate owners and
customers for short to mid-term stay. The aim of the project is to explore AirBnB’s in Washington
DC and gain a better understanding:

1. What do users care about during their AirBnB Stay?
2. What factors affect listing price of an AirBnB listing?

This first part of the project aims to look at the reviews left by customers and try to gain an
understanding what factors do customer care in choosing airbnb listings. While the second part looks to understand what are the relationship that affects the price
per night for listing in Washington DC by analysis the listings.csv file in InsideAirBnB dataset.
## Data

The <a href = http://insideairbnb.com> data set <a> is published by Insideairbnb, an independent non-commerical set of data that is obtained by scrapping public avaliable information on the Airbnb listing and website. The following data collects various locations around the world, but for this analysis I have focused on Washington DC Airbnb listings. 

### Metadata
Reviews dataset

 | Variable | Description |
| --- | --- |
| `Listing id` | Unique Id for the Airbnb listing |
| `id` | Unique Id for the review/comment |
| `date` | Date of the review/comment left |
| `reviewer id` | Unqiue Id for the review |
| `reviewer` | First name of the reviewer |
| `Comments` | Contents of the review |

Listing dataset

 | Variable | Description |
| --- | --- |
| `id` | Unique ID for the listing |
| `listing url` | Link to the Airbnb listing |
| `name` | Name of the listing |
| `summary` | Brief summary of the listing |
| `neighborhood` | Neighborhood where the listing is located  |
| `Cancellation policy` | Policy for cancellation |
| `host id` | Unqiue ID for the host |
| `host name` | First name of the host |
| `host description` | Host self-description|
| `calculated host listing count` | Number of listing assoicated with unique id for the host |
| `Longitude` | longitude coordinates of listing |
| `Latitude` | latitude coordinates of listing |
| `property type` | Type of property of the listing for rent|
| `room type` | Room type of the listing for rent |
| `price` | Price per night for listing |
| `bedrooms` | Number of bedrooms  |
| `bathrooms` | Number of bathrooms|
| `beds` | Number of beds |
| `number of reviews` | Total number of review left at listing throughout it lifetime |
| `last review` | Date of the lastest review |

## Exploratory Data Analysis

To understand what customer cares about, we can infer indirectly from their reviews left on the listing. 

### Reviews

The number of reviews have slowly increased over time which in general follows the trend of Airbnb's increase in popularity over this period.

![alt text](./3_Figures/reviews.png)

From the above chart, it is well observed that the number of comments left steady increased over
the years. This can be explained with the increase popularity of AirBnB over the past decade
and the increase in the number of the listing posting in Washington DC. Though, we can observe
fluctuations of the number of reviews left during a single year. Taking a sample within a year - 2017, we can observe reviews spikes and drops throughout the
years. For example, Feb 2017 was an exceptionally warm February which cause a strong spike in
tourist visiting DC. Another example are events such as April - May 2017 - Cherry Blossom period
in DC.

![alt text](./3_Figures/review2017.png)

#### Sentiment Analysis

As there is no preclassification of reviews, we use transfer learning of a pre-trained model (VADER (Valence Aware Dictionary and sEntiment Reasoner)) which is tuned to sentiments expressed in social media to label the reviews left at Airbnb. The model generates negative, positive, and neutral score for each review and create a compound score where it classify if a review is positive or negative. 

![alt text](./3_Figures/sentiment.png)

From the above, we can observe that majority of the reviews are perceived as neutral reviews with
slight positivity, and not a lot of negative reviews. Thus this shows that most reviews left are positive things that customers like about their stays though it does not reveal too much about what. Thus we conduct topic modeling to see what are the common themes of these positive/neutral reviews. 

#### Topic modeling through LDA

To better understanding what peoplare interested, we conduct Topic modeling with LDA to cluster word groups and similar expressions that best characterize the reviews. After removing puncationas and stop words, we covert tokenize and normalize each reviews (document) and create document term matrix. Then applying LDA to find topics.

![alt text](./3_Figures/topicmodeling.png)

To determine the optimal number of topics, we calculate the coherence score (which assses the quality of the learn topics) and conduct a grid search by repeating the process for various number of topics.

![alt text](./3_Figures/optimal.png)

As the coherence score does not linear increase, we choose the value that elbow value before the high fluctuation of coherence score (6 topics). The results are these following six cluster of words.

![alt text](./3_Figures/lda.png)

which we then look through the words and assign a topic to these six clusters of words respectively:

![alt text](./3_Figures/topic.png)

From the Topic modelling, we find that user talks a lot about Airbnb location, and the experience during the stay. This is further reinforced with the description of the listing with location of the Airbnb / nearby sightseeing locations as the most common words used. 

### Listing

#### Location

#### Apartment Type

#### Summary wordcloud

## Implications and Future Improvements

