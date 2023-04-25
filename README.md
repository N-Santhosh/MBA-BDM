## MBA-BA
    Santhosh-22121024
    Siddharth-2212127

# EDUCATION INSTITUTE


    
## INTRODUCTION
  This a education institution represents the stakeholders of a college system, including students, faculty, courses, departments, classrooms, staff, alumni, library, fees, and attendance. The college system works together to provide high-quality education to students and prepare them for successful careers.
                                                      Students enroll in courses offered by faculty members, and the courses are organized into departments. Classrooms are managed by staff, and the college has a library containing relevant materials. Fees are collected to cover expenses, and attendance is tracked. Alumni are former students who have graduated from the institution. The college system works together to provide high-quality education to students and prepare them for successful careers.



## ENTITIES:
1.	Student
2.	Faculty
3.	Course
4.	Department
5.	Classroom
6.	Staff
7.	Alumni
8.	Library
9.	Fees
10.	Attendance
11.	College



## ATTRIBUTES:
13.	Student ID: Unique identifier for each student
14.	Student Name: Name of the student
15.	Student Email: Email address of the student
16.	Student Phone: Phone number of the student
17.	Student Address: Address of the student
18.	Student Date of Birth: Date of birth of the student
19.	Student Gender: Gender of the student
20.	Student Nationality: Nationality of the student
21.	Student Course ID: Course ID of the student
22.	Student Department ID: Department ID of the student

23.	Faculty ID: Unique identifier for each faculty member
24.	Faculty Name: Name of the faculty member
25.	Faculty Email: Email address of the faculty member
26.	Faculty Phone: Phone number of the faculty member
27.	Faculty Address: Address of the faculty member
28.	Faculty Department ID: Department ID of the faculty member

29.	Course ID: Unique identifier for each course
30.	Course Name: Name of the course
31.	Course Description: Description of the course
32.	Course Duration: Duration of the course in months
33.	Course Department ID: Department ID of the course

34.	Department ID: Unique identifier for each department
35.	Department Name: Name of the department
36.	Department Head ID: ID of the head of the department

37.	Classroom ID: Unique identifier for each classroom
38.	Classroom Name: Name of the classroom
39.	Classroom Capacity: Capacity of the classroom
40.	Classroom Location: Location of the classroom

41.	Staff ID: Unique identifier for each staff member
42.	Staff Name: Name of the staff member
43.	Staff Email: Email address of the staff member
44.	Staff Phone: Phone number of the staff member
45.	Staff Address: Address of the staff member
46.	Staff Department ID: Department ID of the staff member

47.	Alumni ID: Unique identifier for each alumni
48.	Alumni Name: Name of the alumni
49.	Alumni Email: Email address of the alumni
50.	Alumni Phone: Phone number of the alumni
51.	Alumni Address: Address of the alumni
52.	Alumni Course ID: Course ID of the alumni
53.	Alumni Department ID: Department ID of the alumni

54.	Library ID: Unique identifier for each library
55.	Library Name: Name of the library
56.	Library Location: Location of the library

57.	Fees ID: Unique identifier for each fee payment
58.	Fees Student ID: Student ID of the fee payment
59.	Fees Amount: Amount of the fee payment
60.	Fees Date: Date of the fee payment

61.	Attendance ID: Unique identifier for each attendance record
62.	Attendance Student ID: Student ID of the attendance record
63.	Attendance Course ID: Course ID of the attendance record
64.	Attendance Date: Date of the attendance record

65.	College ID: Unique identifier for the college
66.	College Name: Name of the college
67.	College Address: Address of the college
68.	College Website: Website of the college



## ER DIAGRAM:


![BDM-Cia-2 drawio (3)](https://user-images.githubusercontent.com/78794083/234350687-a5b23caa-7b71-4f39-a4ed-eb895ed7ebad.png)



## CONVERTING ER DIAGRAMS INTO TABL:

|Student_ID| Name          | DOB           | phone no     |Address         | DOB      |Gender    | nationality  |Course Id    | deparment id   |
|----------| ------------- |:-------------:| -------------|---------------:|----------|----------|--------------|-------------|----------------|
|          |               |               |              |                |          |          |              |             |                |
|          |               |               |              |                |          |          |              |             |                |
|          |               |               |              |                |          |          |              |             |                |
|          |               |               |              |                |          |          |              |             |                |
|          |               |               |              |                |          |          |              |             |                |
|          |               |               |              |                |          |          |              |             |                |
## FACULTY ID

|Faculty_ID|faculty Name   |faculty email id| phone no     |Address         | deparment id   |
|----------| ------------- |:-------------: | -------------|---------------:|----------------|
|          |               |                |              |                |                | 
|          |               |                |              |                |                |
|          |               |                |              |                |                |
|          |               |                |              |                |                |
|          |               |                |              |                |                |
|          |               |                |              |                |                |


## Course details


|Course_ID |course Name    |description    | duration     | deparment id   |
|----------| ------------- |:-------------: | -------------|---------------:|
|          |               |                |              |                |                
|          |               |                |              |                |                
|          |               |                |              |                |                
|          |               |                |              |                |                
|          |               |                |              |                |                
|          |               |                |              |                |                

## department details

|deparment id| department name| department Head id|
|----------  | ------------- |:-------------:     |
|            |               |                    |                            
|            |               |                    |                          
|            |               |                    |                            
|            |               |                    |                              
|            |               |                    |                              
|            |               |                    |    


## classroom details

|Classroom_ID |classroom Name |classroom capacity |classroom location |
|-------------|---------------|-------------------|-------------------|
|             |               |                   |                   |  
|             |               |                   |                   |
|             |               |                   |                   | 
|             |               |                   |                   | 
|             |               |                   |                   |
|             |               |                   |                   |  


## staff details

|staff _ID |staff  Name    |staff email     |staff phone   | staff address  | staff department |
|----------| ------------- |:-------------: | -------------|---------------:|------------------|
|          |               |                |              |                |                  |
|          |               |                |              |                |                  |
|          |               |                |              |                |                  |  
|          |               |                |              |                |                  |
|          |               |                |              |                |                  |
|          |               |                |              |                |                  |

## library details

|Libarary id | Library name  | libarary location  |
|----------  | ------------- |:------------------ |
|            |               |                    |                            
|            |               |                    |                          
|            |               |                    |                            
|            |               |                    |                              
|            |               |                    |                              
|            |               |                    |  


## fees details

|fees_ID      |fees student id|   fees amount     |     fees date     |
|-------------|---------------|-------------------|-------------------|
|             |               |                   |                   |  
|             |               |                   |                   |
|             |               |                   |                   | 
|             |               |                   |                   | 
|             |               |                   |                   |
|             |               |                   |                   |


## attendence details

|Attendence_ID |Attendence student id|Attendence course id |Attendence date    |
|-------------|----------------------|---------------------|-------------------|
|             |                      |                     |                   |  
|             |                      |                     |                   |
|             |                      |                     |                   | 
|             |                      |                     |                   | 
|             |                      |                     |                   |
|             |                      |                     |                   |

## college details

|College _ID  |College Name   |College address    |College website    |
|-------------|---------------|-------------------|-------------------|
|             |               |                   |                   |  
|             |               |                   |                   |
|             |               |                   |                   | 
|             |               |                   |                   | 
|             |               |                   |                   |
|             |               |                   |                   |




