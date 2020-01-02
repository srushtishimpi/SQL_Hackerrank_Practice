# SQL Practice Problems Hackerrank

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


