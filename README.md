# ETLProject

(E)xtract: I extracted my data as json files returned from two different api\'92s. The first, 'https://randomuser.me/api/' was queried consecutively in batches of 50 and stored as a list of dictionaries. Data was also extracted from \'91http://api.openweathermap.org/data/2.5/weather?' corresponding to the approximate location of each of the users in our first dataset.

(T)ransform: Unfortunately, there wasn\'92t weather data available for every city found in our data set, so we created a list corresponding to the indexes of null values found in the list. More precisely, for weather data extracted which had a [\'91cod\'92] = \'91404\'92. After loading the data into a DataFrame and converting Kelvin temperatures to Fahrenheit, I stored users who lived in a city which had a daily temperature 70 or above. 

(L)oad: I chose to use mongoDB, mainly because of its ease of use, but also because if its scalability and flexibility. I created a collection for our target user group, and another for all of the users who\'92s data we extracted. 
