# Project: Equatorial Weather Analysis and Vacation Planning
## Summary
This project explores the relationship between latitude and weather, specifically focusing on the area near the equator.  We aimed to answer the question: "What is the weather like as we approach the equator?" While the general assumption is that it gets hotter, this project uses data analysis and visualization to provide concrete evidence and explore other weather factors.  Furthermore, using the collected weather data, we developed a vacation planning application to suggest ideal travel destinations based on user-defined weather preferences.

## Background
By leveraging Python's `requests` library, APIs (specifically OpenWeatherMap and Geoapify), and JSON traversal techniques to analyze weather patterns near the equator.  The initial phase focused on collecting and organizing weather data for cities near the equator.  Then analyzed this data to observe trends in temperature and other meteorological factors as latitude approaches zero.

The project is divided into two main parts:

**Part 1:  Equatorial Weather Data Collection and Analysis**

In this part, I:

1.  Used the OpenWeatherMap API to collect current weather data (temperature, humidity, wind speed, cloudiness, etc.) for a selection of cities.
2.  Stored this data in a Pandas DataFrame for further analysis.
3.  Analyzed the collected data, primarily focusing on temperature, to determine if a correlation exists between proximity to the equator and temperature. Also considered other factors such as humidity, wind speed, and cloudiness.
4.  Visualized the data using scatter plots and potentially other charts to present the findings clearly.

**Part 2: VacationPy - Interactive Vacation Planner**

Building upon the weather data collected in Part 1, I developed an interactive vacation planner using GeoViews and the Geoapify API.  This part involved:

1.  Creating an interactive map displaying all the cities from the weather dataset, with point size representing humidity.
2.  Filtering the weather data based on user-defined "ideal" weather conditions (e.g., temperature range, wind speed, cloudiness).
3.  Using the Geoapify API to find hotels near the cities that matched the user's ideal weather criteria.
4.  Displaying the hotels on an interactive map with tooltips showing city, country, humidity, and hotel name.

***Please note that*** 
The provided starter code uses a completely random approach, which led to poor sampling, leading to similar weather data.  I tried to pull the data 4 times and unable to generate the answers.  I did some research and modified the codes to improve the distribution of the random latitude and longitude coordinates within latitude bands to improve the distribution of cities.  For VacationPy assignment, I also need to adjust my specifications to ensure that I set a reasonable limit to the number of rows returned by the API requests.

## Key Technologies Used

*   Python
*   Pandas
*   Requests /JSON
*   OpenWeatherMap API
*   Geoapify API
*   GeoViews
*   Jupyter Notebook
*   Matplotlib (potentially)

## Findings
Temperature vs. Latitude Linear Regression Plot
![image](https://github.com/user-attachments/assets/e74afa30-985b-4b32-bac5-0c10398c0bc6)

In the Northern Hemisphere, a moderately strong negative correlation (R-value of approximately 0.78) exists between latitude and maximum temperature. As latitude increases, moving north and away from the equator, the maximum temperature tends to decrease. This aligns with general climate patterns. The linear regression model (y = -0.79x + 33.87) suggests that for every degree of latitude increase, the maximum temperature is predicted to fall by 0.79 units (Celsius or Fahrenheit, depending on your data's units). While the trend is clear, the scatter plot indicates that other factors beyond latitude also influence temperature, and some outliers suggest local weather anomalies.

In the Southern Hemisphere, the relationship between latitude and maximum temperature is much weaker (R-value of approximately 0.17) and shows a positive correlation. As latitude increases, moving north towards the equator, the maximum temperature tends to increase, though the relationship is not as pronounced as in the Northern Hemisphere. The linear regression model (y = 0.16x + 27.47) suggests a smaller temperature increase of 0.16 units per degree of latitude. The high degree of scatter in the data points indicates that latitude is not a strong predictor of maximum temperature in the Southern Hemisphere, likely due to the larger proportion of ocean area, which moderates temperature fluctuations.

![image](https://github.com/user-attachments/assets/12459288-20a5-4015-b5ae-8120a94948ab)

Northern Hemisphere - Humidity vs. Latitude
The linear regression models the relationship between latitude and humidity in the Northern Hemisphere, exploring if there's a correlation between how far north a city is and its humidity levels. The scatter plot shows a weak positive correlation, suggesting that there's a slight tendency for humidity to increase as latitude increases. However, the R-value of 0.13 indicates that the relationship is very weak, and latitude is not a strong predictor of humidity. The data points are widely scattered, implying that other factors significantly influence humidity. The regression line equation, y = 0.43x + 55.45, indicates that for every degree of latitude increase, humidity is predicted to rise by 0.43 units.

Southern Hemisphere - Humidity vs. Latitude
The scatter plot shows a weak positive correlation, similar to the Northern Hemisphere, with a slight tendency for humidity to increase as latitude increases (moving closer to the equator). The R-value of 0.23 suggests a slightly stronger relationship compared to the Northern Hemisphere, but it's still considered weak. The data points are quite dispersed, indicating that factors other than latitude play a more dominant role in determining humidity levels. The regression equation, y = 0.69x + 87.77, suggests that for each degree of latitude increase, humidity is predicted to increase by 0.69 units. However, given the weak correlation, this prediction should be interpreted cautiously.

![image](https://github.com/user-attachments/assets/2b3ed7eb-067d-4776-bd43-1978c6087e72)

Northern Hemisphere - Cloudiness vs. Latitude
The linear regression models the relationship between latitude and cloudiness in the Northern Hemisphere. The scatter plot indicates a very weak positive correlation, suggesting a slight tendency for cloudiness to increase as latitude increases. However, the R-value of 0.04 indicates that the relationship is practically non-existent, and latitude is a very poor predictor of cloudiness. The data points are widely dispersed, showing that many other factors influence cloud cover. The regression line equation, y = 0.4x + 41.13, suggests a minimal increase in cloudiness with latitude, but given the extremely weak correlation, this prediction has little practical significance.

Southern Hemisphere - Cloudiness vs. Latitude
The linear regression models the relationship between latitude and cloudiness in the Southern Hemisphere. Similar to the Northern Hemisphere, the scatter plot suggests a weak positive correlation, with a slight tendency for cloudiness to increase as latitude increases (moving closer to the equator). The R-value of 0.09 indicates a very weak relationship, slightly stronger than in the Northern Hemisphere but still not meaningful. The data points are widely scattered, indicating that factors other than latitude are the primary drivers of cloudiness. The regression equation, y = 0.83x + 75.61, suggests a more substantial increase in cloudiness with latitude compared to the Northern Hemisphere. However, due to the weak correlation, this prediction should be interpreted cautiously and is not reliably supported by the data.

![image](https://github.com/user-attachments/assets/b5a516fe-3cf8-4835-a1f1-687ff6478f67)

Northern Hemisphere - Wind Speed vs. Latitude
The scatter plot shows a very weak negative correlation, suggesting a slight tendency for wind speed to decrease as latitude increases. However, the R-value of approximately 0.002 indicates that the relationship is essentially non-existent, and latitude is an extremely poor predictor of wind speed. The data points are widely scattered, emphasizing that numerous other factors overwhelmingly influence wind speed. The regression line equation, y = -0.01x + 3.99, suggests a minimal decrease in wind speed with latitude, but due to the extremely weak correlation, this prediction holds no practical significance.

Southern Hemisphere - Wind Speed vs. Latitude
The scatter plot indicates a weak negative correlation, similar to the Northern Hemisphere, with a slight tendency for wind speed to decrease as latitude increases (moving closer to the equator). The R-value of approximately 0.097, while higher than in the Northern Hemisphere, still indicates a weak relationship. The data points are quite dispersed, suggesting that variables other than latitude are the primary determinants of wind speed. The regression equation, y = -0.07x + 2.63, implies a more noticeable decrease in wind speed with latitude compared to the Northern Hemisphere. 

**Vacation.py**
Below is a map that displays a point for every city in the city_data_df DataFrame .

![image](https://github.com/user-attachments/assets/8152c334-4d7b-4c0f-aec3-efa99d978330)

For the ideal weather condition, I adjusted the specifications so that I have a reasonable limit to the number of rows returned by API requests to be able to map out the first hotel located within 10,000 meters of my coordinates as shown below. 

![image](https://github.com/user-attachments/assets/d4ec672b-416c-4c32-8ddf-4a07281b3b8e)








