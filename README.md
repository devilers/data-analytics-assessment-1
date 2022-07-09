## Data Analytics Assessment

Points to remember:

 - Import the data in your database. ( Can use either SQL or CSV to dump the data ).
 - Provide 2-3 lines of your explanation on the approach of your solution.
 - Provide your queries along with the results in a new repository in github ( View the below format ).

In case you don't have a database setup in your machine, you can try [SQL Fiddle](http://sqlfiddle.com/).

 - Copy the sqlfiddle_schema_builder added for every problem folder and paste it in the SQL Fiddle's schema builder (left hand side) and try your solutions
 on your right hand side. ( MySQL 5.6)

#### **Problem Statement**

#### **Explanation (2-3 lines)**

#### **Solution**

**Result Screenshot**


---
### Problem1

**Data**: [click here](https://github.com/29nikhilgarakapati/data-analytics-assessment/tree/main/SQL/Problem1)


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

**Data**: [Click here](https://github.com/29nikhilgarakapati/data-analytics-assessment/tree/main/SQL/Problem2)

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

---
---
---

### Problem3

**Data**: [Click here](https://github.com/29nikhilgarakapati/data-analytics-assessment/tree/main/SQL/Problem3)

Write an SQL query to find the names of all the activities with neither the maximum nor the minimum number of participants.

Each activity in the Activities table is performed by any person in the table Friends.

Return the result table in any order.

> Table: Friends


| Column Name   | Type    |
|-------------- | -------- |
| id            | int     |
| name          | varchar |
| activity      | varchar |

id is the id of the friend and primary key for this table.

name is the name of the friend.

activity is the name of the activity which the friend takes part in.

> Table: Activities

| Column Name   | Type    |
| ------------- | ------- |
| id            | int     |
| name          | varchar | 

id is the primary key for this table.

name is the name of the activity.

```The query result format is in the following example.```

| activity     |
| ------------ |
| Singing      |

**Explanation**:
Eating activity is performed by 3 friends, maximum number of participants, (Jonathan D. , Elvis Q. and Daniel A.)

Horse Riding activity is performed by 1 friend, minimum number of participants, (Bob B.)

Singing is performed by 2 friends (Victor J. and Jade W.)

---
---
---

### Problem4

**Data**: [Click here](https://github.com/29nikhilgarakapati/data-analytics-assessment/tree/main/SQL/Problem4)

A quiet student is the one who took at least one exam and did not score the high or the low score.

Write an SQL query to report the students (student_id, student_name) being quiet in all exams. Do not return the student who has never taken any exam.

Return the result table ordered by student_id.

> Table: student

| Column Name         | Type    |
| ------------------- | ------ |
| student_id          | int     |
| student_name        | varchar |

student_id is the primary key for this table.

student_name is the name of the student.

> Table: Exam

| Column Name   | Type    |
| ------------- | --------|
| exam_id       | int     |
| student_id    | int     |
| score         | int     |

(exam_id, student_id) is the primary key for this table.

Each row of this table indicates that the student with student_id had a score points in the exam with id exam_id.

``` The query result format is in the following example.```


| student_id  | student_name  |
| ------------| --------------|
| 2           | Jade          |

**Explanation**
For exam 1: Student 1 and 3 hold the lowest and high scores respectively.

For exam 2: Student 1 hold both highest and lowest score.

For exam 3 and 4: Studnet 1 and 4 hold the lowest and high scores respectively.
Student 2 and 5 have never got the highest or lowest in any of the exams.

Since student 5 is not taking any exam, he is excluded from the result.

So, we only return the information of Student 2.
