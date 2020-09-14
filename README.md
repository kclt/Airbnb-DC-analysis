# Airbnb-DC-analysis

A simple exploration of Airbnb reviews and listing details to gain understand what factors are important to customer. 

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
