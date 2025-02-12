-- Create and select database
CREATE DATABASE COMPANY_XYZ;  
USE COMPANY_XYZ;  

-- Create Employee table
CREATE TABLE Employee (  
    EMPLOYEE_ID INT NOT NULL PRIMARY KEY AUTO_INCREMENT,  
    FIRST_NAME CHAR(25),  
    LAST_NAME CHAR(25),  
    SALARY INT,  
    JOIN_DATE DATETIME,  
    DEPARTMENT CHAR(25)  
);  

-- Insert data
INSERT INTO Employee (EMPLOYEE_ID, FIRST_NAME, LAST_NAME, SALARY, JOIN_DATE, DEPARTMENT) VALUES  
(101, 'Aarav', 'Sharma', 120000, '2015-03-15 10:00:00', 'Finance'),  
(102, 'Ishita', 'Patel', 85000, '2016-07-20 11:30:00', 'Operations'),  
(103, 'Rohan', 'Verma', 310000, '2017-09-10 09:15:00', 'Finance'),  
(104, 'Neha', 'Kapoor', 520000, '2018-05-25 08:45:00', 'Operations'),  
(105, 'Kunal', 'Mehta', 490000, '2019-02-17 10:20:00', 'Operations'),  
(106, 'Sanya', 'Reddy', 210000, '2020-06-05 12:00:00', 'IT');  

-- Queries  
SELECT * FROM Employee;  
SELECT DISTINCT DEPARTMENT FROM Employee;  

-- Salary-based filters  
SELECT * FROM Employee WHERE SALARY > 200000;  
SELECT * FROM Employee WHERE SALARY BETWEEN 100000 AND 200000;  

-- Department-based queries  
SELECT * FROM Employee WHERE DEPARTMENT = 'Finance' ORDER BY SALARY ASC;  
SELECT MIN(SALARY) FROM Employee WHERE DEPARTMENT = 'Finance';  
SELECT FIRST_NAME, LAST_NAME FROM Employee  
WHERE DEPARTMENT = 'Finance'  
AND SALARY = (SELECT MIN(SALARY) FROM Employee WHERE DEPARTMENT = 'Finance');  

-- Categorizing salary levels  
SELECT EMPLOYEE_ID, FIRST_NAME, DEPARTMENT,  
    CASE  
        WHEN SALARY > 300000 THEN 'High Salary'  
        WHEN SALARY BETWEEN 100000 AND 300000 THEN 'Mid Salary'  
        ELSE 'Low Salary'  
    END AS Salary_Category  
FROM Employee;  

-- Count employees per department  
SELECT DEPARTMENT, COUNT(EMPLOYEE_ID) AS Total_Employees  
FROM Employee GROUP BY DEPARTMENT ORDER BY Total_Employees DESC;  

-- Department with least & most employees  
(SELECT DEPARTMENT, COUNT(*) AS Total_Employees  
 FROM Employee GROUP BY DEPARTMENT ORDER BY Total_Employees ASC LIMIT 1)  
UNION ALL  
(SELECT DEPARTMENT, COUNT(*) AS Total_Employees  
 FROM Employee GROUP BY DEPARTMENT ORDER BY Total_Employees DESC LIMIT 1);  
