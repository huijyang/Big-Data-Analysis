# Big-Data-Analysis

Contributed by Emily Xiaoqi He, Huijing Yang, Lokendra Singh Badgujar, Sheng Zhou and Karollyne Zortea (Team Lead)

## Problem Statement
Air travel is an essential aspect of modern life, with millions of people relying on it for business, leisure, and personal connections. The fluctuating nature of flight prices, influenced by factors such as supply, demand, seasonality, and competition, often leaves travelers overwhelmed when trying to find the best deals on airfare. At the same time, airlines and travel companies are constantly seeking to optimize their pricing strategies to maximize revenues and maintain customer satisfaction. Despite the abundance of flight data available, accurately forecasting flight prices remains a challenge for both travelers and industry stakeholders. Our goal is to develop a flight price predictor that leverages big data techniques and machine learning algorithms to accurately forecast flight prices, enabling travelers to make informed decisions and save money on air travel. By providing essential information, such as departure date and time, arrival time, source and destination, number of stops, and airline name, our solution aims to empower users with the insights they need while also assisting airlines and travel companies in refining their pricing strategies.

## Flight Prices Dataset

**Data source:** https://www.kaggle.com/datasets/dilwong/flightprices

**About the dataset:** Each row of this dataset is a purchasable ticket found on Expedia between 2022-04-16 and 2022-10-05, to/from the following airports: ATL, DFW, DEN, ORD, LAX, CLT, MIA, JFK, EWR, SFO, DTW, BOS, PHL, LGA, IAD, OAK.

**Columns in this Dataset:**

|Column Name|Description|Type|
|--|--|--|
|legId|An identifier for the flight.|String|
|searchDate|The date on which this entry was taken from Expedia.|Timestamp|
|flightDate|The date of the flight.|Timestamp|
|startingAirport|Three-character IATA airport code for the initial location.|String|
|destinationAirport|Three-character IATA airport code for the arrival location.|String|
|fareBasisCode|The fare basis code.|String|
|travelDuration|The travel duration in hours and minutes.|String|
|elapsedDays|The number of elapsed days (usually 0).|Integer|
|isBasicEconomy|Indicates whether the ticket is for basic economy.|Boolean|
|isRefundable|Indicates whether the ticket is refundable.|Boolean|
|isNonStop|Indicates whether the flight is non-stop.|Boolean|
|baseFare|The price of the ticket (in USD).|Double|
|totalFare|The price of the ticket (in USD) including taxes and other fees.|Double|
|seatsRemaining|Indicates the number of seats remaining.|Integer|
|totalTravelDistance|The total travel distance in miles.|Integer|
|segmentsDepartureTimeEpochSeconds|Departure time for each leg of the trip, provided in Unix time format.|String|
|segmentsDepartureTimeRaw|The departure time for each leg of the trip.|String|
|segmentsArrivalTimeEpochSeconds|The arrival time for each leg of the trip, provided in Unix time format.|String|
|segmentsArrivalTimeRaw|The arrival time for each leg of the trip.|String|
|segmentsArrivalAirportCode|The IATA airport code for the arrival location of each leg of the trip.|String|
|segmentsDepartureAirportCode|The IATA airport code for the departure location of each leg of the trip.|String|
|segmentsAirlineName|The name of the airline that services each leg of the trip.|String|
|segmentsAirlineCode|The two-letter airline code that services each leg of the trip.|String|
|segmentsEquipmentDescription|The type of airplane used for each leg of the trip.|String|
|segmentsDurationInSeconds|The duration of the flight (in seconds) for each leg of the trip.|String|
|segmentsDistance|The distance traveled (in miles) for each leg of the trip.|String|
|segmentsCabinCode|The cabin class for each leg of the trip.|String|

## **Project Overview** 
1. Importing Necessary Libraries and Data
    1. Importing libraries 
    2. Importing CSV file
2. Data Exploration
    1. Displaying the schema
    2. Displaying the first few rows
    3. Retrieving the number of records (rows)
    4. Identifying null values
    5. Computing basic statistics on the dataset
3. Data Preparation
    1. Removing irrelevant columns
    2. Exploring "flightDate" column
    3. Converting 'flightDate' column from timestamp to date format
    4. Exploring "segmentsDepartureTimeRaw" and "segmentsArrivalTimeRaw" columns
    5. Extracting date and time from 'segmentsDepartureTimeRaw' and 'segmentsArrivalTimeRaw' columns
    6. Dropping original columns
    7. Exploring "travelDuration" column
    8. Converting "travelDuration" to hours
    9. Creating "flight_week_day" column
    10. Dropping "duration_in_seconds"
    11. Updating column names
    12. Exploring "totalTravelDistance" and "distance" columns
    13. Checking the null count by airlines in the "totalTravelDistance" column
    14. Filtering "Spirit Airlines" and checking null values in the "distance" column
    15. Dropping "distance"
    16. Counting the instances where Spirit Airlines is not null
    17. Dropping Spirits Airlines from dataset
    18. Removing null values from "totalTravelDistance"
    19. Checking for outliers
    20. Writing our dataset to parquet file
4. EDA (Exploratory Data Analysis)
    1. Importing and reading parquet file
    2. Analyzing average fare by each month
    3. Analyzing months with the most or least flights
    4. Analyzing relationship between airlines and base fare
    5. Visulizing the 10 most popular routes
    6. Visualizing the 10 least popular routes
    7. Examining the weekday with the highest frequency of flights
    8. Analyzing relationship between seats remaining and average base fare price
    9. Analyzing relationship between day of the week and number of seats remaining
    10. Analyzing dates with the most purchasable tickets
    11. Analyzing relationship between dates, day of the week and average base fare
    12. Analyzing relationship between total duration hours and average base fare
    13. Examining airlines with the highest proportion of basic economy tickets sold during weekdays
    14. Analyzing relationship between airline and number of non-stop flights
    15. Visualizing most popular traveling time block (morning(6-12), afternoon(12-18), evening(18-24), night(0-6))
    16. Checking the proportion of basic economy, refundable, and non-stop flights
    17. Checking difference in average base fare based on starting airport and destination airport
    18. Checking difference in average total distance based on starting airport and destination airport
5. Feature Engineering & Selection
    1. Dropping 'totalFare', 'departure_date', 'arrival_date', 'departure_time', 'arrival_time', 'duration_in_seconds' and 'segmentsEquipmentDescription'
    2. Handling null values
    3. Converting the boolean features to integers (0 and 1)
    4. Creating a "number of stops" column by counting the occurrences of airlines in the "airline_name" column
    5. Dropping "airline_name"
    6. Dropping "startingAirport" and "destinationAirport"
    7. Dropping "flight_week_day" as we already have the information in "flight_day" and "flight_month" columns
    8. Importing and reading clean parquet file for modeling
6. Modeling
    1. RFormula
    2. Linear Regression
    3. Lasso Regression
    4. Ridge Regression
    5. Gradient Boosted Tree
    6. Random Forest
    7. Decision Tree
    8. Hyperparameter Tuning of Gradient Boosted Tree
7. Analysis & Evaluation
8. Challenges
9. Conclusions & Recommendations
10. Citations
