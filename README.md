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
