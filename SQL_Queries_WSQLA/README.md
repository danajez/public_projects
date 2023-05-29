The course was focused on practical work with databases: how to work, connect and analyze data in databases using the SQL language, obtaining, inserting and updating data, but also analytical queries or practical commands to facilitate work.
---
Main topics of the course:
1. Definition of SQL, what are database systems, data types, creating a table, SQL query and its structure, sorting results, DISTINCT, WHERE conditions, principles of AND and OR, selecty, LIKE, negation.
2. Commands CREATE - creation, DROP - deletion, ALTER - modification, getting data from several tables, joining tables - JOIN, scalar and arithmetic functions, working with NULL values, calculations and related functions, UPPER and LOWER functions, SUBSRT function, CONCAT function.
3. Dates and time functions and formats, column functions, aggregation, combining results.
4. Window functions/OLAP functions, nested queries.
5. Data management, constraints and enforcement, database transaction, atomicity, consistency and locking and logging, isolation, durability, autocommit off, deadlock, explain path, trigger.
---
Here are some of the tasks with the query solutions: 

1. TASK: How do you create EMPLOYEE2 table which is identical with EMPLOYEE table?

  * CREATE TABLE w19dj16.employee2 AS  
  (SELECT * FROM wsqla.employee);


2. TASK: Fill out EMPLOYEE2 table with the data from table EMPLOYEE but don`t include Managers.

  * INSERT INTO w19dj16.employee2  
  SELECT *  
  FROM wsqla.employee  
  WHERE job != 'MANAGER';

3. TASK: Find out which employee in the table EMPLOYEE has the highest salary. (In SELECT use last name and salary).

  * SELECT lastname, salary  
    FROM wsqla.employee  
    WHERE salary = (SELECT max(salary)    
				            FROM wsqla.employee);  
                    
    *With the SubSELECT we filtered the highest salary. With the SELECT we added the name to the highest salary.*          
    ![image](https://github.com/danajez/public_projects/assets/116874735/af13ff6d-2c65-4203-8ad9-3e26ed3ed7b9)  

4. TASK: Delete all employees, which have 'e' as a second letter in their lastname from table EMPLOYEE2.

  * DELETE  
    FROM w19dj16.employee2  
    WHERE lastname LIKE '_E%';
    
5. TASK: Find out which department has the highest average salary in table Employee.

  * SELECT workdept, avg(salary) AS avg_salary  
    FROM wsqla.employee  
    GROUP BY workdept  
    HAVING avg(salary) =
    * (SELECT max(avg_salary)  
    FROM  
      * (SELECT workdept, avg(salary)AS avg_salary  
								FROM wsqla.employee
								GROUP BY workdept) AS avg_sal_dept);
    
    *With the SubSELECT we filtered the highest average salary. With the SELECT we added the department to the highest average salary.*
    ![image](https://github.com/danajez/public_projects/assets/116874735/d3acf4b3-4d44-43d1-90af-b6c8a8e65c71)

6. TASK: Find out the count of activities for every department. Order descending by count of activities. Use tables EMP_ACT, EMPLOYEE. Number of activity is in column ACTNO.

  * SELECT workdept, COUNT(actno)  
    FROM wsqla.employee e  
    RIGHT JOIN wsqla.emp_act ea  
    ON e.empno = ea.empno  
    GROUP BY workdept
    ORDER BY count(actno) DESC
    
7. TASK: Show names and salaries for non-managers from department D21. In first line will be the original salary, in second row will be salary after 10% increase. There will be only 1 Salary column.

  * SELECT lastname, firstnme, 'before_increase' AS when, salary  
    FROM wsqla.employee
    WHERE 
	  workdept = 'D21'  
	  AND job != 'MANAGER'  
    UNION ALL  
    SELECT lastname, firstnme, 'after_increase' AS when, salary*1.01  
    FROM wsqla.employee  
    WHERE   
	  workdept = 'D21'  
	  AND job != 'MANAGER'  
    ORDER BY lastname;  
  
    ![image](https://github.com/danajez/public_projects/assets/116874735/07a54f49-b236-4e68-9921-9c796da048b5)
    
8. TASK: Create a list with columns "wordkept, empno, salary" of every employee in department A00. On the last line sum all salaries you see in the view.

  * SELECT workdept, empno, salary  
    FROM wsqla.employee  
    WHERE workdept = 'A00'  
    UNION ALL  
    SELECT workdept, 'Total_for_dep' , SUM(salary)  
    FROM wsqla.employee  
    WHERE workdept = 'A00'  
    GROUP BY workdept;  
    
    ![image](https://github.com/danajez/public_projects/assets/116874735/689790a5-2c2e-4866-899c-3292f0a7073d)

