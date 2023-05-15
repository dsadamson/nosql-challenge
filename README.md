# Using NoSQL to Set Up and Analyze Data

# Overview
For this project, I was asked to use NoSQL to set up and analyze business data, including several scores and points of location data. Using tools like MongoClient and Regex, I was able to accomplish these tasks.

# Instructions

Be sure to have the following dependencies on your local machine and in a cell at the beginning of your Jupyter Notebook:

    import pymongo
    from pymongo import MongoClient
    from pprint import pprint
    import pandas as pd

Moreover, be sure to import the database, using the following line of code:

    % mongoimport --type json -d uk_food -c establishments --drop --jsonArray /Resources/establishments.json

Otherwise, simply clone the Jupyter Notebook onto your computer, select the correct Python kernel, and run both Notebooks.

# Features

Both Jupyter Notebooks begin in similar ways after importing the database in the terminal. In both, the MongoClient is set to its default port, then the database is set to a variable. Next, the databases and collections are listed to ensure that they were correctly imported. 

In the setup Notebook, I was asked to append the 'establishments' collection with a document about a restaurant that had been excluded. I copy-and-pasted this document into the Jupyter Notebook, set it to a variable, and used an 'insert_one' function to place it into the collection. Because this added restaurant, Penang Flavours, was also missing its 'BusinessTypeID', I used a 'find_one' function to find an establishment with the same 'BusinessType' and to extract its 'BusinessTypeID'. I used an 'update_one' function to set the BusinessTypeID for the added document. Finally, I used several 'update_many' functions to turn coordinate data to decimals and 'RatingValue' to decimals.

In the analysis Notebook, I was asked to answer several questions about the data imported in the setup Notebook. Often, the basis of these answers was using 'find' and find_one' functions to find businesses that met several criteria. However, some of the questions offered some obstacles. For example, question 2 asked me to find the businesses in London with a rating value greater than or equal to 4. Unfortunately, I couldn't find any businesses with London as their designated local authority, as I was told to. Instead, I decided to use the fourth line of address data to find businesses in London with these rating values; this seemed to be where city data was placed for each business based in London. However, future revisions may need to use a different method, as there seems to be a discrepency between my answer and the correct answer given by the assignment. 

# Acknowledgements

This assignment and data were provided by the Data Visualization and Analytics Bootcamp at The Ohio State University. This program sourced the data from UK Food Standards AgencyLinks (2022). UK food hygiene rating data API. https://ratings.food.gov.uk/open-data/en-GBLinks to an external site.. Contains public sector information licensed under the Open Government Licence v3.0Links to an external site.
Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).

# Author
Daniel Adamson
