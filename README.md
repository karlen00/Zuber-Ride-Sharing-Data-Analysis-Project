# Zuber Ride-Sharing Data Analysis Project

## Project Description

You work as an analyst for Zuber, a new ride-sharing company launched in Chicago. Your task is to find patterns in the available information to understand passenger preferences and the impact of external factors on trips. Using the database, you will analyze data from competitors and test hypotheses about the effect of weather on trip frequency.

## Data Description

The database contains information on taxi trips in Chicago with the following tables:

### Table: `neighborhoods`
- `name`: Name of the neighborhood
- `neighborhood_id`: Neighborhood code

### Table: `cabs`
- `cab_id`: Cab code
- `vehicle_id`: Technical ID of the vehicle
- `company_name`: Name of the company owning the vehicle

### Table: `trips`
- `trip_id`: Trip code
- `cab_id`: Cab code operating the trip
- `start_ts`: Trip start date and time (rounded to the nearest hour)
- `end_ts`: Trip end date and time (rounded to the nearest hour)
- `duration_seconds`: Trip duration in seconds
- `distance_miles`: Trip distance in miles
- `pickup_location_id`: Pickup location code
- `dropoff_location_id`: Dropoff location code

### Table: `weather_records`
- `record_id`: Weather record code
- `ts`: Date and time of the weather record (rounded to the nearest hour)
- `temperature`: Temperature at the time of the weather record
- `description`: Short description of weather conditions, such as "light rain" or "scattered clouds".

## Project Instructions

### Step 1: Write a code to extract weather data for Chicago in November 2017 from the website:

- Chicago Weather 2017

### Step 2: Exploratory Data Analysis

1. Find the number of taxi trips for each taxi company on November 15-16, 2017. Name the resulting column `trips_amount` and display it alongside the `company_name` column. Sort the results in descending order by `trips_amount`.

2. Find the number of trips for each taxi company whose name contains the words "Yellow" or "Blue" from November 1-7, 2017. Name the resulting variable `trips_amount`. Group the results by the `company_name` column.

3. In November 2017, the most popular taxi companies were Flash Cab and Taxi Affiliation Services. Find the number of trips for these two companies and name the resulting variable `trips_amount`. Combine trips from all other companies into one group: "Other". Group the data by the taxi company name. Name the column containing the taxi company names `company`. Sort the results in descending order by `trips_amount`.

### Step 3: Hypothesis Testing

Test the hypothesis that the trip duration from the Loop to O'Hare International Airport changes when it rains on Saturdays.

1. Get the neighborhood IDs for O'Hare and Loop from the `neighborhoods` table.
2. For each hour, get weather condition records from the `weather_records` table. Use a `CASE` statement to divide all hours into two groups: "Bad" if the `description` column contains the word "rain" or "storm", and "Good" for all other conditions. Name the resulting column `weather_conditions`. The final table should contain two columns: date and time (`ts`), and `weather_conditions`.
3. Extract from the `trips` table all trips that start in the Loop (neighborhood_id: 50) and end in O'Hare (neighborhood_id: 63) on Saturdays. Get the weather conditions for each trip using the method applied in the previous task. Also, get the duration of each trip. Ignore trips for which weather condition data is unavailable.

### Step 4: Exploratory Data Analysis (Python)

In addition to the data you obtained in the previous tasks, you are provided with two additional CSV files:

- `project_sql_result_01.csv`: Contains the following data:
  - `company_name`: Name of the taxi company
  - `trips_amount`: Number of trips for each taxi company on November 15-16, 2017.

- `project_sql_result_04.csv`: Contains the following data:
  - `dropoff_location_name`: Name of the Chicago neighborhood where the trip ended
  - `average_trips`: Average number of trips ending in each neighborhood in November 2017.

For these datasets, you need to:

1. Import both files.
2. Explore the contents of the data.
3. Ensure the data types are correct.
4. Identify the top 10 neighborhoods as drop-off points.
5. Create visualizations: taxi companies and their trip counts, top 10 neighborhoods by drop-offs.
6. Draw conclusions based on the visualizations and explain the results.

### Step 5: Hypothesis Testing (Python)

- `project_sql_result_07.csv`: Result of the final query. This file contains trip data from the Loop to O'Hare International Airport. The columns are:
  - `start_ts`: Date and time of pickup
  - `weather_conditions`: Weather conditions at the start of the trip
  - `duration_seconds`: Trip duration in seconds

Test the hypothesis:
- "The average trip duration from the Loop to O'Hare International Airport changes when it rains on Saturdays."

Set the significance level (alpha) independently.

Explain:
- How you formulated the null and alternative hypotheses.
- The criteria you used to test the hypothesis and the reason for using them.

---

This README will guide you through the systematic and structured completion of the data analysis project for the Zuber ride-sharing company.
