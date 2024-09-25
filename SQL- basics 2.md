SELECT AVG(grade) AS average_grade
FROM Enrollments;ALTER
![image](https://github.com/user-attachments/assets/d1cf21f6-3972-469c-a183-a9a6efb8d849)

SELECT Students.name, Courses.course_name
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;
![image](https://github.com/user-attachments/assets/4217fbbf-1315-409e-898e-d27ed07ddda9)
![image](https://github.com/user-attachments/assets/45b1e404-1135-43ff-8f24-56f0fd62ccd6)

SELECT grade_level, COUNT(*) AS student_count
FROM Students
GROUP BY grade_level;
![image](https://github.com/user-attachments/assets/f9c62477-2a69-4bb3-86b1-c00c46cea5d8)

SELECT Courses.course_name, MAX(Enrollments.grade) AS max_grade
FROM Enrollments
JOIN Courses ON Enrollments.course_id = Courses.course_id
GROUP BY Courses.course_name;
![image](https://github.com/user-attachments/assets/7aa9c0e0-48c8-4c52-9e73-ce26fa490841)

SELECT AVG(Enrollments.grade) AS average_grade
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
WHERE Students.grade_level = 3;
![image](https://github.com/user-attachments/assets/4775143c-ba31-4af9-a906-76687ee351ec)

SELECT Students.name, Courses.course_name, Courses.credits
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;
![image](https://github.com/user-attachments/assets/616fd108-eb81-4e20-85a8-26f0dea87f1d)
![image](https://github.com/user-attachments/assets/82cb1666-119b-454a-a074-7e4579f8a57c)

SELECT Courses.course_name, AVG(Enrollments.grade) AS average_grade
FROM Enrollments
JOIN Courses ON Enrollments.course_id = Courses.course_id
GROUP BY Courses.course_name
HAVING AVG(Enrollments.grade) > 3.0;
![image](https://github.com/user-attachments/assets/4168ba1c-68a7-40b7-a674-c629c7f4a502)

SELECT DISTINCT Students.name
FROM Students
WHERE Students.student_id NOT IN (
    SELECT Enrollments.student_id
    FROM Enrollments
    WHERE Enrollments.grade = 4.0);
![image](https://github.com/user-attachments/assets/b61236d7-66b8-45e8-a7c6-d0e50676d108)

WITH StudentAverage AS (
    SELECT student_id, AVG(grade) AS avg_grade
    FROM Enrollments
    GROUP BY student_id),
OverallAverage AS (
    SELECT AVG(grade) AS overall_avg
    FROM Enrollments)
SELECT Students.name
FROM StudentAverage
JOIN Students ON StudentAverage.student_id = Students.student_id
WHERE StudentAverage.avg_grade > (SELECT overall_avg FROM OverallAverage);
![image](https://github.com/user-attachments/assets/6bf9b81a-0368-4361-996f-6362c2f63ce3)

SELECT Students.name, COUNT(Enrollments.course_id) AS total_courses, AVG(Enrollments.grade) AS average_grade
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
GROUP BY Students.name;
![image](https://github.com/user-attachments/assets/e3e68d62-a521-4f06-804c-ef024eba3c3d)











