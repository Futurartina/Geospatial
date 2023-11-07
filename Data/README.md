Project 3 - Geospatial Data

Overview
The aim of this project is to find the best location for a company in the gaming industry. 
There are 87 employees in the company and different requirements from their side, which I have taken into account to make the final decision. 

Requirements/Libraries used:
- MongoClient
- Pandas
- Folium
- matplotlib.pyplot
- Seaborn
- os 
- requests
- dotenv
- json
- time

Methodology
I have queried the database called "Companies" using Mongo and found venues using the API of 4square. 
It is very difficult to comply with all the requirements, so I have focused on the most important ones:
 - Cost of living.
 - Vegan restaurants for the CEO.
 - Closeness to an airport. 
 - Nearby preschools (considering that the age of the employees is between 25 and 40, so that their kids could be toddlers).
 - Starbucks for Starbucks lovers.
 - Density of tech companies near the location. 

 Firstly, I have reduced the dataset filtering it by companies in the tech world: 
 - Analytics
 - Biotech
 - Cleantech
 - Games_video
 - Hardware
 - Nanotech
 - Network_hosting
 - Software
 - Web

Secondly, I have filtered the ones that have raised more than $1M. 

With these filters, I have already reduced the "Companies" dataset considering the requirements of the company.

Afterwards, I have made plots to check the most important countries. .

![top_10_countries] (https://github.com/Futurartina/Geospatial/blob/main/Data/Top%2010%20countries%20in%20Tech.jpg?raw=true)
USA is the most important in terms of tech companies that have raised more than $1M. 

![top_10_cities_USA] (https://github.com/Futurartina/Geospatial/blob/main/Data/Top%2010%20cities%20in%20Tech%20in%20USA.jpg?raw=true)
 I decided to check the cities in USA, and the one with more activity is San Francisco. 
San Francisco is big and there are many neighbourhoods. Therefore, I decided to take a look at the zip code. 

![top_zip_codes] (https://github.com/Futurartina/Geospatial/blob/main/Data/Top%2010%20zip%20code%20in%20Tech.jpg?raw=true)
The most repetead zip codes in USA are in San Francisco city and some other in Sunnyvale and surroundings (close to San Francisco.)
Based on these facts, I took the decision to compare San Francisco centre and Sunnyvale centre to check which is the most appropriate location for the company.
Having the cities defined, I focused on finding the airports, vegan restaurants, preschools and Starbucks in the specific area. 

![cities_map] (https://github.com/Futurartina/Geospatial/blob/main/Data/citiesmap.html)

To choose the city, I weighed the different requirements:
 - Cost of living (30%) - A lower cost of living will reduce mainly the office expenses.
 - Vegan restaurants for the CEO (20%) - We need to have the CEO happy so that he makes splendid decisions. 
 - Closeness to an airport (20%) - Easy transportation to an airport will avoid managers waste unnecessary time. 
 - Nearby preschools (15%) - Employees can take and pick their kids up easily and in less time. 
 - Starbucks for Starbucks lovers (10%) - People will work better if they have access to one of their favourite drinks. 
 - Density of tech companies near the location (5%) - The closeness of tech companies (including design companies) can help create a powerful and creative environment.
   Thus,  there could probably be collaborations with other start-ups. 

![SF_map] (https://github.com/Futurartina/Geospatial/blob/main/Data/SF_map.png?raw=true)

![SUN_map] (https://github.com/Futurartina/Geospatial/blob/main/Data/SUN_map.png?raw=true)

The coordinates chosen for each city are the coordenates for the city centre. 
The radius used for looking for venues in 4square has been 5 km.
The chosen outer_radius is 4 km from each city centre and the one for the inner_radius is 2 km from the city centre.

The carrot markers correspond to vegan restaurants.
The plane markers correspond to airports.
The green markers correspond to preschools.
The coffee markers correspond to Starbucks.

If we compare the two maps, take into consideration info from Mongo and the web, we can arrive at the following conclusions:
San Francisco:
  - There is more variety of vegan restaurants (20%).
  - There is a bigger quantity of Starbucks (10%).
  - The number of tech companies is higher (5%).
  The total sum of the different weights of San Francisco is 35%.

Sunnyvale:
  - The cost of living is lower than SF (30%).
  - The airport is close to the city (20%). 
  - There are more preschools in the city centre (15%).
  The total sum of the differents weight of Sunnyvale is 65%.

Undoubtedly, the city which would fit most the requirements would be Sunnyvale. 
It must also be considered that both cities are located in California (1 hour and 23 mins by car).
So, if the company wants to meet some other companies in San Francisco, it can be easily done. Besides, videoconferences exist nowadays!