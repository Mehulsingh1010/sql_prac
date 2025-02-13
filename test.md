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
