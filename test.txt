






Q3

SELECT * 
FROM Worker 
WHERE FIRST_NAME NOT IN ('Vipul', 'Satish');
![image](https://github.com/user-attachments/assets/4cb22ebf-8631-498d-bc4e-c35ca8835cbd)




Q4:
SELECT * 
FROM Worker 
WHERE FIRST_NAME LIKE '_____h';  -- 5 underscores + h = 6 characters

![image](https://github.com/user-attachments/assets/037f2cb5-be94-411e-858d-842dc49901bc)




Q5:

SELECT COUNT(*) 
FROM Worker 
WHERE DEPARTMENT = 'Admin';

![image](https://github.com/user-attachments/assets/c5937fcd-6cd6-4e8f-b6cf-7887c82f83cc)

Q6:

SELECT FIRST_NAME, LAST_NAME, SALARY 
FROM Worker 
WHERE SALARY BETWEEN 50000 AND 100000;


![image](https://github.com/user-attachments/assets/5f32812a-4a3d-4a0d-bf38-29d99185606b)


Q7:

SELECT DEPARTMENT, COUNT(*) as worker_count
FROM Worker
GROUP BY DEPARTMENT
ORDER BY worker_count DESC;

![image](https://github.com/user-attachments/assets/68848d8f-b98f-4634-91a5-3c3087af3912)


Q8:
SELECT * FROM (
    SELECT DISTINCT SALARY 
    FROM Worker 
    ORDER BY SALARY DESC
) 
WHERE ROWNUM = 5;

![image](https://github.com/user-attachments/assets/62bdcfd9-dca5-4f85-ab0a-00dc5b670b1e)

Q9:

![image](https://github.com/user-attachments/assets/5f875bdf-16bf-4228-82b9-72571e2ad3c0)

Q10:
SELECT DEPARTMENT, COUNT(*) as emp_count
FROM Worker
GROUP BY DEPARTMENT
HAVING COUNT(*) < 3;
![image](https://github.com/user-attachments/assets/d8abb141-701a-41de-b393-33dbdeb41267)


