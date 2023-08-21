### Microsoft Teams Power Users

Given a table named messages from Microsoft Teams, this README provides details to identify the top 2 Power Users who sent the highest number of messages in August 2022.

Assumption:
No two users have sent the same number of messages in August 2022.

| Column Name  | Type      |
|--------------|-----------|
| message_id   | integer   |
| sender_id    | integer   |
| receiver_id  | integer   |
| content      | varchar   |
| sent_date    | datetime  |

### Example Input:

| sender_id | message_count |
|-----------|---------------|
| 3601      | 2             |
| 4500      | 1             |


### Solution:

```sql 
SELECT sender_id, COUNT(*) as count_messages FROM messages 
WHERE EXTRACT(MONTH FROM sent_date) = 8 AND EXTRACT(YEAR FROM sent_date) = 2022
GROUP BY sender_id
ORDER BY count_messages DESC
LIMIT 2;
