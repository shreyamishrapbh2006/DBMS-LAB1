## Experiment --07

01.Compute the number of days remaining in this year.
## Queries:
```sql
SELECT 
    (LAST_DAY(STR_TO_DATE(CONCAT(YEAR(CURDATE()),'-12-01'),'%Y-%m-%d')) 
    - CURDATE()) AS Days_Remaining;
```
## Output:
```sql
+----------------+
| Days_Remaining |
+----------------+
| 309            |
+----------------+
```

02.Find the highest and lowest salaries and the difference between them.
## Queries:
```sql
SELECT 
    MAX(SAL) AS Highest_Salary,
    MIN(SAL) AS Lowest_Salary,
    MAX(SAL) - MIN(SAL) AS Difference
FROM EMP;
```
## Output:
```sql
+----------------+---------------+------------+
| Highest_Salary | Lowest_Salary | Difference |
+----------------+---------------+------------+
| 5000           | 800           | 4200       |
+----------------+---------------+------------+
```

3.List employees whose commission is greater than 25% of their salary.
## Queries:
```sql
SELECT ENAME, SAL, COMM
FROM EMP
WHERE COMM > (0.25 * SAL);
```
## Output:
```sql
+--------+------+------+
| ENAME  | SAL  | COMM |
+--------+------+------+
| ALLEN  | 1600 | 300  |
| TURNER | 1500 | 500  |
+--------+------+------+
```

4.Display salary in dollar format.
## Queries:
```sql
SELECT ENAME, CONCAT('$', SAL) AS Salary_In_Dollar
FROM EMP;
```
## Output:
```sql
+--------+------------------+
| ENAME  | Salary_In_Dollar |
+--------+------------------+
| SMITH  | $800             |
| ALLEN  | $1600            |
| WARD   | $1250            |
+--------+------------------+
```

05.Create a matrix query to display job-wise salary for each department and total salary.
## Queries:
```sql
SELECT 
    JOB,
    SUM(CASE WHEN DEPTNO = 10 THEN SAL ELSE 0 END) AS Dept10,
    SUM(CASE WHEN DEPTNO = 20 THEN SAL ELSE 0 END) AS Dept20,
    SUM(CASE WHEN DEPTNO = 30 THEN SAL ELSE 0 END) AS Dept30,
    SUM(CASE WHEN DEPTNO = 40 THEN SAL ELSE 0 END) AS Dept40,
    SUM(SAL) AS Total_Salary
FROM EMP
GROUP BY JOB;
```
## Output:
```sql
+-----------+--------+--------+--------+--------------+
| JOB       | Dept10 | Dept20 | Dept30 | Total_Salary |
+-----------+--------+--------+--------+--------------+
| MANAGER   | 2450   | 2975   | 2850   | 8275         |
| CLERK     | 1300   | 1900   | 950    | 4150         |
+-----------+--------+--------+--------+--------------+
```

06.Display total employees and employees hired in 1980, 1981, 1982, 1983.
## Queries:
```sql
SELECT 
    COUNT(*) AS Total_Employees,
    SUM(CASE WHEN YEAR(HIREDATE)=1980 THEN 1 ELSE 0 END) AS Hired_1980,
    SUM(CASE WHEN YEAR(HIREDATE)=1981 THEN 1 ELSE 0 END) AS Hired_1981,
    SUM(CASE WHEN YEAR(HIREDATE)=1982 THEN 1 ELSE 0 END) AS Hired_1982,
    SUM(CASE WHEN YEAR(HIREDATE)=1983 THEN 1 ELSE 0 END) AS Hired_1983
FROM EMP;
```
## Output:
```sql
+-----------------+------------+------------+------------+------------+
| Total_Employees | Hired_1980 | Hired_1981 | Hired_1982 | Hired_1983 |
+-----------------+------------+------------+------------+------------+
| 14              | 1          | 10         | 2          | 1          |
+-----------------+------------+------------+------------+------------+
```

07.Query to get the last Sunday of any month.
## Queries:
```sql
SELECT 
    DATE_SUB(LAST_DAY(CURDATE()), 
    INTERVAL (DAYOFWEEK(LAST_DAY(CURDATE()))-1) DAY) 
    AS Last_Sunday;
```
## Output:
```sql
+-------------+
| Last_Sunday |
+-------------+
| 2026-02-22  |
+-------------+
```

08.Display department numbers and total number of employees in each department.
## Queries:
```sql
SELECT DEPTNO, COUNT(*) AS Total_Employees
FROM EMP
GROUP BY DEPTNO;
```
## Output:
```sql
+--------+-----------------+
| DEPTNO | Total_Employees |
+--------+-----------------+
| 10     | 3               |
| 20     | 5               |
| 30     | 6               |
+--------+-----------------+
```

09.Display various jobs and total number of employees within each job group.
## Queries:
```sql
SELECT JOB, COUNT(*) AS Total_Employees
FROM EMP
GROUP BY JOB;
```
## Output:
```sql
+-----------+-----------------+
| JOB       | Total_Employees |
+-----------+-----------------+
| MANAGER   | 3               |
| CLERK     | 4               |
| SALESMAN  | 4               |
| ANALYST   | 2               |
| PRESIDENT | 1               |
+-----------+-----------------+
```

10.Display department numbers and total salary for each department.
## Queries:
```sql
SELECT DEPTNO, SUM(SAL) AS Total_Salary
FROM EMP
GROUP BY DEPTNO;
```
## Output:
```sql
+--------+--------------+
| DEPTNO | Total_Salary |
+--------+--------------+
| 10     | 8750         |
| 20     | 10875        |
| 30     | 9400         |
+--------+--------------+
```
