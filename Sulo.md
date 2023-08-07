# Input
SELECT * FROM employee 
WHERE id IN (SELECT employee_id FROM awards );
SELECT * FROM employee 
WHERE id NOT IN (SELECT employee_id FROM awards );
SELECT * FROM employee 
WHERE role = 'Developer' AND salary > 
( SELECT max(salary) FROM employee 
 WHERE role = 'Manager');
 SELECT * FROM employee WHERE role = "Developer" and salary > 
 (SELECT salary From employee
  WHERE role = "Manager" );
SELECT * FROM employee WHERE salary > 
(SELECT AVG(salary) 
 From employee GROUP BY "role");
# output
| id      | name | salary       | role    |
|-----------|-----|-------------|---------------|
| 1    | Augustine Hammond | 10000  | Developer |
| 3    | Cassy Delafoy | 30000 | Developer     |

| id | name              | salary | role       |
|----|-------------------|--------|------------|
| 2  | Perice Mundford   | 10000  | Manager    |
| 4  | Garwood Saffen    | 40000  | Manager    |
| 5  | Faydra Beaves     | 50000  | Developer  |

| id | name              | salary | role       |
|----|-------------------|--------|------------|
| 5  | Faydra Beaves     | 50000  | Developer  |

| id | name              | salary | role       |
|----|-------------------|--------|------------|
| 3  | Cassy Delafoy     | 30000  | Developer  |
| 5  | Faydra Beaves     | 50000  | Developer  |

| id | name              | salary | role       |
|----|-------------------|--------|------------|
| 4  | Garwood Saffen    | 40000  | Manager    |
| 5  | Faydra Beaves     | 50000  | Developer  |
