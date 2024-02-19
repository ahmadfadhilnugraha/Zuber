# Zuber
In this project, I am acting as an analyst for Zuber, a new ride-sharing company launched in Chicago. The main goal of this project is to understand passenger preferences and the impact of external factors on travel. Using a database, I will analyze data from competitors and test hypotheses related to the influence of weather on travel frequency.

## Goal

- Identifying the top 10 regions used as delivery points
- Analyzing taxi companies and their trip counts
- Testing the hypothesis "Average trip duration from the Loop to O'Hare International Airport changes when it rains on Saturdays."

## Step

1. Writing a code to scrape weather data in Chicago for November 2017 from the website: https://practicum-content.s3.us-west-1.amazonaws.com/data-analyst-eng/moved_chicago_weather_2017.html
2. Initial Exploratory Data Analysis (***Notes: this step has been completed using SQL***)
3. Data Type Correction
4. Advanced Exploratory Data Analysis
5. Hypothesis Testing

## Data Description

**Database containing taxi trip information in Chicago:**
  - **Table neighborhoods:**
      - **name:** name of the area
      - **neighborhood_id:** area code
  - **Table cabs:**
      - **cab_id:** vehicle code
      - **vehicle_id:** technical ID of the vehicle
      - **company_name:** name of the company owning the vehicle   
  - **Table trips:**
      - **trip_id:** trip code
      - **cab_id:** code of the operating vehicle
      - **start_ts:** date and time trip started (time rounded to the nearest hour)
      - **end_ts:** date and time trip ended (time rounded to the nearest hour)
      - **duration_seconds:** duration of the trip in seconds
      - **distance_miles:** distance of the trip in miles
      - **pickup_location_id:** pickup area code
      - **dropoff_location_id:** dropoff area code
  - **Table weather_records:**
      - **record_id:** weather record code
      - **ts:** date and time when weather recording was taken (time rounded to the nearest hour)
      - **temperature:** temperature at the time of weather recording
      - **description:** brief description of weather conditions, such as "light rain" or "scattered clouds."
   
After SQL EDA process, we obtain 3 new datasets.
- **project_sql_result_01.csv**. This file contains the following data:
    - **company_name**: the name of the taxi company
    - **trips_amount**: the number of trips for each taxi company on November 15-16, 2017.
- **project_sql_result_04.csv**. This file contains the following data:
    - **dropoff_location_name**: the name of the neighborhood in Chicago where the trip ends
    - **average_trips**: the average number of trips ending in each neighborhood in November 2017.
- **project_sql_result_07.csv** - the result of the last query. This file contains trip data from the Loop to O'Hare International Airport. Remember, here are the values ​​of the columns in this table:
    - **start_ts** -- date and time of pickup
    - **weather_conditions** -- weather conditions at the start of the trip
    - **duration_seconds** -- trip duration in seconds

## Conclusion

- The top 10 destinations most frequently visited by taxi passengers are: Loop, River North, Streeterville, West Loop, O'Hare, Lake View, Grant Park, Museum Campus, Gold Coast, and Sheffield & DePaul.
- The top 10 taxi companies with the highest number of trips are: Flash Cab, Taxi Affiliation Services, Medallion Leasing, Yellow Cab, Taxi Affiliation Service Yellow, Chicago Carriage Cab Corp, City Service, Sun Taxi, Star North Management LLC, and Blue Ribbon Taxi Association Inc.
- Flash Cab emerges as the market leader due to its significant customer base compared to other companies.
- The average trip duration from the Loop to O'Hare International Airport differs on rainy Saturdays.
