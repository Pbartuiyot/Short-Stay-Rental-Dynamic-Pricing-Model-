
# 1. Project Overview

Airbnb hosts often struggle to set competitive prices, relying on intuition or static strategies that overlook what guests value. Guest reviews, however, contain rich insights, expressing both overall sentiment and opinions about specific aspects such as cleanliness, amenities, location, and host responsiveness.
This project combines BERT-based sentiment analysis of guest reviews with listing data to build a dynamic pricing model that recommends optimal Airbnb prices in Boston.

# 2. Objectives

Primary Objectives:

i) Build a production-ready model that recommends data-driven prices for each listing.

ii) Use BERT to extract overall and aspect-level sentiment from guest reviews.

iii)Quantify how review sentiment and listing features affect price and occupancy.

iv)Provide host-facing recommendations to improve listing appeal and visibility.

# 3. Data Sources

a) Listings dataset: Contains attributes of Boston Airbnb properties, including pricing, host details, location, property characteristics, and review scores.

b) Customer Reviews dataset: Contains listing_id and customer comments.

Join key: listing_id — datasets are combined via inner join to ensure modeling only includes listings with both listing details and reviews. One listing may have multiple reviews.

# 4. Preprocessing & Feature Engineering

Text preprocessing:

Clean reviews by removing extra spaces and fixing encoding errors.

Keep contractions and informal language (handled by BERT).

Optionally exclude very short reviews.

# 5. BERT sentiment analysis:

Fine-tune a pre-trained BERT model (e.g., bert-base-uncased) to predict overall sentiment (negative, neutral, positive) and aspect-level sentiment for features like cleanliness, Wi-Fi, or location.

Output sentiment scores and aspect-polarity pairs per review.

Aggregation & feature engineering:

Aggregate review-level outputs to the listing level: average sentiment, percentage of negative comments on key aspects, number of recent negative mentions, total review volume.

Join aggregated features with the main listings dataset.

Optional additional features: TF-IDF or LDA keywords; compound sentiment score per listing.

<img width="300" height="500" alt="image" src="https://github.com/user-attachments/assets/1c3aecd6-ed02-4a4a-8f0f-8404f3c2af94" />

# 6. Pricing Model

Goal: Predict optimal nightly price.

Potential models:

Random Forest Regressor

XGBoost

LightGBM

Gradient Boosting

Loss & metrics:

Primary: MAE, RMSE, MAPE on price

Evaluation goals:
