# MongoDB Practice Questions Based on Business Inspection Dataset

## Easy Questions (1–30)

1. Retrieve all documents in the collection.
2. Retrieve the `business_name` of all businesses.	
3. Retrieve the `business_name` and `certificate_number` of all businesses.
4. Find all businesses where the `result` is "Violation Issued".
5. Find all businesses where the `result` is "No Violation Issued".
6. List all unique values in the `sector` field.
7. Retrieve all documents where the `address.city` is "QUEENS VLG".
8. Retrieve all documents where the `address.zip` is 11428.
9. Retrieve all documents where the `sector` is "Cigarette Retail Dealer - 127".
10. Find the business with the `certificate_number` 5381180.
11. Retrieve the `id` and `date` for all businesses.
12. Find all documents where the `certificate_number` is exactly 9278806.
13. List all businesses whose `address.city` is "NEW YORK".
14. Find all documents where the `address.street` is "214TH ST".
15. Retrieve the `business_name` and `sector` of all businesses inspected after "Feb 15 2015".
16. Find documents where the `business_name` starts with the letter "A".
17. List all documents where the `result` is either "Violation Issued" or "No Violation Issued".
18. Count the total number of businesses in the collection.
19. Retrieve businesses whose `address.zip` code is between 10000 and 12000.
20. Find documents where the `address.number` is greater than 9000.
21. Retrieve all documents where the `address.number` is 1233.
22. List the `business_name` of businesses whose `sector` contains the word "Contractor".
23. Find businesses where the `address.city` is either "RIDGEWOOD" or "NEW YORK".
24. Retrieve the `business_name`, `date`, and `result` for all businesses with a `certificate_number` less than 7000000.
25. Find all documents sorted by `date` in ascending order.
26. List the `id` values of businesses with the `result` "No Violation Issued".
27. Retrieve all documents where the `address.street` is "MENAHAN ST".
28. Find businesses whose `business_name` contains the word "GROCERY".
29. List all businesses where the `sector` is not "Tax Preparers - 891".
30. Retrieve documents sorted by `certificate_number` in descending order.

## Medium Questions (31–50)

31. Find the number of businesses for each unique `result` type.
32. List all businesses along with their `business_name` and `address.city`, sorted by `certificate_number` in ascending order.
33. Find all businesses inspected in "QUEENS VLG" that received a "Violation Issued" result.
34. Count how many businesses belong to the `sector` "Home Improvement Contractor - 100".
35. Find the average `address.number` for businesses in "QUEENS VLG".
36. List distinct `address.city` values where `result` is "Violation Issued".
37. Find the earliest inspection date recorded in the collection.
38. Retrieve the top 3 businesses with the highest `certificate_number`.
39. Count how many businesses have `address.zip` codes greater than 11000.
40. Group businesses by `sector` and count how many businesses belong to each sector.
41. Find businesses where the `address.street` contains the word "ST" and `result` is "No Violation Issued".
42. Update the `result` to "Pending" for all businesses where the `result` is currently "No Violation Issued".
43. Delete all businesses with a `certificate_number` less than 6000000.
44. Find businesses inspected in "Feb 2015" and list their `business_name` and `result`.
45. Find all businesses whose `address.number` is between 8000 and 9500.
46. Retrieve the list of businesses, projecting only `business_name`, `result`, and `address.zip`, sorted by `address.zip`.
47. Find documents where the `address.zip` is either 11385 or 11427.
48. Count how many unique `certificate_number` values exist in the collection.
49. List the businesses where the `business_name` contains "INC" (case insensitive).
50. Find businesses whose `sector` ends with "100".

## Hard Questions (51–60)

51. Group businesses by `address.city` and calculate the average `certificate_number` for each city.
52. Find the top 2 `sectors` with the highest number of "Violation Issued" results.
53. Retrieve the `business_name` of the business with the latest inspection `date`.
54. Group businesses by `sector` and `result`, then count how many businesses fall into each combination.
55. Find the percentage of businesses that received a "Violation Issued" result out of the total businesses.
56. List businesses that have the same `address.zip` but different `result` values.
57. Retrieve businesses whose `address.number` is higher than the average `address.number` of all businesses.
58. For each `address.city`, count how many businesses have a `certificate_number` above 7000000.
59. Find businesses with duplicate `certificate_number` values (if any).
60. Group businesses by the month of the `date` and count how many inspections happened in each month.
