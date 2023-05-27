# nosql-challenge
Module 12 Assignment
This assignment involved analysing UK food establishments for food hygiene Ratings and provide the data to the food magazine, Eat,Safe,Love inorder to help their journalists and food critics decide where to focus future articles.The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. 

### Part 1: Database set up: uk_foods and establishment collection via jupyter notebook
   - NoSQL_setup_starter.ipynb is used. 
   - establishments.json is imported into uk_food database using the terminal. collection name: establishments
   - libraries imported: PyMongo and Pretty Print(pprint)
   - Create an instance of the Mongo Client using localhost and specified port.
   - Confirm that you created the database and loaded the data properly, by listing the database, collections.
   - Find and display one document in the establishments collection using find_one and display with pprint.
   - Assign the establishments collection to a variable to prepare the collection for use.
   - Close mongoDB connection.

### Part 2: Updating the database
   - NoSQL_setup_starter.ipynb is used. 
   - An exciting new halal restaurant, Penang Flavors just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to   include it in your analysis. Add the following information to the database:
   - ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/95ced564-1ee8-41fe-9f5d-aafdcf26831f)

   - Query the database to find BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.
   - Update the new restaurant with the BusinessTypeID that was found.
   - The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local  Authority(994).Remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
   - Use update_many to convert latitude and longitude to decimal numbers.
   - Use update_many to convert RatingValue to integer numbers. However, This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. These non-numeric values need to be updated to nulls during the database setup before converting ratings to integers.
   ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/9fb38d9a-9bb5-4425-8c81-76049677f30e)

   - Assign the establishments collection to a variable to prepare the collection for use.
   - Close mongoDB connection.
   
    
### Exploratory Analysis: NoSQL_analysis_starter.ipynb is used for analysis

   - Dataset exploration: 
                        - RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.
                        - The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.
   - Use count_documents to display the number of documents contained in the result.- 38786
   - Display the first document in the results using pprint.
   - Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows. 
   - Which establishments have a hygiene score equal to 20?
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/4f6f03f0-c6ce-437f-8bb5-27f23585e63f)

   - Which establishments in London have a RatingValue greater than or equal to 4?
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/024b9d26-56af-4fb9-a6f4-6ade75dfc9e1)

   - What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/6fd02bca-94e6-4d26-9f5b-0c12b55c5c4e)

   - How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/4ee1c5a3-8ef8-457b-8397-222cee1e0fd4)

   - Extracting data for London establishments and saving the data into a csv for map plots: "Resources/london_ratings.csv"
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/71ed8c26-e02d-4e24-806e-d18b07ff8cb6)

   - Extracting data for all establishments(only those who have ratings) and saving the data into a csv for map plots: "Resources/all_establishments_rating.csv"
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/711ae729-ae75-4e93-b36f-f439d7463e5f)
      
   

### Map plot for London establishments.

   - London_Ratings_Map_plots.ipynb
   - Reads the london_ratings.csv into a dataframe, ranks the ratings as a column and plots into a map. 
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/7a7b6b5e-aa15-4f85-8c25-e5ef6df1f31b)
      
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/24dd4895-2614-4b04-a7f5-7db49854e9aa)


### Map plot for uk establishments.

   - All_Establishments_Ratings_Map_plots.ipynb
   - Reads the all_establishments_rating.csv into a dataframe, ranks the ratings as a column and plots into a map.
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/bea501f5-160a-4e16-a234-9acdfbb73570)
      ![image](https://github.com/BijoyetaK/nosql-challenge/assets/126313924/f6d4c3e5-896d-4e1e-9ed4-4c1047712288)

