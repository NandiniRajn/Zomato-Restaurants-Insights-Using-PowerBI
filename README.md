# Zomato Restaurant Insights Dashboard

This project provides an interactive Power BI dashboard to visualize and analyze Zomato restaurant data across various metrics, including restaurant distribution, online delivery availability, ratings, price ranges, etc. 

## Step 1: Data Import and Transformation

### 1. Load Data
   - Open **Power BI** and click on **Get Data** to import the Zomato dataset.
   - After importing, examine the dataset to understand its structure.

### 2. Data Cleaning
   - Go to **Transform Data** to clean and organize the data.
   - Remove duplicates to avoid over-counting restaurants.
   - Handle missing values by filling in or excluding nulls as needed.

### 3. Data Transformation
   - Use Power BI's data transformation tools to adjust column data types as required for accurate visualizations and calculations.

### 4. Data Processing
   - Create a new column for country names based on `CountryCode` using **DAX**:
     - Go to the **Table** view, and in the **Modeling** tab, select **New Column**.
     - Use the following DAX formula to map `CountryCode` values to their respective country names:

     ``` DAX
     CountryName = 
     SWITCH(
         TRUE(),
         ZomatoData[CountryCode] = 1, "India",
         ZomatoData[CountryCode] = 14, "Australia",
         ZomatoData[CountryCode] = 30, "Brazil",
         ZomatoData[CountryCode] = 37, "Canada",
         ZomatoData[CountryCode] = 94, "Indonesia",
         ZomatoData[CountryCode] = 148, "New Zealand",
         ZomatoData[CountryCode] = 162, "Philippines",
         ZomatoData[CountryCode] = 166, "Qatar",
         ZomatoData[CountryCode] = 184, "Singapore",
         ZomatoData[CountryCode] = 189, "South Africa",
         ZomatoData[CountryCode] = 191, "Sri Lanka",
         ZomatoData[CountryCode] = 208, "Turkiye",
         ZomatoData[CountryCode] = 214, "The United Arab Emirates",
         ZomatoData[CountryCode] = 215, "United Kingdom",
         ZomatoData[CountryCode] = 216, "United States"
     )
     ```

## Step 2: Create Visuals for the Dashboard

### 1. Key Metrics (Card/KPI Visuals)
   - Display key metrics at a glance, such as:
     - **Total Restaurants**: 9,551
     - **Total Cities**: 141
     - **Total Countries**: 15
   - Use **Slicer Filters** for targeted analysis by city, rating, online delivery, and price range.

### 2. Top Cities by Restaurant Count (Bar Chart)
  - Highlight the countries or cities with the highest concentration of restaurants.
   - Show the cities with the highest restaurant counts:
     - **New Delhi**: 5.5K restaurants, the largest concentration.
     - **Gurgaon and Noida**: 1.1K each.
   - This helps identify primary restaurant hubs within Zomato, especially within Indian cities.

### 3. Online vs. Offline Delivery Availability (Pie Chart)
   - Visualize online delivery options:
     - **74.29%** of restaurants do not offer online delivery.
     - **25.65%** provide online delivery.

### 4. Top Restaurants by Rating and Cost for Two (Matrix Chart)
   - List top-rated restaurants with their average cost for two:
     - Examples: **Sushi Masa** (500,000), **Talaga Sampireun** (200,000), **Spiral - Sofitel** (6,000).
     - These restaurants maintain high ratings (4.90), representing premium options in the database.

### 5. Votes by Price Range Analysis (Donut Chart)
   - Show distribution of customer votes across four price ranges:
     - **Price Range 3**: Highest with 41.71% of votes.
     - **Price Range 4**: 30.65%
     - **Price Range 2**: 14.4%

### 6. Map Visualization
   - Display the global distribution of restaurants using a map visual.
   - Interactive exploration of data density by city or country is possible by selecting specific regions.

## Insights
This dashboard offers a comprehensive view of Zomato’s global restaurant data, providing insights into restaurant distribution, delivery availability, user engagement by price range, and more.

---

![Zomato Dashboard](./Zomato%20Dashboard.png)
![Zomato Dashboard1](https://github.com/NandiniRajn/Zomato-Restaurants-Insights-Using-PowerBI/blob/main/Zomato%20Dashboard%201.png)
