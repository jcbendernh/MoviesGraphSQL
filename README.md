# MoviesGraphSQL

Movies Sample Database for SQL Graph and Power BI

This repo provides 12 SQL Notebooks that can be executed in Azure Data Studio to create a Movies Graph SQL demo database.

I created this repo because when I was looking to evaluate Graph SQL for a customer, I could not find a good sample/demo database.  Thus, I created these Notebooks using a Neo4J sample set and retrofitted the data structure to Azure Graph SQL.

To execute the notebooks, download the [Movies.zip](./files/Movies.zip) file and install [Azure Data Studio](https://learn.microsoft.com/en-us/azure-data-studio/what-is-azure-data-studio).

Here is a summary of the Notebooks

1.  01 - Reference Data - Creates the reference NODE tables of Countries, Gender, Genre, Language, Language Role and Department and populates them with data. 
2.  02 - Keyword - Creates the Keyword NODE table and populates the table.