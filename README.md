Q.Table world

Q.Show the name and population for France, Germany, Italy	
	SELECT name, population 
	FROM world
	WHERE name IN
	('France', 'Germany', 'Italy')

Q.Give the name and the per capita GDP for those countries with a population of at least 200 million.

	SELECT name, gdp/population 
	FROM world
	WHERE population > 200000000	
	
Q.Show the countries which have a name that includes the word 'United'	
	SELECT name
	FROM world
	WHERE name LIKE '%United%'
	
Q.Show the countries that are big by area or big by population. Show name, population and area.
	SELECT name,population,area
	FROM world
	WHERE (area > 3000000 or population >250000000)	
  
Q.Exclusive OR (XOR). Show the countries that are big by area or big by population but not both. Show name, population and area.

Australia has a big area but a small population, it should be included.
Indonesia has a big population but a small area, it should be included.
China has a big population and big area, it should be excluded.
United Kingdom has a small population and a small area, it should be excluded.

  SELECT name,population,area
  FROM world
  WHERE (area >3000000 XOR population >250000000)
Q.Show the name and population in millions and the GDP in billions for the countries of the continent 'South America'. 
	Use the ROUND function to show the values to two decimal places.
	For South America show population in millions and GDP in billions both to 2 decimal places.	
	
		SELECT name, Round(population/1000000,2), Round(gdp/1000000000,2)
		from world
		where continent ='South America'
Q.Show the name and per-capita GDP for those countries with a GDP of at least one trillion (1000000000000; that is 12 zeros).
 Round this value to the nearest 1000.		
	SELECT name,Round(gdp/population,-3)AS GDP
from world
where gdp>1000000000000    

Q.Show the name and capital where the name and the capital have the same number of characters.
  You can use the LENGTH function to find the number of characters in a string	.
	SELECT name, capital
	  FROM world
		WHERE (LENGTH(name)=LENGTH(capital))
    
Q.Show the name and the capital where the first letters of each match. Don't include countries where the name and the capital are the same word.
You can use the function LEFT to isolate the first character.
You can use '<>' as the NOT EQUALS operator.	
	SELECT name,capital
	FROM world
	where (LEFT(name,1)=LEFT(capital,1) AND (name<>capital))
	
Q.Find the country that has all the vowels and no spaces in its name.
	SELECT name
	FROM world
	WHERE (name LIKE '%a%'
	AND name LIKE '%e%'
	AND name LIKE '%i%'
	AND name LIKE '%o%'
	AND name LIKE '%u%'
	AND name NOT LIKE '% %')
  
  
    
    
