# Assignment 3: MongoDB Setup and Queries

## Introduction
This document outlines the steps taken to complete the MongoDB setup and query assignment. It includes details on signing up for MongoDB Atlas, installing MongoDB Community Edition, running queries in MongoDB Compass, and the queries used to meet the assignment's requirements.

## Step 0: GitHub Repository Creation
A GitHub repository was created to host the assignment work. This repository includes:
- This Readme.md file documenting the assignment process.
- Code snippets used for MongoDB queries.
- Screenshots of MongoDB Compass interface showing the queries and their results.

## Step 1: Sign Up MongoDB Atlas
1. **MongoDB Account Creation:** An account was created at MongoDB Atlas using the following link: [MongoDB Atlas Registration](https://www.mongodb.com/cloud/atlas/register).
2. **Free Cluster Creation:** A free cluster was created following the instructions at [Create a Free Cluster](https://www.mongodb.com/docs/guides/atlas/cluster/).
3. **Database User Creation:** A database user was added as described here: [Add a Database User](https://www.mongodb.com/docs/guides/atlas/db-user/).
4. **Network Connection Configuration:** The network connection was configured using the guide found at [Configure a Network Connection](https://www.mongodb.com/docs/guides/atlas/network-connections/).
5. **Sample Data Loading:** Sample data was loaded into the cluster following [Load Sample Data](https://www.mongodb.com/docs/guides/atlas/sample-data/).
6. **Connection String Retrieval:** The connection string was retrieved using the instructions at [Get Connection String](https://www.mongodb.com/docs/guides/atlas/connection-string/).

## Step 2: Install MongoDB Community Edition
MongoDB Community Edition was installed following the guide at [Install MongoDB Community Edition](https://www.mongodb.com/docs/manual/administration/install-community/). The installation process was straightforward, and the connection to the Atlas cluster was successfully established using MongoDB Compass.

![MongoDB Compass Connection](path/to/your/screenshot.png)

## Step 3: Run Queries Using MongoDB Compass
Queries were executed within the embedded MongoDB Shell in MongoDB Compass. More information about using the shell can be found at [MongoDB Compass Embedded Shell](https://www.mongodb.com/docs/compass/current/embedded-shell/).

### Query 1: Movies with Runtime Greater Than 200 Minutes in Year 1983
The following query was used to find all movies from 1983 with a runtime greater than 200 minutes, showing the runtime, title, and year fields sorted by runtime in increasing order:
```javascript
db.movies.find(
  {
    $and: [
      { year: 1983 },
      { runtime: { $gt: 200 } }
    ]
  },
  {
    _id: 0,
    runtime: 1,
    title: 1,
    year: 1
  }
).sort({ runtime: 1 })
```
Query and Results Screenshot:

Query 2: Movies After Year 2014 with IMDb Rating Greater Than 9
This query finds all movies released after the year 2014 with an IMDb rating greater than 9, including the title, year, and IMDb rating:
```javascript
db.movies.find(
  {
    $and: [
      { year: { $gt: 2014 } },
      { "imdb.rating": { $gt: 9 } }
    ]
  },
  {
    _id: 0,
    title: 1,
    year: 1,
    "imdb.rating": 1
  }
)
```
Query and Results Screenshot:

Conclusion
This assignment provided a comprehensive overview of MongoDB Atlas setup, MongoDB Community Edition installation, and executing queries within MongoDB Compass. The hands-on experience gained from running actual queries and managing database operations was invaluable.

Please replace `path/to/your/screenshot.png`, `path/to/movies_runtime200_year1983.png`, and `path/to/movies_rating9_year2014.png` with the actual paths to your screenshots in your GitHub repository. Make sure to commit and push these screenshots along with your `Readme.md` file to your GitHub repository.
