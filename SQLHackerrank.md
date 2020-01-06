# SQL Practice Problems Hackerrank
# Basic SELECT Queries

## 1. Revising the Select Query I

Query all columns for all American cities in **CITY** with populations larger than 100000. The CountryCode for America is USA. The **CITY** table is described as follows: 

Input Format:

![Q1](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

Solution:
```SQL
SELECT *
FROM CITY
WHERE COUNTRYCODE ='USA' AND POPULATION > 100000;
```

## 2. Revising the Select Query II

Query the names of all American cities in **CITY** with populations larger than 120000. The CountryCode for America is USA.The **CITY** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

Solution:
```SQL
SELECT NAME
FROM CITY
WHERE COUNTRYCODE ='USA' AND POPULATION > 120000;
```

## 3. Select All

Query all columns (attributes) for every row in the **CITY** table.The **CITY** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

Solution:
```SQL
SELECT *
FROM CITY;

```

## 4. Select By ID

Query all columns for a city in **CITY** with the ID 1661.The **CITY** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

Solution:
```SQL
SELECT *
FROM CITY
WHERE ID = 1661;
```

## 5. Japanese Cities' Attributes

Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN. The **CITY** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

Solution:
```SQL
SELECT *
FROM CITY
WHERE COUNTRYCODE ='JPN';
```

## 6. Japanese Cities' Names

Query the names of all the Japanese cities in the **CITY** table. The COUNTRYCODE for Japan is JPN. The **CITY** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

Solution:
```SQL
SELECT NAME
FROM CITY
WHERE COUNTRYCODE ='JPN';
```

## 7. Weather Observation Station 1

Query a list of CITY and STATE from the **STATION** table where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT CITY, STATE
FROM STATION;
```

## 8. Weather Observation Station 3

Query a list of CITY names from **STATION** with even ID numbers only. You may print the results in any order, but must exclude duplicates from your answer, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE MOD(ID,2)=0 ;
```

## 9. Weather Observation Station 4

Let **N** be the number of CITY entries in **STATION**, and let **N'** be the number of distinct CITY names in **STATION**; query the value of **N-N'** from **STATION**. In other words, find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT (COUNT(CITY) - COUNT(DISTINCT CITY))
FROM STATION;
```

## 10. Weather Observation Station 5

Query the two cities in **STATION** with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:
![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Sample Input:
Let's say that CITY only has four entries: DEF, ABC, PQRS and WXY

Sample Output:
```
ABC 3
PQRS 4
```
Explaination:
When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with the respective lengths **3,3,4** and **3**. The longest-named city is obviously PQRS, but there are **3** options for shortest-named city; we choose ABC, because it comes first alphabetically.

**Note:**
**You can write two separate queries to get the desired output. It need not be a single query.**

Solution:
```SQL
SELECT CITY, CHAR_LENGTH(city)
FROM STATION
WHERE city = (SELECT MIN(city)
              FROM STATION
              WHERE CHAR_LENGTH(city) = ( SELECT MIN(CHAR_LENGTH(city))
                                          FROM STATION)
)

OR 

city = (SELECT MIN(city)
        FROM STATION
        WHERE CHAR_LENGTH(city) = (SELECT MAX(CHAR_LENGTH(city))
                                   FROM STATION)
)
```

## 11. Weather Observation Station 6

Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from **STATION**. Your result cannot contain duplicates, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%' 
ORDER BY CITY ASC; 
```


## 12. Weather Observation Station 7

Query the list of CITY names ending with vowels (a, e, i, o, u) from **STATION**. Your result cannot contain duplicates, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT DISTINCT(CITY) 
FROM STATION 
WHERE CITY LIKE '%A' 
OR CITY LIKE '%E' 
OR CITY LIKE '%I' 
OR CITY LIKE '%O' 
OR CITY LIKE '%U';  
```

## 13. Weather Observation Station 8

Query the list of CITY names from **STATION** which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT DISTINCT(CITY) 
FROM STATION 
WHERE (CITY LIKE '%A' 
OR CITY LIKE '%E' 
OR CITY LIKE '%I' 
OR CITY LIKE '%O' 
OR CITY LIKE '%U')
AND
(CITY LIKE 'A%' 
OR CITY LIKE 'E%' 
OR CITY LIKE 'I%' 
OR CITY LIKE 'O%' 
OR CITY LIKE 'U%');   
```

## 14. Weather Observation Station 9

Query the list of CITY names from **STATION** that do not start with vowels. Your result cannot contain duplicates, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT DISTINCT CITY
FROM STATION 
WHERE UPPER(SUBSTR(CITY,1,1)) NOT IN ('A','E','I','O','U');    
```


## 15. Weather Observation Station 10

Query the list of CITY names from **STATION** that do not end with vowels. Your result cannot contain duplicates, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT DISTINCT CITY 
FROM STATION 
WHERE LOWER(SUBSTR(CITY, LENGTH(CITY),1)) NOT IN ('a','e','i','o','u');    
```



## 16. Weather Observation Station 11

Query the list of CITY names from **STATION** that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT DISTINCT CITY 
FROM STATION 
WHERE LOWER(SUBSTR(CITY,1,1)) NOT IN ('a','e','i','o','u') 
OR 
LOWER(SUBSTR(CITY, LENGTH(CITY),1)) NOT IN ('a','e','i','o','u'); 
```


## 17. Weather Observation Station 12


Query the list of CITY names from **STATION** that do not start with vowels and do not end with vowels. Your result cannot contain duplicates, where LAT_N is the northern latitude and LONG_W is the western longitude. The **STATION** table is described as follows: 

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

Solution:
```SQL
SELECT DISTINCT CITY 
FROM STATION 
WHERE LOWER(SUBSTR(CITY,1,1)) NOT IN ('a','e','i','o','u') 
AND 
LOWER(SUBSTR(CITY, LENGTH(CITY),1)) NOT IN ('a','e','i','o','u');
```


## 18. Higher Than 75 Marks


Query the Name of any student in **STUDENTS** who scored higher than **75** Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

The **STUDENTS** table is described as follows:  
The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

Input Format:

![Q2](https://s3.amazonaws.com/hr-challenge-images/12896/1443815243-94b941f556-1.png)

Sample Input:

![Q3](https://s3.amazonaws.com/hr-challenge-images/12896/1443815209-cf4b260993-2.png)

Sample Output:
```
Ashley
Julia
Belvet
```

Explanation:
Only Ashley, Julia, and Belvet have Marks > **75**. If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.

Solution:
```SQL
SELECT NAME 
FROM STUDENTS
WHERE MARKS>75
ORDER BY SUBSTR(NAME, LENGTH(NAME)-2, LENGTH(NAME)), ID;
```



## 19. Employee Names


Write a query that prints a list of employee names (i.e.: the name attribute) from the **Employee** table in alphabetical order.

Input Format:

The **Employee** table containing employee data for a company is described as follows:

![Q2](https://s3.amazonaws.com/hr-challenge-images/19629/1458557872-4396838885-ScreenShot2016-03-21at4.27.13PM.png)

In this table, employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

Sample Input:

![Q3](https://s3.amazonaws.com/hr-challenge-images/19629/1458558202-9a8721e44b-ScreenShot2016-03-21at4.32.59PM.png)

Sample Output:
```
Angela
Bonnie
Frank
Joe
Kimberly
Lisa
Michael
Patrick
Rose
Todd
```


Solution:
```SQL
SELECT NAME
FROM EMPLOYEE
ORDER BY NAME;
```


## 20. Employee Salaried


Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than **$2000** per month who have been employees for less than **10** months. Sort your result by ascending employee_id.

Input Format:

The **Employee** table containing employee data for a company is described as follows:

![Q2](https://s3.amazonaws.com/hr-challenge-images/19629/1458557872-4396838885-ScreenShot2016-03-21at4.27.13PM.png)

In this table, employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

Sample Input:

![Q3](https://s3.amazonaws.com/hr-challenge-images/19629/1458558202-9a8721e44b-ScreenShot2016-03-21at4.32.59PM.png)

Sample Output:
```
Angela
Michael
Todd
Joe
```

Explanation:

Angela has been an employee for **1** month and earns **$3443** per month.
Michael has been an employee for **6** months and earns **$2017** per month.
Todd has been an employee for **5** months and earns **$3396** per month.
Joe has been an employee for **9** months and earns **$3573** per month.
We order our output by ascending employee_id.


Solution:
```SQL
SELECT NAME
FROM EMPLOYEE
WHERE SALARY>2000 AND MONTHS<10
ORDER BY EMPLOYEE_ID;
```

# Advance SELECT Queries

## 1. New Companies


Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy: <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458531031-249df3ae87-ScreenShot2016-03-21at8.59.56AM.png)

Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

**Note:**

* The tables may contain duplicate records.
* The company_code is string, so the sorting should not be **numeric**. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.

**Input Format:**

The following tables contain company data:

* **Company**: The company_code is the code of the company and founder is the founder of the company. <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458531125-deb0a57ae1-ScreenShot2016-03-21at8.50.04AM.png)


* **Lead_Manager**: The lead_manager_code is the code of the lead manager, and the company_code is the code of the working comapny.<Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458534960-2c6d764e3c-ScreenShot2016-03-21at8.50.12AM.png)


* **Senior_Manager**: The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458534973-6548194998-ScreenShot2016-03-21at8.50.21AM.png)

* **Manager**: The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458534988-7fc0af46ce-ScreenShot2016-03-21at8.50.29AM.png)


* **Employee**: The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458535002-d47f63cbb4-ScreenShot2016-03-21at8.50.41AM.png)


**Sample Input:**

Company Table: <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458535049-2a207c44b3-ScreenShot2016-03-21at8.50.52AM.png)


Lead_Manager Table: <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458535073-919107f639-ScreenShot2016-03-21at8.51.03AM.png)

Senior_Manager Table: <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458535111-b1c48335b3-ScreenShot2016-03-21at8.51.15AM.png)

Manager Table: <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458535122-888f4bf340-ScreenShot2016-03-21at8.51.26AM.png)

Employee Table: <Br>
![Q2](https://s3.amazonaws.com/hr-challenge-images/19505/1458535134-878767e0d9-ScreenShot2016-03-21at8.51.52AM.png)

**Sample Output:**
```
C1 Monika 1 2 1 2
C2 Samantha 1 1 2 2
```

**Explanation:**

In company C1, the only lead manager is LM1. There are two senior managers, SM1 and SM2, under LM1. There is one manager, M1, under senior manager SM1. There are two employees, E1 and E2, under manager M1.

In company C2, the only lead manager is LM2. There is one senior manager, SM3, under LM2. There are two managers, M2 and M3, under senior manager SM3. There is one employee, E3, under manager M2, and another employee, E4, under manager, M3.


Solution:
```SQL
SELECT A.Company_Code, A.founder, COUNT(DISTINCT B.lead_manager_code), COUNT(DISTINCT B.senior_manager_code),COUNT(DISTINCT B.manager_code), COUNT(DISTINCT B.employee_code)
FROM Company A
JOIN Employee B
ON A.Company_Code = B.Company_Code
GROUP BY A.Company_Code, A.FOUNDER
ORDER BY A.Company_Code;
```


