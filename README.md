# MSCS_634_Project4Deliverable_1
## Dataset Summary

The Bike Sharing Dataset (UCI Machine Learning Repository) contains hourly and daily rental data spanning 2011–2012 for a bike rental service.

Size: 17,379 hourly records (2 years).

Attributes (16 total):

Date/Time: dteday, hr

Weather & Season: season, weathersit, temp, atemp, hum, windspeed

Calendar: holiday, weekday, workingday

Users: casual, registered, cnt (total rentals)

This dataset was chosen because it:
 1. Exceeds the size requirement (>500 records, 10+ features)
 
 2. Offers numerical & categorical features suitable for regression, classification, clustering
 
 3. Provides real-world patterns (seasonality, weather effects, user behavior)

## Data Cleaning Steps

Missing values

Checked all columns → no missing values detected.

Duplicates

Verified dataset → no duplicate rows.

Data consistency

humidity, temp, windspeed confirmed within normalized [0,1] ranges.

Created month from dteday for seasonal analysis.

Outliers

Identified occasional spikes in rental counts (cnt) but retained them, as they represent real high-demand hours (e.g., events/holidays).

## Exploratory Data Analysis (Key Insights)

Rental distribution: Right-skewed, most hours have low rentals but some peak periods with very high usage.

Hourly pattern: Strong commuting peaks at 8 AM and 5–6 PM on working days; weekends show flatter usage.

Seasonality: Rentals peak in summer and fall, drop in winter.

Weather effect: Rentals drop sharply in adverse weather (rain/snow).

Temperature: Strong positive correlation (~0.63) with rentals.

Humidity: Weak negative correlation with rentals.

User segmentation: Registered users dominate overall usage; casual users rise on weekends/holidays.

## Challenges & Solutions

Outliers in rental counts (cnt)

Challenge: Extreme spikes could skew regression.

Solution: Retained but noted possible log transformation in future modeling.

Temporal features

Challenge: dteday is not directly useful for modeling.

Solution: Engineered month and hour features to capture seasonality and daily cycles.

Multicollinearity

Challenge: temp and atemp are highly correlated.

Solution: Will consider dropping or combining during modeling.
