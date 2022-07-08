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


----
---
---
### Problem2

Write an SQL query that reports the most experienced employees in each project. In case of a tie, report all employees with the maximum number of experience years.

Return the result table in any order.

> Table: project

| Column Name | Type |
| ----------- | ---- |
| project_id  | int |
| employee_id | int |

(project_id, employee_id) is the primary key of this table.

employee_id is a foreign key to Employee table.

Each row of this table indicates that the employee with employee_id is working on the project with project_id.

> Table: Employee

| Column Name | Type |
| ----------- | ---- |
| employee_id | int |
| name | varchar |
| experience_years | int |

employee_id is the primary key of this table.
Each row of this table contains information about one employee.

``` The query result format is in the following example.```

| project_id | employee_id |
| ---------- | ----------- |
| 1 | 1 |
| 1 | 3 |
| 2 | 1 |

**Explanation**: Both employees with id 1 and 3 have the most experience among the employees of the first project. For the second project, the employee with id 1 has the most experience.