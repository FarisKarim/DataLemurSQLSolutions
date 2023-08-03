## Data Science Job Candidates

### Problem Statement

You have a table of candidates and their skills. Your task is to find the candidates best suited for an open Data Science job. Specifically, you want to identify candidates who are proficient in Python, Tableau, and PostgreSQL.

| candidate_id | skill       |
|--------------|-------------|
| 123          | Python      |
| 123          | Tableau     |
| 123          | PostgreSQL  |
| 234          | R           |
| 234          | PowerBI     |
| 234          | SQL Server  |
| 345          | Python      |
| 345          | Tableau     |

## Example Output

| candidate_id |
|--------------|
| 123          |



### Solution

```sql
SELECT candidate_id
FROM candidates
WHERE skill IN ('Python', 'Tableau', 'PostgreSQL')
GROUP BY candidate_id
HAVING COUNT(DISTINCT skill) = 3
ORDER BY candidate_id ASC;






