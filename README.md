# Airbnb Listings EDA Project: New York 2024  

---

## Project Overview
This project performs **Exploratory Data Analysis (EDA)** on New York Airbnb data to understand pricing patterns, availability trends, and host behavior. The analysis focuses on extracting meaningful insights from raw data.
![AirBnb](Images\Renting-out-on-Air-BnB-scaled.jpg)
---

## Objective
The goal of this project is to:
1. Analyze **room types, prices, and availability** across different neighborhoods.
2. Understand **host behavior** and listing patterns.
3. Detect potential **outliers** in prices.
4. Provide recommendations for guests and hosts based on insights.

---

## Dataset
The dataset contains **20,770 entries and 22 features**, including:
- **id**: Unique identifier for each listing  
- **name**: Title of the Airbnb listing  
- **host_name**: Name of the host  
- **neighborhood_group**: Group (borough) where the listing is located  
- **latitude/longitude**: Geolocation of listings  
- **price**: Nightly rental price  
- **room_type**: Type of accommodation (e.g., entire home, private room)  
- **reviews_per_month**: Average monthly reviews for the listing  
- **availability_365**: Number of available days in the year  

---

## Steps and Workflow

### 1. Data Cleaning
- **Handled missing data**: `price`, `neighborhood`, and `beds` columns had null values.  
-  **Handled duplicate values**: Dropped duplicate values from data.
- **Fix data types**: Converted `last_review` to a **datetime** object.
- **Remove outliers**: The IQR method identified an upper bound of approximately 377 for the price column. However, the distribution of Airbnb prices is highly right-skewed, with extreme values (maximum price = 100,000) inflating the variance.  
To avoid removing legitimate high-priced listings while still filtering unrealistic values, listings with prices greater than 1500 were treated as outliers and removed from the dataset.

---

## 2. Exploratory Data Analysis (EDA)

### Price Distribution
![Price Distribution](Images\Price-Distribution.png)

- Most listings are priced between $50–$300
- The distribution is highly right-skewed, indicating presence of extreme high-price listings

---

### Price by Neighborhood and Room Type
![Price by Neighborhood](Images\Price-by-Neighborhood.png)

- Manhattan has the highest average prices across most room types
- Entire homes/apartments are consistently the most expensive option in all neighbourhoods
- Private and shared rooms are more affordable, with relatively similar pricing across areas
- Brooklyn and Queens offer comparatively lower prices than Manhattan

---

### Price vs Number of Reviews
![Price vs Reviews](Images\Price-vs-Reviews.png)

- Lower-priced listings tend to receive more reviews
- Indicates a negative relationship between price and demand

---

### Correlation Heatmap
![Correlation Heatmap](Images\Correlation-Heatmap.png)

- Price shows moderate correlation with number of reviews and availability
- Most variables have weak correlations, indicating independent effects
---

## Key Findings and Insights
1. **Price Trends**:  
   - **Manhattan** has the most expensive listings, followed by Brooklyn.  
   - **Entire homes/apartments** cost significantly more than private or shared rooms.  

2. **Room Type Distribution**:  
   - **Entire homes/apartments** are the most common, but **private rooms** offer budget-friendly options.

3. **Outliers in Price**:  
   - Few listings priced at **$10,000+** were detected, indicating the need to filter such extreme values.

4. **Availability Patterns**:  
   - Listings with **high availability** tend to have lower prices and more reviews.

5. **Host Behavior**:  
   - Some hosts manage **multiple listings**, indicating a trend toward professional hosting.

---

## Recommendations
- **For Guests**: 
   - Look for listings with high availability and good reviews for a better experience.
   - **Private rooms** in Brooklyn offer affordable stays compared to Manhattan.

- **For Hosts**:  
   - Improve **availability** and **review response rates** to attract more bookings.
   - Competitive pricing within the $50–$300 range can improve booking chances.
---

## Conclusion
This project offers valuable insights into the New York Airbnb market, helping both guests and hosts make informed decisions. By using **EDA techniques**, we identified key trends and developed actionable recommendations. Future improvements can involve advanced analytics and predictive modeling to further enhance the findings.

---

Author
Faisal Khan  
Gmail: Faisalkhan2287@gmail.com  
