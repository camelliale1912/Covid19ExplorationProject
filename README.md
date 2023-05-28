
# Covid 19 Exploration Project




## Authors

- Github: [@camelliale1912](https://www.github.com/camelliale1912)
- Linkedin: www.linkedin.com/in/tra-le-nguyen-huong




## Summary of Project
The project involved analyzing data from two tables, CovidDeaths and CovidVaccinations, in SQL Server Management Studio to gain insights into the COVID-19 situation in the years 2020 and 2021.

The analysis started with an overview of the data from the CovidDeaths table, including information about the continent, location, date, total cases, new cases, total deaths, and population. The data was sorted by different criteria to provide a comprehensive view of the COVID-19 situation.

The analysis then focused on specific aspects, such as the comparison of total cases and total deaths in the United States, as well as the relationship between total cases and population in the United States. These queries provided valuable information about the impact of COVID-19 in the country.

## Datasets
`CovidDeaths.csv` - Uncleaned dataset focused on COVID-19 cases and deaths, providing detailed information on the number of confirmed cases, new cases, total deaths, and daily deaths from 2020-2021 scraped from Our World in Data website.

`CovidVaccinations.csv` - Uncleaned dataset concentrated on COVID-19 vaccinations, offering data on the number of vaccine doses administered, vaccination rates, and the distribution of vaccines across countries scraped from Our World in Data website.
## Technical Implementation: SQL Code Summary
**Select statement:**
Used in multiple queries to retrieve specific columns from the tables.

**Aggregate function:**
Used in various queries to perform calculations on a set of rows.
*Examples:
MAX: Used to find the maximum value (e.g., MAX(total_cases)).
SUM: Used to calculate the sum of values (e.g., SUM(new_cases)).*

**Calculation:**
Used to perform mathematical operations on columns or values.
*Examples:
Division: Used to calculate percentages (e.g., (total_deaths/total_cases)*100).*
CAST: Used to convert data types (e.g., MAX(cast(Total_deaths as int))).*

**Common Table Expression (CTE):**
Used to create a named temporary result set that can be referenced multiple times within a query. It is defined using the "WITH" keyword and can include multiple SELECT statements.
*Example:
PopvsVac: A CTE that calculates the rolling number of vaccinated individuals.*

**Group by statement:**
Used to group rows with similar values together based on a specific column or columns. 
*Example:
Group by location, population: Groups data by location and population.*

**Order by statement:**
Used to sort the result set in ascending (default) or descending order. 
*Example:
Order by 1,2: Orders the result set by the first and second columns.*

**Join statement:**
Used to combine rows from two or more tables based on a related column between them. 
*Example:
Join CovidDeaths dea JOIN CovidVaccinations vac ON dea.location = vac.location AND dea.date = vac.date.*

**Temp table:**
Used to create and store temporary data during the execution of a query.
*Example:
#PercentPopulationVaccinated: A temporary table that stores the results of a query.*

**View:**
Used to create a virtual table that stores a query's result set and can be referenced later.
*Example:
PercentPopulationVaccinated: A view created to store data for later visualizations.*

**Partition by clause:**
Used in conjunction with aggregate functions to divide rows into partitions based on specified criteria. *Example:
Partition by dea.Location 
Order by dea.location, dea.Date: Defines the partition for the rolling number of vaccinated individuals based on location and ordered by location and date.*
