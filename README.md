# data-sourcing-challenge

# Data Sourcing Challenge - Movie Data

In this challenge we are tasked with collecting data from two different datasets. The first being the New York Times (NYT), the second is The Movie Database (TMDB).
This allows for the fetching and merging of multiple data sources and putting it together in an aggregate way.

## Workflow

- Access and fetch data from the NYT api
    1. Build out query string details to fetch the required data
    2. Using pagination within the api fetch 20 pages worth of data
        - Implements a sleep to throttle the number of requests to not get blacklisted
    3. Clean and normalize the data
    4. Create a pandas DataFrame using the json_normalize function.
- Access and fetch data from the TMDB api
    1. Using movies based on titles from the NYT data, fetch details from TMDB
        - Implemets a 1 second throttle after 50 requests to fit request parameters.
    2. For each movie detail found, parse out specific details and add to a custom dictionary, that dictionary is then added to a list.
    3. Using the dictionary list (series) generate a pandas DataFrame of the data
- Clean all data and merge the DataFrames for export. 
    1. Clean lists so the data can be exported via csv
    2. Remove byline column as the data isn't compatible for csv
    3. Remove duplicates
    4. Export data to movie_data.csv