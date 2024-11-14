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

### What is it about?

Uber fare prediction involves estimating the cost of ridesharing services based on various factors like the time and location of pickups and drop-offs, distance traveled, demand, and other contextual variables. The model is trained using historical ride data from 2009–2015 to learn patterns and establish correlations between these features and the fare.

### Why Does It Matter?

- **Company Optimization**: Accurate fare predictions are critical to Uber’s operational efficiency, ensuring fair compensation for drivers and maintaining the balance between supply, demand, and pricing strategies.
- **Competitive Advantage**: Precise fare estimations give Uber an edge over competitors in the highly competitive ridesharing market, attracting more customers.
- **Data Insights**: Analyzing fare projections provides insights into peak demand periods, rider behavior, and the impact of external factors on pricing. This data can be leveraged for marketing and resource allocation strategies.

### What are your research questions?

1. Does the time of day significantly affect the fare amount for Uber rides?
2. Is there a direct positive correlation between the distance of the trip and the fare amount?
3. Does the number of passengers in the vehicle significantly impact the fare amount for Uber rides?

---

## 3. Data

### Dataset Description:

- **Source**: [Kaggle ](https://www.kaggle.com/datasets/yasserh/uber-fares-dataset) 
- **Size**: 22.3 MB  
- **Shape**:  
  - Number of Rows: 200,000  
  - Number of Columns: 8  
- **Time Period**: 2009-2015  
### What does each row represent?(a patient, a school, a crime, etc.)

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

### Which variable/column will be your target/label in your ML model?

- **Target Variable**: `fare_amount`

### Which variables/columns may be selected as features/predictors for your ML models?
- `pickup_datetime`
- `pickup_longitude`
- `pickup_latitude`
- `passenger_count`
- `dropoff_longitude`
- `dropoff_latitude`

## Exploratory Data Analysis (EDA)

### Performing Data Exploration in Jupyter Notebook
In this project, data exploration was conducted using Jupyter Notebook to better understand the target variable (`fare_amount`) and relevant features. Columns unrelated to predictive analysis were dropped to streamline the dataset.

### Summary Statistics of Key Variables
Summary statistics were generated for `fare_amount`, `passenger_count`, `pickup_datetime` components (year, month, day, hour), and calculated distances. This provided insights into the distribution and range of values across key features, identifying any outliers or abnormal data patterns.

### Visualizations
Visualizations were created to analyze data distribution and relationships between variables. Using Plotly Express and Matplotlib:
- **Trip Distance Histogram**: Showed that most Uber trips were under 5 km.
![Screenshot 2024-11-14 004010](https://github.com/user-attachments/assets/00b42a56-8412-482b-8472-e6b792ed1ed1)
- **Fare Distribution**: Illustrated a right-skewed distribution for fare amounts, indicating the presence of high-fare outliers.
![Screenshot 2024-11-14 004217](https://github.com/user-attachments/assets/41ff137c-f712-4242-9e83-533a9060b66c)
- **Rides per Day and Revenue per Day**: Revealed peak usage days and higher revenue on Fridays.
![Screenshot 2024-11-14 004922](https://github.com/user-attachments/assets/96aaf803-4baf-41a8-b139-24a872cee407)
![Screenshot 2024-11-14 005005](https://github.com/user-attachments/assets/5a2375f4-18f0-4a7b-85e4-2a30c29c5eda)
- **Rides per Month**: Indicated higher ride demand in the spring and early summer months (March-May).
![Screenshot 2024-11-14 144147](https://github.com/user-attachments/assets/8f23596c-5c00-4d94-ab03-8827d6e22ca6) 
- **Box Plot of Fare Amount by Passenger Count**: Provided insights into how fares vary with the number of passengers.
![Screenshot 2024-11-14 010454](https://github.com/user-attachments/assets/a0a3b8d7-aac4-4368-b910-529ac295996e)

### Data Cleaning Requirements
- **Missing Values**: Rows with missing data were removed to ensure data integrity.
- **Duplicate Rows**: Duplicate entries were checked and removed to avoid data redundancy.
- **Outliers**: Outliers in `fare_amount` and `distance_km` were identified and handled to improve model performance.

### Data Transformation and Augmentation
- **Datetime Decomposition**: The `pickup_datetime` column was decomposed into year, month, day, and hour to capture time-based patterns.
- **Distance Calculation**: `distance_km` was calculated using pickup and drop-off coordinates.
- **Merging/Splitting**: There were no additional data sources needed for this project. Future work could explore adding socioeconomic or demographic data, such as population density or income levels, to refine predictions.

### Data Tidiness
To ensure the data was tidy:
- Each row represented one unique trip (observation).
- Each column represented one unique attribute of the trip (fare, date, distance, etc.).

## Model Training

### Predictive Models
Three models were selected for fare prediction:
1. **Linear Regression**
2. **Random Forest Regressor**
3. **Gradient Boosting Regressor**

### Training Process
The dataset was split into training and testing sets (80/20 split) to evaluate the model's performance on unseen data. The features used for training included `passenger_count`, `distance_km`, and datetime components (year, month, day, hour).

### Python Packages
The following packages were used for model development:
- **scikit-learn** for model training and evaluation
- **pandas** for data manipulation
- **geopy** for distance calculation
- **Matplotlib** and **Seaborn** for visualizations

### Development Environment
The project was developed using Jupyter Notebook on a personal laptop, with code and documentation managed in a GitHub repository.

### Model Evaluation Metrics
Model performance was measured using:
- **Root Mean Square Error (RMSE)** to assess prediction error
- **R² Score** to evaluate the variance explained by each model

Gradient Boosting achieved the best performance with the lowest RMSE and highest R², indicating it was the most accurate model for this prediction task.

## Application of the Trained Models

To make the model accessible, a web app will be developed. The app will allow users to interact with the model by entering input values (e.g., `passenger_count`, `distance_km`, date, and time) to get fare predictions.

### Tools for Web App Development
The app will be created using:
- **Streamlit**: Chosen for its simplicity and ease of use, Streamlit allows for quick deployment of data science models as interactive web applications.

## Conclusion

### Summary of Work
This project demonstrated the use of machine learning to predict Uber fares based on trip data. The Gradient Boosting model proved to be the most suitable, effectively capturing complex patterns in the data.

### Potential Applications
This fare prediction model could be used by ride-sharing companies to dynamically price rides, optimize routes, and improve customer experience through more accurate fare estimates.

### Limitations
Some limitations of the model include:
- Lack of additional external data, such as traffic or weather, which may impact fare prices.
- Limited to the dataset's geographic and temporal scope, making it challenging to generalize to other regions or time periods.

### Lessons Learned
- Feature engineering, such as distance calculation and datetime decomposition, played a crucial role in enhancing model accuracy.
- Model evaluation and comparison were essential for selecting the best-performing model.

### Future Directions
- Incorporate external data sources, such as weather or traffic data, to further improve model accuracy.
- Experiment with hyperparameter tuning for Gradient Boosting to achieve even better performance.

## References

1. Streamlit Documentation. Retrieved from [Streamlit Docs](https://docs.streamlit.io/)
2. Uber Open Dataset [Kaggle ](https://www.kaggle.com/datasets/yasserh/uber-fares-dataset)
3. Geopy Distance Calculation. Retrieved from [Geopy Documentation](https://geopy.readthedocs.io/)
