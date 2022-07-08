## Data Analytics Assessment

---
### Problem1


You would like to compute the scores of all teams after all matches. Points are awarded as follows:

 - A team receives three points if they win a match (i.e., Scored more goals than the opponent team).

 - A team receives one point if they draw a match (i.e., Scored the same number of goals as the opponent team).

 - A team receives no points if they lose a match (i.e., Scored fewer goals than the opponent team).
Write an SQL query that selects the team_id, team_name and num_points of each team in the tournament after all described matches.

Return the result table ordered by num_points in decreasing order. In case of a tie, order the records by team_id in increasing order.


> Table: teams

| Column Name | Type |
| ----------- | ---- |
| id          | int  |
| team_id     | int  |
| team_name   | varchar |

id represents primary key of the table.

team_id is the id of the football team.

Each row of this table represents a single football team.

> Table: matches

| Column Name | Type |
| ----------- | ---- |
| id          | int  |
| match_id    | int  |
| host_team   | int  |
| guest_team  | int  |
| host_goals  | int  |
| guest_goals | int  |

id represents primary key of the table.

match_id is the match happened between two teams.

Each row is a record of a finished match between two different teams. 

Teams host_team and guest_team are represented by their IDs in the Teams table (team_id), and they scored host_goals and guest_goals goals, respectively.

``` The statement result format is in the following example.```

| team_id | team_name | num_points |
| ------- | --------- | ---------- |
| 10      | FC Barcelona | 7       |
| 20      | NewYork FC | 3 |
| 50      | Toronto FC | 3 |
| 30      | Atlanta FC | 1 |
| 40 | Chicago FC | 0 |

