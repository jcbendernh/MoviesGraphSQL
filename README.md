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