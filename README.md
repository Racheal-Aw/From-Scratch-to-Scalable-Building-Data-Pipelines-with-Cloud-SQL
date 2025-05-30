# From-Scratch-to-Scalable-Building-Data-Pipelines-with-Cloud-SQL
![Alt Text](relative/path/to/Proposed Database Schema.png)
The project involved applying skills such as web scraping with BeautifulSoup and building an API tracking system to deploy an automation solution in the cloud. Although the project was hypothetical, it helped me develop valuable skills that have shaped my path toward a career in data science. 
MY JOURNEY AS A JUNIOR DATA ENGINEER

I was tasked with building a robust data pipeline for Gans to ensure that e-scooters are available at the right locations when needed. My responsibilities included collecting various data types, such as geographical coordinates, demographics, meteorological data, and black box data; conducting exploratory data analysis using Python; and fully automating the entire process to run independently and seamlessly in the cloud.

I gained hands-on experience in web scraping, Application Programming Interfaces (API) integration, data cleaning, and cloud automation, key skills for a detail-oriented data scientist. Let’s proceed to understand the details of how I handled each phase of the project.

Phase 1: Cloud Pipeline

MySQL Database

A relational MySQL database was established as the central repository for Gans’ data pipeline, storing all collected, cleaned, and processed data. This structure offers the advantage of efficiently managing, querying, and analyzing large datasets to extract valuable, data-driven insights. Now, let me walk you through the database structure.

Database Structure

The relational MySQL database includes key tables such as city, population, cities_airport (static data), weather, and flight (dynamic data). Each table contains a unique identifier known as the primary key, along with foreign keys that establish relationships between tables, which is essential for performing meaningful, data-driven analysis.

Here is an overview of the key tables and their relationships:

1. City Table: This table stores geographical data for the cities where Gans operates. It includes fields such as city_id, city_name, country, latitude, and longitude.

2. Population Table: This table contains demographic information for each city, including the population size, the timestamp indicating when the data was retrieved (population_timestamp), and the associated city_id to link it to the corresponding city.

3. Weather Table: This table holds meteorological data for each city, with attributes including a unique identifier, city_name, forecast_time, timestamp_weather, outlook (weather description), temperature, feels_like (perceived temperature), temp_min (daily minimum temperature), temp_max (daily maximum temperature), pressure, humidity, wind_speed, rain, and the associated city_id to link it to the corresponding city.

4. Cities_Airport Table: This table contains airport data, including icao_code as the unique identifier for each airport, the airport name, and the associated city_id to link each airport to its corresponding city.

5. Flights Table: This table stores black box-related information, including the flight number, departure airport’s icao code, scheduled arrival time, timestamp_flight and the arrival airport’s icao code to link to each airport.
6. Web Scraping with BeautifulSoup

The first task involved collecting geographical and demographic data for Berlin, where Gans e-scooters are based, and expanding to two additional cities: Hamburg and Munich. The data include latitude, longitude, country, and population details. To gather this information, I wrote a web scraping function using Python’s BeautifulSoup library to extract data from Wikipedia. The script parsed the HTML content of the Wikipedia pages, extracted the necessary data, and stored it in a Pandas DataFrame, which was then saved to a MySQL database.
Meteorological data plays a vital role in predicting the movement and usage patterns of Gans e-scooters. I collected 24-hour weather forecasts to better understand how weather conditions could impact user behaviour and to optimize e-scooter availability accordingly.
The AeroDataBox API provides detailed flight information that is essential for Gans to optimize e-scooter distribution in response to customer demand. I collected data on flights scheduled to arrive the following day. Below is an example of how I used the AeroDataBox API to retrieve and process flight arrival information:
