# Final-Project-Statistical-Modelling-with-Python

## This project was made possible because the the citybikes API, which can be found here: http://api.citybik.es/v2/

## Project/Goals
- To apply and practice python, and relevent libraries, with environment that resembles the real world.
- Practice pushing changes to github after every session or change as opposed to one big push at submission.
- Develop code that is clean and concise with the knowledge I have.
- Seek help when I need to and have exhausted all efforts.
- Accept that I need to explain my process to others in order to see the flaws in my methods.
- As always, have fun

## Process
### _Citybikes_
1. Created the a remote repository (repo) on my github and cloned it to my local machine,
2. Created my goals for this project in no particular order, 
3. Did a initial run through of the project to determine a plan and identify areas where I may be strong or weak,
4. Connected to the City Bikes API for Vancouver, BC,
5. Accessed relevent information from the JSON result and created a dictionary,
6. Put dictionary from above into a dataframe and initialized an empty dictionary,
7. Looped through the dataframe to create keys and a list of values,
8. Converted dictionary into a dataframe,
9. From the dataframe I created a list of lists for latitude and longitude pairs from the dataframe so that I could call the list in the yelp and foursquare notebook,
### _Yelp and Foursquare_
10. I created environment variables for my api keys to call and use,
11. I made calls to the appropriate API's to get the data and load into a list,
12. I save the collection of responses as a separate file for later use as credit/call limits were a concern for me,
13. I looped through the list of data to get the data I wanted - sometimes I had to load it all with the intention of modifying the dataframe,
14. I had nested dictionaries in in my raw data df so I created a new df with the expanded data (e.g., location or address)
15. I joined the new df with the raw df, and proceeded to drop the irrelevant columns to get my final df
16. I got the top 10 locations by rank for each df and then compared the df from Foursquare and Yelp for similarites,
### _Joining data from part 1 and 2_
17. Imported relevent libraries and orginal df
18. Joined df individually then together
19. Checked for duplicates in combined data
20. Performed a describe function to get an overlay of the data; saw I had some outliers and some 0's
21. Created some visualizations of the combined data
22. Loaded the data into a db and created tables for relevent df
### _model building_
23. Decided to build two models - forward and backward selection
24. Imported the data from the db I created
25. I decided on the following questions: Do the restaurant characteristics(e.g., price) have an impact on the number of bikes in a location?
26. Dropped irrelevent columns to my analysis and due to time constraints, I dropped NaN values from my analysis
27. Built separate models which ended up having the same variables, but very different R2 values



## Results
(fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model.)
I found the City Bikes API quite comprehensive. The interesting comparison was between Foursquare and Yelp. Foursquare had 2429 raw results while Yelp had 3834 raw results from the API. Foursquare did have more features like total photos, while Yelp was pretty basic. The difference is results could be because Yelp is an older company, and thus has better reviewer base and trust as opposed to Foursquare. This was outlined in this [article](https://medium.com/similar-app-development/yelp-vs-foursquare-two-similar-platforms-with-a-completely-different-approach-8bd40ae895e2).

The models did not yield anything interesting. My forward selection model resulted and adjusted R2 value of 57% when only total_ratings and distance was included. The backward selection model was indicated an even worse fit. The adjusted R2 value was 17% or less depending on the variables removed. I removed distance first price first evne though its p-value was less than 0.05, but it was the highest. This did not impact the adjusted R2 value, but the p value for rating did increase to 0.055. This was subsequently removed and, again, there was no change in the R2 value.

Overall, I don't think there is any relation between restaurant features and the number of bikes. The results could heavily depend on the city in which the bike stations are in. For instance, the location's features like geography, weather, public transit infrastructure, cycling infrastructure and culture, and outdoor areas for cycling. Perhaps resaurants (dining and drinking establishments) were a poor point of interest.

## Challenges 
- Connecting to the citybike api, seemed to be missing data initially. Results deviated from documentation
- looping through the results from the API's, nested dictionaries were extremely difficult and part 2 took a week for me to do
- had a bad habit of not commiting frequently and appropriately had VS Code crash on me, but luckily I copied and pasted my code in a separate file. what a nightmare...
- connecting and building a database, I'm still trying to juggle WSL on Windows and some of the tools we use
- building and using functions, I tried some for the database portion, but I was not able to identify parts of the project where I would do something multiple times. For this project, I found it easier to just code
- 


## Future Goals
- Define and use more functions,
- I want to become more proficient with the syntax and Google less. Right now, I am Googling around 80% of the time,
- SLOW DOWN, I need to really focus on small portion at a time and commmit them to Github
- I would like to start building my own projects now, I feel like I may learn better that way
- Long term: get a DS or DA job