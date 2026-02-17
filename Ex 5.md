# DBMS Query 5 – 

```sql
-- Query 5 (1)
SELECT COUNT(*) AS TOTAL_EMPLOYEE_COUNT FROM EMPLOYEE;
+----------------------+
| TOTAL_EMPLOYEE_COUNT |
+----------------------+
| 14                   |
+----------------------+

-- Query 5 (2)
SELECT SUM(SAL) AS TOTAL_SAL FROM EMPLOYEE;
+-----------+
| TOTAL_SAL |
+-----------+
| 31368     |
+-----------+

-- Query 5 (3)
SELECT MAX(SAL) AS MAX_SAL FROM EMPLOYEE;
+---------+
| MAX_SAL |
+---------+
| 5500    |
+---------+

-- Query 5 (4)
SELECT MIN(SAL) AS MIN_SAL FROM EMPLOYEE;
+---------+
| MIN_SAL |
+---------+
| 880     |
+---------+

-- Query 5 (5)
SELECT AVG(SAL) AS AVG_SAL FROM EMPLOYEE;
+-----------+
| AVG_SAL   |
+-----------+
| 2240.5714 |
+-----------+

-- Query 5 (6)
SELECT MAX(SAL) AS MAX_CLERK_SAL FROM EMPLOYEE WHERE JOB = 'CLERK';
+---------------+
| MAX_CLERK_SAL |
+---------------+
| 1430          |
+---------------+

-- Query 5 (7)
SELECT MAX(SAL) AS MAX_SAL FROM EMPLOYEE WHERE DEPTNO = 20;
+---------+
| MAX_SAL |
+---------+
| 5500    |
+---------+

-- Query 5 (8)
SELECT MIN(SAL) AS MIN_SALESMAN_SAL FROM EMPLOYEE WHERE JOB = 'SALESMAN';
+------------------+
| MIN_SALESMAN_SAL |
+------------------+
| 1250             |
+------------------+

-- Query 5 (9)
SELECT AVG(SAL) AS AVG_MANAGER_SAL FROM EMPLOYEE WHERE JOB = 'MANAGER';
+-----------------+
| AVG_MANAGER_SAL |
+-----------------+
| 3034.3333       |
+-----------------+

-- Query 5 (10)
SELECT SUM(SAL) AS TOTAL_ANALYST_SAL 
FROM EMPLOYEE 
WHERE JOB = 'ANALYST' AND DEPTNO = 40;
+-------------------+
| TOTAL_ANALYST_SAL |
+-------------------+
| 3300              |
+-------------------+

-- Query 5 (11)
SELECT UCASE(ENAME) AS UPPERCASE_ENAME FROM EMPLOYEE;
+-----------------+
| UPPERCASE_ENAME |
+-----------------+
| SMITH           |
| ALLEN           |
| WARD            |
| JONES           |
| MARTIN          |
| BLAKE           |
| CLARK           |
| SCOTT           |
| KING            |
| TURNER          |
| ADAMS           |
| JAMES           |
| FORD            |
| MILLER          |
+-----------------+

-- Query 5 (12)
SELECT LCASE(ENAME) AS LOWERCASE_ENAME FROM EMPLOYEE;
+-----------------+
| LOWERCASE_ENAME |
+-----------------+
| smith           |
| allen           |
| ward            |
| jones           |
| martin          |
| blake           |
| clark           |
| scott           |
| king            |
| turner          |
| adams           |
| james           |
| ford            |
| miller          |
+-----------------+

-- Query 5 (13)
SELECT CONCAT(
       UCASE(LEFT(ENAME,1)),
       LCASE(SUBSTR(ENAME,2))
) AS PROPER_CASE_NAME
FROM EMPLOYEE;
+------------------+
| PROPER_CASE_NAME |
+------------------+
| Smith            |
| Allen            |
| Ward             |
| Jones            |
| Martin           |
| Blake            |
| Clark            |
| Scott            |
| King             |
| Turner           |
| Adams            |
| James            |
| Ford             |
| Miller           |
+------------------+

-- Query 5 (14)
SELECT LENGTH('SHREYA');
+------------------+
| LENGTH('SHREYA') |
+------------------+
| 6                |
+------------------+

-- Query 5 (15)
SELECT ENAME, LENGTH(ENAME) FROM EMPLOYEE;
+--------+---------------+
| ENAME  | LENGTH(ENAME) |
+--------+---------------+
| SMITH  | 5             |
| ALLEN  | 5             |
| WARD   | 4             |
| JONES  | 5             |
| MARTIN | 6             |
| BLAKE  | 5             |
| CLARK  | 5             |
| SCOTT  | 5             |
| KING   | 4             |
| TURNER | 6             |
| ADAMS  | 5             |
| JAMES  | 5             |
| FORD   | 4             |
| MILLER | 6             |
+--------+---------------+
```
