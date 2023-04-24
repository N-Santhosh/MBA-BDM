Entities:
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


Attributes:
1.	Student: StudentID, Name, Date of Birth, Email, Phone Number, Address, Gender, Nationality, Admission Date, Degree Program, CollegeID
2.	Faculty: FacultyID, Name, Date of Birth, Email, Phone Number, Address, Gender, Nationality, Department, CollegeID
3.	Course: CourseID, Name, Credits, Department, Prerequisites, Faculty, CollegeID
4.	Department: DepartmentID, Name, HOD, Location, CollegeID
5.	Classroom: RoomID, Capacity, Type, Location, CollegeID
6.	Staff: StaffID, Name, Date of Birth, Email, Phone Number, Address, Gender, Nationality, Department, Designation, CollegeID
7.	Alumni: AlumniID, Name, Date of Birth, Email, Phone Number, Address, Gender, Nationality, Graduation Year, Degree Program, CollegeID
8.	Library: BookID, Title, Author, Publisher, Publication Year, Availability, CollegeID
9.	Fees: FeeID, StudentID, Fee Type, Amount, Date, CollegeID
10.	Attendance: AttendanceID, StudentID, CourseID, Date, Status, CollegeID
11.	College: CollegeID, Name, Address, Phone Number, Email, Website

