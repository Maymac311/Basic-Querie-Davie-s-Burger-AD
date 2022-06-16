# Basic-Querie-Davie-s-Burger-AD
Writing a basic querie as part of the Codecademy course
The restaurant business has been booming and it is now looking to place a catchy advertisement in the local subway station. Help them dig into their orders table to see if there is anything interesting in there for a funny tagline!

#1. Getting a feel of the 'orders' table
SELECT *
FROM orders
LIMIT 10;

#2. How recent is the data?
SELECT DISTINCT order_date
FROM orders
ORDER BY order_date DESC;

#3. The 'special_instruction' column stores the data where Davie's Burger customers leave a note for the kitcher or the delivery. Limit the results to 20 rows.
SELECT special_instructions
FROM orders
LIMIT 20;

#4. There seem to be a lot of empty values in that column. That is because customers sometimes leave the notes section blank. We will edit the query so that we are only returning the special instructions that are not empty
SELECT special_instructions
FROM orders
WHERE special_instructions IS NOT NULL;

#5. Sorting the instructions in alphabetical order (A-Z)
SELECT special_instructions
FROM orders
WHERE special_instructions IS NOT NULL
ORDER BY special_instructions;

#6. Now we have a good idea of the list. Let's search for special intructions that have the word "sauce"
SELECT special_instructions
FROM orders
WHERE special_instructions LIKE '%sauce%';

#7. Let's search for special instructions that have the word "door"
SELECT special_instructions
FROM orders
WHERE special_instructions LIKE '%door%';

#8. One more time, searching for special instructions that have the word "box"
SELECT special_instructions
FROM orders
WHERE special_instructions LIKE '%box%';

#9. Looks like we have plenty of great tag lines to choose from! But what are their order numbers? Instead of just returning the special instructions, also return their order 'ids'. For more readability, rename 'id' as "#" and 'special_instructions' as notes
SELECT id AS '#', special_instructions AS notes
FROM orders
WHERE special_instructions LIKE '%box%';

