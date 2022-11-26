# Adeniyi
SPAIN CRIME STATISTICS
/*creating the database*/
create database crime;


/*IMPORTING THE DATASET INTO MYSQL WORKBENCH AND VIEWING THE TABLES*/
select * from crime_rate_spain;

/*CHECKING FOR NULL VALUES*/
select * from crime_rate_spain
where total_cases is null;


/*SHOWING CRIME TYPE AND THE TOTAL CASES DESCENDING ORDER*/
select distinct(crime) as crime_type, sum(total_cases) as total_crimes
from crime_rate_spain
where year = 2021
group by crime
order by total_cases desc;


/*SHOWING THE ORDER OF CRIME TYPE COMMITTED IN 2019*/
select distinct(crime) as crime_type, sum(total_cases) as total_crimes
from crime_rate_spain
where year = 2019
group by crime
order by total_cases desc;


/*SHOWING THE ORDER OF CRIME TYPE COMMITTED IN 2020*/
select distinct(crime) as crime_type, sum(total_cases) as total_crimes
from crime_rate_spain
where year = 2020
group by crime
order by total_cases desc;


/*SHOWING THE ORDER OF CRIME TYPE COMMITTED IN 2021*/
select distinct(crime) as crime_type, sum(total_cases) as total_crimes
from crime_rate_spain
where year = 2021
group by crime
order by total_cases desc;


/*SHOWING RESULT OF LOCATION WITH THE HIGHEST NUMBER OF CRIME*/
select distinct(crime) as crime_type, max(total_cases) as highest_crime 
from crime_rate_spain;


/*SHOWING RESULT FOR LOCATION WITH THE LOWEST NUMBER OF CRIME*/
select distinct(crime) as crime_type, min(total_cases) as lowest_crime_roported
from crime_rate_spain;


/*SHOWING RESULT OF LOCATION, YEAR AND TOTAL CASES RECORDED*/
select distinct(location), year, sum(total_cases) as total_crimes
from crime_rate_spain
group by location, year
order by location;


/*GROUPING YEAR WITH TOTAL NUMBER OF CASES*/
select distinct(year), sum(total_cases)
from crime_rate_spain
group by year;


/*TOP 5 LOCATION WITH TOTAL NUMBER OF CASES*/
select distinct(location), sum(total_cases) as total_crimes
from crime_rate_spain
group by location
order by total_cases desc
limit 5;


/*TOP 5 CRIME TYPE*/
select distinct(crime) as crime_type, sum(total_cases) as total_crimes
from crime_rate_spain
group by crime
order by total_cases desc
limit 5;


/*TOTAL NUMBER OF CRIME COMMITTED*/
select sum(total_cases) 
from crime_rate_spain;
![spain dashboard](https://user-images.githubusercontent.com/100759379/204086370-1f2da396-6c7e-4f74-8d68-d285c115c10a.png)
