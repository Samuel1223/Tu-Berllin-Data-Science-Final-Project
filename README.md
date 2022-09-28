# Tu-Berllin-Data-Science-Final-Project
# When I was learning in the online program, we be asked to finish this data analysis project
# the question are designed as following:
### Plan of attack:

1. **Load the crime data set in 'data/crime_data.csv' and investigate: (5%)**
    1. From what city is this data? (Lat and Long might help) (Use Google)
    2. From which year(s) is the data?
    3. How many crimes have been reported in total? (each row of the data refers to one reported crime.)


2. **Clean the the data: (25%):**
    1. remove the columns: "UCR PARTS" and "Location", which are not needed 
    2. the column "SHOOTING" only has the value `"Y"` (for yes) inside, if a shooting was reported for that crime. Otherwise, this value is NaN (not a number). Therefore clean this column by placing a `"N"` (for no) when no shooting was reported. 
    3. only use rows which where committed in the year __2017__, therefore remove other years.
    4. remove any row with incomplete data, e.g. remove any row which still has empty values.
    5. Save the cleaned data under 'data/clean_crime.csv' and use it for plotting.


3. **Create the following plots and answer the attached question: (60%)**
    1. Create a bar chart, which displays the frequency of each crime type (use the column OFFENSE_CODE_GROUP). What is the most frequent crime type?
    
    2. Show the total crime count per hour for all days of the week. Therefore, create a line chart with the hours of a day on the x-axis and the total count of crimes on the y-axis. How does crime proceed during the day?
    
    3. For each district, create a Pie Chart, which shows the count of crimes for each street. Some districts have quite a lot of streets, therefore only display the **7** top streets. What is the street with most crimes for each district?
    
    4. Create a Map, which displays the crime types:
        1. Robbery
        2. Auto Theft
        3. Simple Assault
        4. Larcency
        5. Drug Violation
        6. Crimes with SHOOTING
        
       Therefore, plot the Lat and Long values as X- and Y-values in a scatter plot, and give each crime type a different marker. Since we want to focus on the city center, remove outliers (42.2< Lat < 42.4 and -71.2< Long < -70.9)(Check again the order of Lat and Long on your axis). What is the hotspot (mean) of each crime type? 
    5. __(Extra Credit)__ You may create any additional interisting plots, which you can present to your coworkers! 
       
       
4. **Finally, we want to use our skills to detect/predict crime in this city. Therefore, we want to build a classifier, which predicts the type of crime when it occurs. (10%)**
    1. Load the training data for a machine learning classifier in _'data/crime_training_data.csv'_ and corresponding training labels in _'data/crime_training_labels.csv'_.
    2. Train a classifier of your choosing with the training data set. 
    3. Predict the crime type (labels) of reported crimes in _'data/crime_test_data.csv'_.
    4. Save the predictions in a _.csv_ file.
    
### Hand in:
Hand in the following files in a _.zip_ file:
   - your code in a jupyter notebook (_.ipynb_) or standard python source code (_.py_).
   - a _.pdf_ with your findings and plots (you can easily create a PDF in juypter notebook under ->File-> Download as-> PDF via Latex, might need to install some software)
   - your predictions as a _csv._ file.
   
The _.zip_ file should have your name(s) in them, ex: _project_jason_harris.zip_.

Send the _.zip_ file to harris.e.jason@gmail.com before **Friday 29th, January 2021**.  


### Note on implementation:
- for each task, create a cell and answer the question(s) with 1-2 sentences in a markdown cell.
- when plotting, try to create one plot, before creating multiple plots for different districts or crime types
- try to use techniques learned in the course! Many similar problems have been used in the lectures/exercises
- don't hesitate to ask for help!
- You are free to use any classification algorithm that you want. If you find better recommendation approaches on the web(there certainly are better, but also more involved ones), you are free to use those.
- Some proven algorithms, other than the ones learned in the lectures are: 
    - https://towardsdatascience.com/intro-to-recommender-system-collaborative-filtering-64a238194a26
    - https://towardsdatascience.com/prototyping-a-recommender-system-step-by-step-part-1-knn-item-based-collaborative-filtering-637969614ea
"""

# Commented out IPython magic to ensure Python compatibility.
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
# %matplotlib inline
