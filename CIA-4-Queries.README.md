## MBA-BA
    Santhosh-22121024
    Siddharth-2212127

# EDUCATION INSTITUTE

## INTRODUCTION
This code is a SQL script that creates several database tables to represent a university system. The tables created include Faculty, FacultyAddress, Department, Course, Student, Student_Address, Staff, StaffAddress, Phonenumber, Email, and Fees. These tables are designed to store information about various entities in the university, such as faculty, staff, students, courses, and their contact information. The script also defines relationships between the tables using foreign keys to enforce referential integrity. The purpose of this code is to provide a framework for storing and managing data related to the university system in a structured and organized manner.

## PROBLEM STATEMENTS

**1) Retrieve the total number of students enrolled in each course.**

**QUERY:**

SELECT CourseName, COUNT(*) as TotalStudents 
FROM Student 
JOIN Course ON student.courseID = course.CourseID 
GROUP BY CourseName;

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/81821fc5-55ec-497c-97de-8b4cd013306f)

----------------------------------------

**2) The institute wants to analyze the geographic distribution of its students and identify the cities from which the highest number of students come from. Write a query to retrieve the list of cities along with the count of students from each city.**

**QUERY:**

SELECT city, COUNT(*) as TotalStudents 
FROM Student_Address 
GROUP BY city;
   
**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/2636c56e-77d5-483f-a851-a91a35ab4b71)

----------------------------------------

**3)Retrieve the list of staff members and the number of students they have mentored.**

**QUERY:**

SELECT Staff.StaffName, COUNT(Student.student_id) as MentoredStudents
FROM Staff
LEFT JOIN Department ON Staff.DepartmentID = Department.DepartmentID
LEFT JOIN Course ON Department.DepartmentID = Course.DepartmentID
LEFT JOIN Student ON Course.CourseID = Student.courseID
GROUP BY Staff.StaffName;

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/69fe3d78-dc27-42f4-aa90-26c0ceab0071)

----------------------------------------

**4)Retrieve the CourseName, CourseDuration and the number of students enrolled.**

**QUERY:**

SELECT CourseName, CourseDuration, COUNT(*) AS NumStudents
FROM Student
JOIN Course ON Student.CourseID = Course.CourseID
GROUP BY CourseName, CourseDuration;

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/0a67e69d-b931-4b18-a68e-b365044fd7cf)

----------------------------------------

**5)Show the number of students from each department by gender.**

**QUERY:**

SELECT DepartmentName,
       (SELECT COUNT(*) FROM Student WHERE Department.DepartmentID = Student.departmentID AND student_gender = 'male') AS MaleStudents,
       (SELECT COUNT(*) FROM Student WHERE Department.DepartmentID = Student.departmentID AND student_gender = 'female') AS FemaleStudents
FROM Department;

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/05f99759-faba-490e-b97c-3e6efa3b4e65)

----------------------------------------

**6)Show the number of courses offered by each department:**

**QUERY:**

SELECT DepartmentName, COUNT(*) AS CourseCount
FROM Course
JOIN Department ON Course.DepartmentID = Department.DepartmentID
GROUP BY DepartmentName;

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/ff02a80d-e95c-4a91-8df6-5d893266a233)

----------------------------------------

**7)Retrive the list of number of alumni by department**

**QUERY:**

SELECT DepartmentName, COUNT(*) as NumAlumni
FROM Alumni
INNER JOIN Department ON Alumni.DepartmentID = Department.DepartmentID
GROUP BY DepartmentName;

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/f580be26-045c-4a79-939a-90223272bde3)

----------------------------------------

**8)Show the Total fees earned by each department.**

**QUERY:**

SELECT d.DepartmentName, SUM(f.Amount) AS TotalFees
FROM Department d
JOIN Student s ON s.DepartmentID = d.DepartmentID
JOIN Fees f ON f.student_id = s.student_id
GROUP BY d.DepartmentName;

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/1381d48a-e841-4e99-ad2c-60f95b75b05e)

----------------------------------------

**9)Retrieve the count of students born in each year for generating a graph showing the distribution of students' birth year.**

**QUERY:**

SELECT YEAR(student_date_of_birth) AS Year, COUNT(*) AS StudentCount
FROM Student
GROUP BY YEAR
ORDER BY YEAR;

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/be62d4cc-f2ef-439e-bc94-201968313ac6)

----------------------------------------

**10)To retrieve the classroom names and their respective capacities**

**QUERY:**

SELECT ClassroomName, ClassroomCapacity FROM Classroom

**GRAPH:**

![image](https://github.com/N-Santhosh/MBA-BDM-CIA/assets/78794083/ec85d5f9-3a08-4689-a08e-725270fe0af1)

----------------------------------------



