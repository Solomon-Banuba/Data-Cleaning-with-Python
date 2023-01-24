# Data-Cleaning-with-Python

Data cleaning is an important step in any data science/analytics project.
In this project covers ways to detect and fix anomalies in dataset in python.
The following steps:

 #### 1. Import the Library
    import pandas as pd
    import numpy as np
    
#### 2. Import the dataset
    df = pd.read_csv('df.csv')
    
#### 3. Inspect the dataset
###### Checking columns to ensure consistent naming conversion
    # Read column names 
    
      df.columns
      
    # Dealing with inconsistent naming
    ## Change the column names to lower/upper case
    
            df.columns.str.lower()
    
            df.columns.str.upper()
    
    ## Renaming Columns
    
            df = df.rename(columns={'engine fuel type':'fuel_type', 
                     'engine hp':'hp', 
                     'engine cylinders': 'cylinders',
                     'transmission type': 'transm_type',
                     'driven_wheels':'wheels',
                     'number of doors':'doors',
                     'market category': 'market_category',
                     'vehicle size':'vehicle_size',
                     'vehicle style' : 'vehicle_style',
                     'highway mpg': 'highway_mpg',
                     'city mpg': 'city_mpg'})
                     
    ## Inspecting the number of rows and columns
    
                df.shapes
    
    ## Checking for data types
    
                df.dtypes
    
 #### Missing Values
        
               df.isnull().any()
               
               df.isnull().sum()
               
###### Dealing with Missing Values 

     ## Fill in with zero
            
                df_with_0 = df.fillna(0)
          
     ## Filling a specific (numeric) column with the mean
          
                   df_with_mean_hp = df.hp.fillna(df['hp'].mean())
           
      ## Dropping missing/ NaN values
          
                    df_drop_na = df.dropna()
                    
       ## Dropping with condition/threshold
            # Remove null column beyond a threshold
            # say 60% (0.6) null values in a column
            
                    threshold = len(cars)*.6
                    print(threshold)
                    
            # Dropping columns that have over 60% null values
                    
                   df.dropna(thresh=threshold, axis = 1)
            
#### Remove Duplicates values 
        
                   df.drop_duplicates(inplace = True)

                
                    
          
                
                
                
   
