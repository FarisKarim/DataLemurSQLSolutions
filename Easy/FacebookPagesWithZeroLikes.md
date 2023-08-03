# Facebook Pages with Zero Likes

## Problem Statement

Assume you're given two tables containing data about Facebook Pages and their respective likes (as in "Like a Facebook Page"). Your task is to write an SQL query to return the IDs of the Facebook pages that have zero likes. The output should be sorted in ascending order based on the page IDs.

## `pages` Table
| page_id | page_name          |
|---------|--------------------|
| 20001   | SQL Solutions      |
| 20045   | Brain Exercises    |
| 20701   | Tips for Data Analysts |

| user_id | page_id | liked_date            |
|---------|---------|-----------------------|
| 111     | 20001   | 04/08/2022 00:00:00   |
| 121     | 20045   | 03/12/2022 00:00:00   |
| 156     | 20001   | 07/25/2022 00:00:00   |


## Solution

```sql
SELECT page_id
FROM pages
WHERE page_id NOT IN (SELECT page_id FROM page_likes)
ORDER BY page_id ASC;
