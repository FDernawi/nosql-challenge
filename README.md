# nosql-challenge
Before You Begin

    1.    Create a new repository for this project called nosql-challenge.
    •    Do not add this homework to an existing repository.
    2.    Clone the new repository to your computer.
    3.    Add your Jupyter notebook starter files and your Resources folder containing establishments.json to this folder.
    4.    Push the changes to GitHub.
    
    Files

    •    Download the following files to help you get started:
Module 12 Challenge files

Instructions

The UK Food Standards Agency evaluates various establishments across the United Kingdom and gives them a food hygiene rating. You’ve been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

Part 1: Database and Jupyter Notebook Set Up

Use NoSQL_setup_starter.ipynb for this section of the challenge.
    1.    Import the data provided in the establishments.json file from your Terminal.
    •    Name the database uk_food and the collection establishments.
    •    Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.
    2.    Within your notebook, import the libraries you need:
    •    PyMongo and Pretty Print (pprint).
    3.    Create an instance of the Mongo Client.
    4.    Confirm that you created the database and loaded the data properly:
    •    List the databases you have in MongoDB. Confirm that uk_food is listed.
    •    List the collection(s) in the database to ensure that establishments is there.
    •    Find and display one document in the establishments collection using find_one() and display with pprint.
    •    Assign the establishments collection to a variable to prepare the collection for use.
    
    {
    "BusinessName":"Penang Flavours",
    "BusinessType":"Restaurant/Cafe/Canteen",
    "BusinessTypeID":"",
    "AddressLine1":"Penang Flavours",
    "AddressLine2":"146A Plumstead Rd",
    "AddressLine3":"London",
    "AddressLine4":"",
    "PostCode":"SE18 7DY",
    "Phone":"",
    "LocalAuthorityCode":"511",
    "LocalAuthorityName":"Greenwich",
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
    "scores":{
        "Hygiene":"",
        "Structural":"",
        "ConfidenceInManagement":""
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },
    "RightToReply":"",
    "Distance":4623.9723280747176,
    "NewRatingPending":True
}

2.    Find the BusinessTypeID for “Restaurant/Cafe/Canteen” and return only the BusinessTypeID and BusinessType fields.
    3.    Update the new restaurant with the BusinessTypeID you found.
    4.    Remove establishments in Dover:
    •    Check how many documents contain the Dover Local Authority.
    •    Remove any establishments within the Dover Local Authority from the database.
    •    Check the number of documents to ensure they were deleted.
    5.    Convert string values to appropriate data types:
    •    Use update_many to convert latitude and longitude to decimal numbers.
    •    Use update_many to convert RatingValue to integer numbers.
    
    Part 3: Exploratory Analysis

Use NoSQL_analysis_starter.ipynb for this section of the challenge.

Exploration Questions

    1.    Which establishments have a hygiene score equal to 20?
    •    Use count_documents to display the number of documents contained in the result.
    •    Display the first document in the results using pprint.
    •    Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.
    2.    Which establishments in London have a RatingValue greater than or equal to 4?
    •    Use $regex as part of your search to handle the longer name of the London Local Authority.
    •    Use count_documents to display the number of documents contained in the result.
    •    Display the first document in the results using pprint.
    •    Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.
    3.    What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, “Penang Flavours”?
    •    Search within 0.01 degree on either side of the latitude and longitude.
    •    Limit results to establishments with a RatingValue of 5.
    •    Use the sort() method to sort in ascending order on the hygiene score.
    •    Use the limit() method to limit the results to 5.
    •    Print all five results using pprint.
    •    Convert the results to a Pandas DataFrame and display them.
    4.    How many establishments in each Local Authority area have a hygiene score of 0?
    •    Use the aggregation method to:
    •    Match documents with a hygiene score of 0.
    •    Group by LocalAuthorityName and count the number of documents.
    •    Sort the count in descending order.
    •    Print the first ten results using pprint.
    •    Convert the results to a Pandas DataFrame and display the first 10 rows.
    
    Requirements

Part 1: Database and Jupyter Notebook Set Up (15 points)

    •    Include the mongoimport command text in a markdown cell (3 points).
    •    Correctly drop existing establishments collection before importing (2 points).
    •    Name the database uk_food and the collection establishments (2 points).
    •    Correctly import PyMongo and Pretty Print (2 points).
    •    Create an instance of the MongoClient (1 point).
    •    List databases to confirm uk_food exists (1 point).
    •    List collections in uk_food to confirm establishments exists (1 point).
    •    Use find_one() and pprint to display a document (2 points).
    •    Assign the establishments collection to a variable (1 point).

Part 2: Update the Database (20 points)

    •    Insert “Penang Flavours” data (3 points).
    •    Query and return BusinessTypeID for “Restaurant/Cafe/Canteen” (3 points).
    •    Update “Penang Flavours” with the correct BusinessTypeID (3 points).
    •    Remove documents with LocalAuthorityName as “Dover” (3 points).
    •    Perform a count_documents() check before and after deletion (4 points).
    •    Convert latitude, longitude, and RatingValue fields to correct data types (4 points).

Part 3: Exploratory Analysis (55 points)

    •    Correct queries and results for all four exploration questions (details in instructions).

Deployment and Submission (6 points)

    •    Submit a GitHub link with project files (2 points).
    •    Use command line to add and commit files with appropriate messages (2 points).

Comments (4 points)

    •    Ensure concise, relevant comments for all code (4 points).
    
