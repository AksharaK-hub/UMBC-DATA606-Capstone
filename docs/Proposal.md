# Uber Fare Prediction

## 1. Title and Author

- **Project Title**: Uber Fare Prediction  
- **Prepared for**: UMBC Data Science Master Degree Capstone by Dr. Chaojie (Jay) Wang  
- **Author Name**: Akshara Kocharla  
- **GitHub Repository**: [UMBC-DATA606-Capstone](https://github.com/AksharaK-hub/UMBC-DATA606-Capstone/tree/main)  
- **LinkedIn Profile**: [Akshara Kocharla](https://www.linkedin.com/in/akshara-kocharla-303868189)  
- **PowerPoint Presentation**: [Link to Presentation]  
- **YouTube Video**: [Link to Video]  

---

## 2. Background

### What is Uber Fare Prediction?

Uber fare prediction involves estimating the cost of ridesharing services based on various factors like the time and location of pickups and drop-offs, distance traveled, demand, and other contextual variables. The model is trained using historical ride data from 2009–2015 to learn patterns and establish correlations between these features and the fare.

### Why Does It Matter?

- **Company Optimization**: Accurate fare predictions are critical to Uber’s operational efficiency, ensuring fair compensation for drivers and maintaining the balance between supply, demand, and pricing strategies.
- **Competitive Advantage**: Precise fare estimations give Uber an edge over competitors in the highly competitive ridesharing market, attracting more customers.
- **Data Insights**: Analyzing fare projections provides insights into peak demand periods, rider behavior, and the impact of external factors on pricing. This data can be leveraged for marketing and resource allocation strategies.

### Research Questions:

1. Does the time of day significantly affect the fare amount for Uber rides?
2. Is there a direct positive correlation between the distance of the trip and the fare amount?
3. Does the number of passengers in the vehicle significantly impact the fare amount for Uber rides?

---

## 3. Data

### Dataset Description:

- **Source**: Kaggle  
- **Size**: 22.3 MB  
- **Shape**:  
  - Number of Rows: 200,000  
  - Number of Columns: 8  
- **Time Period**: 2009-2015  
- **Each Row Represents**: A unique Uber ride

### Data Dictionary:

- **Continuous Variables**:
  - `key`: Unique identifier for each trip
  - `fare_amount`: Fare amount paid for the ride
  - `pickup_datetime`: Date and time of the ride
  - `pickup_longitude`: Longitude of the pickup location
  - `pickup_latitude`: Latitude of the pickup location
  - `passenger_count`: Number of passengers in the ride
  - `dropoff_longitude`: Longitude of the dropoff location
  - `dropoff_latitude`: Latitude of the dropoff location

- **Categorical Variables**: None

### Target/Label for the ML Model:

- **Target Variable**: `fare_amount`

### Features/Predictors for ML Models:

- `pickup_datetime`
- `pickup_longitude`
- `pickup_latitude`
- `passenger_count`
- `dropoff_longitude`
- `dropoff_latitude`
