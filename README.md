# ECE-2112-Programming-Assignment-3-
This repository contains the contents of my programming assignment 3 for my class, ECE 2112. Alongside, the appropriate explanations for each portion of the code to facilitate ease of understanding. 

LAO, JARED RUSELL CHUA
2ECE-B

A. POSITIONAL AND LABEL-BASED SLICING


1. import pandas as pd - A line of code that imports the pandas library, and allows it to be used as the shortcut pd

2. cars = pd.read_csv('cars.csv') - Using the syntax pd.function, this line of code utilizes the .read_csv to read the uploaded cars.csv file

3. cars.shape - Using the attribute .shape, we are able to get the shape of the dataframe of the cars.csv file

4. cars.columns - Using the .columns attribute, it gets all of the column names of the cars.csv file

5. cars_6_to_10 = cars.iloc[6:11] - Using the integer location, .iloc, indexer while using the concept of index slicing, we are able to get rows 6 to 10 of the cars_csv file
Note: in the index slicing, 6 is the starting point, and 11 is the ending point, excluding 11.

6. cars_6_to_10 = cars.loc[6:10, ['Model', 'mpg', 'cyl', 'hp', 'gear']] - Similarly, this code uses the location indexer, which splits the indexing into rows and columns. 

    6a. Rows: the 6:10 portion of the index is a range; this time not index slicing, because the .loc method has an inclusive indexing

    6n. Column: The ['Model', 'mpg', 'cyl', 'hp', 'gear'] is the column portion of the code, emphasizing that you only want the columns previously listed

B. MODEL LOOKUP


1. toyota = cars[cars["Model"] == "Toyota Corolla"] - This is a boolean condition that retunrs the row of Toyota Corolla, the way it works is that when the compiler scans the dataframe, it would put false on everything that isn't equivalent to the model, Toyota Corolla, so when it reaches that model, it would give back true, then you simply put that condition inside the dataframe and you can get the row.

2. pontiac = cars.loc[cars["Model"] == "Pontiac Firebird"] [["Model", "mpg", "hp", "wt"]] - Similarly, here when the Model follows the condition of equating to Pontiac Firebird you get the same result, but using .loc one is able to add the column portion having the format of cars.loc[condition][columns] which initially gets the row then gets the columns

C. MULTI-MODEL SUBSETTING


1. selected_cars = pd.concat([
    cars[cars["Model"] == "Datsun 710"],
    cars[cars["Model"] == "Lotus Europa"],
    cars[cars["Model"] == "Ferrari Dino"]
])
selected_cars = selected_cars [["Model", "mpg", "cyl", "hp", "gear"]]

1a. pd.concat - this portion of the code is what allowed me to combine all 3 rows into one thing, as if I had used the same syntax in the previous numbers as before, it would result in an error. 

1b. 
[cars[cars["Model"] == "Datsun 710"],
cars[cars["Model"] == "Lotus Europa"],
cars[cars["Model"] == "Ferrari Dino"]] - This portion of the code uses the same logic as before and using bolean conditioning, gets the following rows: Datsun 710, Lotus Europa, and Ferrari Dino

1c. selected_cars = selected_cars [["Model", "mpg", "cyl", "hp", "gear"]] - This portion of the code was what allowed the combined 3 rows to have only the 5 instructed columns, and furthermore it also reassigned selected_cars to have it hold the new selected_cars dataframe instead of the old one 

2. selected_cars.shape - this gets the shape of the selected_cars dataframe 

