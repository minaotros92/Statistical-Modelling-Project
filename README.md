# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The aim of this project is to develop a statistical model using Python and its various libraries, including pandas, numpy, seaborn, matplotlib, and PIL. The primary goal was to extract, cleanse, transform, analyze, and construct a model to evaluate data sourced from three distinct APIs: CityBikes, Foursquare, and Yelp. The city of Mobi in Vancouver was selected for this study. The objective was to explore whether the availability of bikes at each station in the city correlated with the popularity of nearby points of interest (POIs). To gauge popularity, the study utilized 'rating' and 'review count' as metrics to determine how favored these POIs were among users.
## Process
### (your step 1)
 Connecting with the CityBikes API
I began by investigating the CityBikes network, learning about its various cities and how to request data. My focus was on finding cities by their ID to gather information about those using the bike-sharing app. Eventually, I selected Mobi in Vancouver for my study, and found that using CityBikes made data collection straightforward.

### (your step 2)Connecting with the POIs API with a get request given to Foursquare and Yelp
1. Connecting to APIs
Foursquare API: I registered for a developer account on Foursquare and obtained my API key. Using Python's requests library, I connected to the Foursquare Places API. The API was queried for specific data points such as restaurants, bars, and various Points of Interest (POIs) near each bike station location retrieved from the CityBikes data.
Yelp API: Similarly, I registered on Yelp's developer platform and acquired an API key. Using the Yelp API, I requested information about local businesses and POIs around the bike stations, focusing on categories like restaurants and bars.
2. Querying APIs for Bike Station Locations
For each bike station (latitude and longitude) obtained from the CityBikes data, I made API calls to both Foursquare and Yelp. I searched for nearby restaurants, bars, and other POIs within a predefined radius of each station.
3. Creating DataFrames
Yelp DataFrame: Compiled the results from Yelp into a DataFrame, including details like business name, category, distance, address, latitude, longitude, rating, and review count.
Foursquare DataFrame: Created a similar DataFrame for Foursquare data, capturing information such as name, category, distance, and location coordinates.
4. Analyzing and Comparing API Data
Conducted an Exploratory Data Analysis (EDA) on both DataFrames to compare the quality and coverage of data from Yelp and Foursquare.
Coverage Analysis: I considered factors such as the number of POIs, diversity of POIs, user ratings, review counts, and the granularity of location data.
Quality Assessment: Evaluated the reliability, accuracy, and relevance of the data provided by each API for the locations around the bike stations.
5. Conclusions and Insights
Comparison of Completeness: Determined which API provided more comprehensive coverage around the bike stations based on the selected criteria (e.g., number of POIs, reviews per POI).
Better Coverage: Analyzed which API offered better coverage in terms of variety and depth of information for the specified location.
6. Documentation
All these steps were meticulously documented in the yelp_foursquare_EDA.ipynb notebook, showcasing the process of data retrieval, cleaning, analysis, and comparison.

(your step 3)
The research focused on identifying variables that could predict the availability of bikes for rent at a station. During the Exploratory Data Analysis (EDA), the data was thoroughly analyzed and interpreted, raising key questions:

Types of Variables: Understanding the variety of variables present in the dataset.
Variable Roles: Identifying which variables significantly influence the availability of free bikes.
Variable Types: Classifying the variables by their data types.
The data cleaning and transformation process involved several steps:

Handling Missing Data: Identifying and addressing missing values, such as NaNs, non-null entries, and empty spaces.
Data Type Conversion: Altering data types of specific variables for analysis. Variables like empty slots, free bikes, renting bikes, and review count were converted from Float64 to int8.
Duplicate Assessment: Identifying and removing duplicated rows.
Column Interpretation: Analyzing each column in the dataset to determine its relevance before removing any.
The culmination of these efforts was the creation of a merged dataset combining data from citybikes, faq, and yelp. This comprehensive dataset aimed to facilitate a more accurate prediction of the dependent variable, 'free bikes'.

(your step 4)
 involved the analysis of the dataset using descriptive statistics, hypothesis testing, and a multivariate linear regression model. This regression model was employed to explore the relationship between a dependent variable (free bikes) and several independent variables, including rating, review count, and others. The analytical process began with descriptive statistics and hypothesis testing, utilizing Pearson's Correlation Theory. To assess the model's performance, a technique known as forward stepwise selection was adopted. In this approach, variables were incrementally added to the analysis with the dependent variable. Initially, the model contained only rating and review count, with additional variables like empty slots and renting bikes incorporated one at a time. At each step, the variable that contributed the most to improving the model's fit was retained. The inclusion of these variables collectively led to enhancements in our model's performance, and this was continuously reassessed throughout the analysis.
## Results
The outcomes of this study, derived from our statistical analysis, hypothesis testing, and multivariate regression model, indicate that the number of available bikes at a station may be influenced by a combination of various factors, including the number of empty slots, the ratings of nearby points of interest (POIs), the review count of these places, and possibly the bike rental activity itself. When these predictors are incorporated into the same model, they suggest that stations in proximity to popular places of interest, characterized by higher ratings and review counts, tend to have fewer or no available bikes for rent, presumably due to increased foot traffic in those areas. The graphical representations reveal a negative correlation between ratings, review counts, and bike availability. Thus, if the places are more popular, it becomes more likely that people won't find available bikes for rent.

Furthermore, it is important to note that despite employing the forward selection strategy and conducting multiple iterations of the model with the aid of visualizations, these results serve as potential indicators for predicting changes in bike availability at a station. Consequently, this project paves the way for future research in this field.

Additionally, it's worth mentioning that the "rating" variable is presented as an interval value. If the ratings were assigned based on a predefined set of categories or classifications (e.g., "Excellent," "Very Good," "Fair," "Poor," etc.), and if the distances between these categories held meaningful significance (although this parameter was omitted due to missing information for all requested POIs), combining this quality measure could offer more insightful findings for this project.
## Challenges 
Many challenges were faced during this project, such as:
- Matching the data retrieved by different APIs;
- Thinking about sampling possibilities to be done from a population of stations in a short time;
- Making important decisions about the cleanning and transformation of the data, such as, removing duplicates, filling missing values with 0 and others, deleting rows and columns, among others;
- Parsing the data and creating different datasets to be analyzed;
- Applying the statistical analysis before and while building the regression model.
## Future Goals

If I had more time available, I would have delved deeper into the datasets, examining their underlying patterns and investigating the population of the stations. Since this project had a tight deadline with numerous tasks to complete, the analytical process remained somewhat unfinished. Additionally, I wasn't able to explore some of the libraries to the extent I would have preferred, resulting in similarities in some of the visualizations, primarily utilizing plots, scatterplots, and histograms.