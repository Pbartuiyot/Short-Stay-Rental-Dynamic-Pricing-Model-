# Dynamic Pricing for Airbnb Listings in Boston using Sentiment Analysis (BERT)

# 1. Project Overview
Airbnb hosts in Boston often struggle with setting the right price for their listings. Improper pricing strategies, poor visibility, and a lack of insight into guest preferences lead to low occupancy rates and missed revenue opportunities. This project uses Natural Language Processing and machine learning to:

1)	Analyze guest reviews to extract sentiment and key factors influencing satisfaction.
2)	Understand how listing features and sentiment impact pricing.
3)	Build a dynamic pricing model to suggest optimal prices for Airbnb hosts.
4)	Provide data-driven recommendations for improving listing quality and visibility.
   
#2. Problem Statement

Unlike hotels that benefit from brand loyalty and standardized pricing, Airbnb guests primarily base their booking decisions on user reviews, host behavior, and listing descriptions or features. However, many hosts lack clear insights into the specific factors that guests value most, leading to pricing decisions that are either too high, resulting in vacant bookings or too low, which reduces profitability. Additionally, listings often fail to highlight unique amenities or nearby local attractions that could enhance guest appeal, and there is currently no systematic approach to pricing that integrates guest sentiment, proximity to attractions, or real-time demand trends.

# 3. Objectives

While key features such as amenities, host responsiveness, and location influence guest satisfaction and dictate the dynamic pricing, the primary objectives of this project include:
1)	Extract and analyze guest sentiments from Airbnb reviews using Natural Language Processing (NLP) with BERT to classify reviews as positive, neutral, or negative.
2)	Develop a dynamic pricing model that integrates sentiment scores, listing features, geographical location, and demand trends.
3)	Generate predictive insights to recommend optimal pricing strategies that maximize both occupancy and profitability.
   
# 4. Data Sources
Data is sourced from InsiderAirbnb.
There are two datasets
a)	Listing
b)	Customer reviewers

To address this issue, I will collect a dataset from an insider website which provides datasets or short-stay rentals across major cities, which offers hosts to list their short-stay rental houses and also allows customers to leave reviews and ratings. The following are characteristics of the data: 
a)	Listing Details: Title, property type (e.g., apartment, house), number of bedrooms/bathrooms, amenities (e.g., Wi-Fi, pool)
b)	Pricing: Nightly rate, discounts, service fees
c)	Location: County, city, or specific coordinates
d)	Reviews: Ratings, number of reviews, guest comments
e)	Host Information: Name, response rate, superhost status
f)	Availability: Booked/unbooked dates.

Reviews	Guest comments, ratings, number of reviews

# 5. Methodology

5.1 Data Preprocessing
•	Remove null values, duplicates, and irrelevant rows.
•	Convert text to lowercase, remove punctuation, special characters, and emojis.
•	Tokenization, stopword removal, and lemmatization using NLTK/spaCy.
•	Encode categorical data (One-Hot Encoding).
•	Standardize numerical features (price, number of bedrooms).

5.2 Sentiment Analysis
•	Pre-trained BERT model to classify reviews:
o	Negative (-1), Neutral (0), Positive (+1)
o	Come up with compound score
•	Compute average sentiment score per listing.
•	Extract keywords using TF-IDF or topic modelling (LDA).
<img width="1900" height="2065" alt="image" src="https://github.com/user-attachments/assets/1c3aecd6-ed02-4a4a-8f0f-8404f3c2af94" />

5.3 Machine Learning Model
•	Combine numerical + encoded categorical + sentiment features.
•	Train regression models:

o	Random Forest Regressor
o	XGBoost
o	Gradient Boosting
