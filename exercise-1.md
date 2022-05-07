1.  Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

SELECT *
FROM CITY
WHERE COUNTRYCODE = 'USA' AND POPULATION > 100000

2. Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

SELECT DISTINCT CITY
FROM STATION
WHERE ID % 2 = 0


3. Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. The query returns , because
total number of records - number of unique city names = 3 - 2 = 1.


SELECT COUNT(CITY) - COUNT(DISTINCT CITY)
FROM STATION


4. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[AEIOU]'

SELECT DISTINCT CITY
FROM STATION
WHERE CITY RLIKE '^[AEIOU].*'


5. Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

SELECT DISTINCT CITY
FROM STATION
WHERE CITY RLIKE '[aeiou]$'

SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '.*[aeiou]$'


6. Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[AEIOU]' AND CITY RLIKE '[AEIOU]$'

SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[AEIOU].*[aeiou]$'

7. Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

SELECT DISTINCT CITY
FROM STATION
WHERE NOT CITY REGEXP '^[AEIOU]'

SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT REGEXP '^[AEIOU].*'

8. Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT REGEXP '[aeiou]$'

9. Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT RLIKE '^[aeiou]'
OR CITY NOT REGEXP '[aeiou]$'


10. Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT REGEXP '^[aeiou]'
AND CITY NOT REGEXP '[aeiou]$'