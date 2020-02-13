# sqlalchemy-challenge
## Objectives

### Step 1 - Climate Analysis and Exploration

To begin, use Python and SQLAlchemy to do basic climate analysis and data exploration of your climate database. All of the following analysis should be completed using SQLAlchemy ORM queries, Pandas, and Matplotlib:

  1. Choose a start date and end date for your trip. Make sure that your vacation range is approximately 3-15 days total.
  2. Use SQLAlchemy create_engine to connect to your sqlite database.
  3. Use SQLAlchemy automap_base() to reflect your tables into classes and save a reference to those classes called Station and Measurement.

#### Precipitation Analysis

  1. Design a query to retrieve the last 12 months of precipitation data.
  2. Select only the date and prcp values.
  3. Load the query results into a Pandas DataFrame and set the index to the date column.
  4. Sort the DataFrame values by date.
  5. Plot the results using the DataFrame plot method.
  6. Use Pandas to print the summary statistics for the precipitation data.

#### Station Analysis

  1. Design a query to calculate the total number of stations.
  2. Design a query to find the most active stations.
    - List the stations and observation counts in descending order.
    - Which station has the highest number of observations?
    - Hint: You may need to use functions such as func.min, func.max, func.avg, and func.count in your queries.
  3. Design a query to retrieve the last 12 months of temperature observation data (tobs).
    - Filter by the station with the highest number of observations.
    - Plot the results as a histogram with bins=12.
    
### Step 2 - Climate App

Now that you have completed your initial analysis, design a Flask API based on the queries that you have just developed.
  1. Use FLASK to create your routes.

Routes
  1. /
    - Home page.
    - List all routes that are available.

  2. /api/v1.0/precipitation
    - Convert the query results to a Dictionary using date as the key and prcp as the value.
    - Return the JSON representation of your dictionary.

  3. /api/v1.0/stations
    - Return a JSON list of stations from the dataset.

  4. /api/v1.0/tobs
    - Query for the dates and temperature observations from a year from the last data point.
    - Return a JSON list of Temperature Observations (tobs) for the previous year.

  5. /api/v1.0/<start> and /api/v1.0/<start>/<end>
    - Return a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.
    - When given the start only, calculate TMIN, TAVG, and TMAX for all dates greater than and equal to the start date.
    - When given the start and the end date, calculate the TMIN, TAVG, and TMAX for dates between the start and end date inclusive.
