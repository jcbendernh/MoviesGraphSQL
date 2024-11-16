# Movies Sample Database for SQL Graph and Power BI

## Overview
This repo provides 13 SQL Notebooks that can be executed in Azure Data Studio to create a Movies Graph SQL demo database.

I created this repo because when I was looking to evaluate Graph SQL for a customer, I could not find a good sample/demo database.  Thus, I created these Notebooks using a Neo4J sample set and retrofitted the data structure to Azure Graph SQL.

To execute the notebooks, download the [Movies.zip](./files/Movies.zip) file and install [Azure Data Studio](https://learn.microsoft.com/en-us/azure-data-studio/what-is-azure-data-studio).

## Notebooks
Here is a summary of the Notebooks

*  01-Reference Data - Creates the reference NODE tables of Countries, Gender, Genre, Language, Language Role and Department and populates them with data. 
*  02-Keyword - Creates the Keyword NODE table and populates the table.
*  03-Person - Creates the Person NODE table and populates the table>.
*  04-ProductionCompany - Creates the Production_Company NODE table and populates the table.
*  05-Movies - Creates the Movies NODE table and populates the table.
*  06-MovieCast - Creates the Movie_Cast EDGE table and populates the table via a lookup table and view.  It also creates the EDGE constraint of Movies to Person.
*  07-MovieCompany - Creates the Movie_Company EDGE table and populates the table via a lookup table and view.  It also creates the EDGE constraint of Movies to Production_Company.
*  08-MovieCrew - Creates the Movie_Crew EDGE table and populates the table via a lookup table and view.  It also creates the EDGE constraint of Movies to Person.
*  09-MovieGenres - Creates the Movie_Genres EDGE table and populates the table via a lookup table and view.  It also creates the EDGE constraint of Movies to Genre.
*  10-MovieKeywords - Creates the Movie_Keywords EDGE table and populates the table via a lookup table and view.  It also creates the EDGE constraint of Movies to Keywords.
*  11-MovieLanguages - Creates the Movie_Languages EDGE table and populates the table via a lookup table and view.  It also creates the EDGE constraint of Movies to Languages.
*  12-ProductionCountry - Creates the Production_Country EDGE table and populates the table via a lookup table and view.  It also creates the EDGE constraint of Production to Country.
*  13-Database Queries - Contains various queries to sample the data.

## Power BI
I have also included a [Movies.pbix](/files/Movies.pbix) sample report that uses the [Force-Directed Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) add in for Power BI, I was able to do some interesting visuals, see below for reference.

Query Used for Power BI
```sql
SELECT 
    p.person_name AS actor
    , m.title as movie
    , mc.gender as gender
    , c.country_name as country
FROM 
    person p, 
    movie_cast mc, 
    movie m, 
    production_country pc, 
    country c
WHERE 
    MATCH (p<-(mc)-m-(pc)->c)

ORDER BY 
    p.person_name ASC
```

The report shows a visual of top 25 actors by movie count per country.<BR>&nbsp;<BR>

![alt picture](/img/powerbi1.jpg)

If I drill through to a certain actor, I can see a graph visual via the force directed graph add in.<BR>&nbsp;<BR>

![alt picture](/img/powerbi2.jpg)

...

![alt picture](/img/powerbi3.jpg)

If I click on a certain movie, the graph shows me the sub-nodes for that movie. 

![alt picture](/img/powerbi4.jpg)