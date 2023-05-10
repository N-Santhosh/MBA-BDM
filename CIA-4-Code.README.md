## CODE


CREATE DATABASE `Education-Institute`;
USE `Education-Institute`;



-- Create Faculty Table
CREATE TABLE Faculty (
  FacultyID INT PRIMARY KEY,
  FacultyName VARCHAR(50) NOT NULL,
  DepartmentID INT NOT NULL,
  FOREIGN KEY (DepartmentID) REFERENCES Department(DepartmentID)
);

INSERT INTO Faculty (FacultyID, FacultyName, DepartmentID) VALUES
(1, 'Dr. Ravi Kumar', 1101),
(2, 'Prof. Sneha Sharma', 1102),
(3, 'Dr. Sameer Desai', 1101),
(4, 'Prof. Radha Patel', 1103),
(5, 'Dr. Ajay Gupta', 1103),
(6, 'Prof. Meera Shah', 1103),
(7, 'Dr. Anil Patel', 1101),
(8, 'Prof. Smita Mishra', 1102),
(9, 'Dr. Vikas Kumar', 1102),
(10, 'Prof. Priya Choudhary', 1103);

CREATE TABLE FacultyAddress (
  FacultyID INT PRIMARY KEY,
  door_no varchar (50),
  street VARCHAR(100),
  city VARCHAR(100),
  state VARCHAR(100),
  PinCode INT
);

INSERT INTO FacultyAddress (FacultyID, door_no, street, city, state, PinCode) VALUES
(1, '233', 'Main St', 'Mumbai', 'Maharashtra', 732768),
(2, '44/2', 'Lalbagh Rd', 'Bengaluru', 'Karnataka', 560027),
(3, '15', 'Park St', 'Kolkata', 'West Bengal', 700016),
(4, '7A/23', 'Pusa Rd', 'New Delhi', 'Delhi', 110005),
(5, '32', 'Model Town', 'Ludhiana', 'Punjab', 141002),
(6, '11', 'Gandhi Rd', 'Chennai', 'Tamil Nadu', 600006),
(7, '2/41', 'Rajaji Nagar', 'Bengaluru', 'Karnataka', 560010),
(8, '24/1', 'Shivaji Rd', 'Pune', 'Maharashtra', 411005),
(9, '8', 'Shalimar Bagh', 'New Delhi', 'Delhi', 110088),
(10, '17', 'MG Rd', 'Ernakulam', 'Kerala', 682011); 




-- Create Department Table
CREATE TABLE Department (
  DepartmentID INT PRIMARY KEY,
  DepartmentName VARCHAR(50) NOT NULL,
  HeadID INT NOT NULL,
  FOREIGN KEY (HeadID) REFERENCES Faculty(FacultyID)
);

INSERT INTO Department (DepartmentID, DepartmentName, HeadID) VALUES
(1101, 'Department of Management', 1),
(1102, 'Department of Computer Science', 2),
(1103, 'Department of Law', 3);




-- Create Course Table
CREATE TABLE Course (
  CourseID INT PRIMARY KEY,
  CourseName VARCHAR(50) NOT NULL,
  CourseDescription VARCHAR(100) NOT NULL,
  CourseDuration INT NOT NULL,
  DepartmentID INT NOT NULL,
  FOREIGN KEY (DepartmentID) REFERENCES Department(DepartmentID)
);

INSERT INTO Course (CourseID, CourseName, CourseDescription, CourseDuration, DepartmentID) VALUES
(101, 'MBA', 'Master of Business Administration', 2, 1101),
(102, 'MCA', 'Master of Computer Applications', 2, 1102),
(103, 'LLB', 'Bachelor of Laws', 5, 1103),
(104, 'BCOM', 'Bachelor of Commerce', 3, 1101),
(105, 'BBA', 'Bachelor of Business Administration', 3, 1101);




--CREATE TABLE Student (
  student_id INT PRIMARY KEY,
  student_name VARCHAR(255) NOT NULL,
  student_date_of_birth DATE NOT NULL,
  student_gender ENUM('Male', 'Female', 'Other') NOT NULL,
  student_nationality VARCHAR(50) NOT NULL,
  courseID INT NOT NULL,
  departmentID INT NOT NULL,
  FOREIGN KEY (CourseID) REFERENCES Course(CourseID),
  FOREIGN KEY (DepartmentID) REFERENCES Department(DepartmentID)
);		
											
INSERT INTO Student (student_id, student_name, student_date_of_birth, student_gender, student_nationality, courseID, departmentID) VALUES
(1001, 'Aryan Sharma', '2000-01-01', 'Male', 'Indian', 101, 1101),
(1002, 'Neha Singh', '2001-02-02', 'Female', 'Indian', 102, 1102),
(1003, 'Rahul Desai', '2002-03-03', 'Male', 'Indian', 101, 1103),
(1004, 'Priya Patel', '2001-04-04', 'Female', 'Indian', 102, 1102),
(1005, 'Karan Gupta', '2000-05-05', 'Male', 'Indian', 103, 1101),
(1006, 'Anjali Shah', '1999-06-06', 'Female', 'Indian', 104, 1102),
(1007, 'Amit Patel', '1997-07-07', 'Male', 'Indian', 101, 1101),
(1008, 'Divya Mishra', '1999-08-08', 'Female', 'Indian', 102, 1103),
(1009, 'Rohan Kumar','1998-09-09', 'Male', 'Indian', 104, 1103),
(1010, 'Sonia Choudhary', '2000-10-10', 'Female', 'Indian', 105, 1101),
(1011, 'Alok Tiwari', '2001-01-01', 'Male', 'Indian', 103, 1103),
(1012, 'Pooja Sharma', '2002-02-02', 'Female', 'Indian', 102, 1102),
(1013, 'Rohit Verma', '2003-03-03', 'Male', 'Indian', 101, 1101),
(1014, 'Shreya Singh', '1999-04-04', 'Female', 'Indian', 103, 1103),
(1015, 'Ankit Sharma', '1998-05-05', 'Male', 'Indian', 102, 1102),
(1016, 'Nidhi Gupta', '1998-06-06', 'Female', 'Indian', 104, 1101),
(1017, 'Vikas Patel', '1999-07-07', 'Male', 'Indian', 102, 1102),
(1018, 'Ritu Sharma', '2002-08-08', 'Female', 'Indian', 103, 1103),
(1019, 'Sahil Gupta', '2001-09-09', 'Male', 'Indian', 101, 1101),
(1020, 'Monika Singh', '2000-10-10', 'Female', 'Indian', 103, 1103),
(1021, 'Rajesh Kumar', '2000-11-12', 'Male', 'Indian', 101, 1101),
(1022, 'Manisha Sharma', '2001-12-13', 'Female', 'Indian', 102, 1102),
(1023, 'Gaurav Singh', '2002-11-14', 'Male', 'Indian', 103, 1103),
(1024, 'Neha Gupta', '2003-12-15', 'Female', 'Indian', 101, 1101),
(1025, 'Sachin Patel', '2002-11-16', 'Male', 'Indian', 102, 1102),
(1026, 'Swati Mishra', '2001-12-17', 'Female', 'Indian', 104, 1103),
(1027, 'Rajat Verma', '2000-11-18', 'Male', 'Indian', 101, 1101),
(1028, 'Anjali Singh', '2000-12-19', 'Female', 'Indian', 102, 1102),
(1029, 'Aditya Sharma','2001-11-20', 'Male', 'Indian', 104, 1103),
(1030, 'Aarti Choudhary', '2002-12-21', 'Female', 'Indian', 105, 1101),
(1031, 'Alok Gupta', '2001-11-22', 'Male', 'Indian', 103, 1103),
(1032, 'Kriti Sharma', '2002-12-23', 'Female', 'Indian', 102, 1102),
(1033, 'Avinash Verma', '2003-11-24', 'Male', 'Indian', 101, 1101),
(1034, 'Sakshi Singh', '2001-12-25', 'Female', 'Indian', 103, 1103),
(1035, 'Gaurav Sharma', '2001-11-26', 'Male', 'Indian', 102, 1102),
(1036, 'Jyoti Gupta', '2002-12-27', 'Female', 'Indian', 104, 1101),
(1037, 'Alok Patel', '2002-11-28', 'Male', 'Indian', 102, 1102),
(1038, 'Anshika Sharma', '2001-12-29', 'Female', 'Indian', 103, 1103),
(1039, 'Varun Gupta', '2002-11-30', 'Male', 'Indian', 101, 1101),
(1040, 'Manish Singh', '2000-12-01', 'Female', 'Indian', 103, 1103),
(1041, 'Vivek Kumar', '2000-11-02', 'Male', 'Indian', 101, 1101),
(1042, 'Aarti Sharma', '2001-12-03', 'Female', 'Indian', 102, 1102),
(1043, 'Ankit Singh', '2002-11-04', 'Male', 'Indian', 103, 1103),
(1044, 'Nisha Gupta', '2000-12-10', 'Female', 'African',102,1102),
(1045, 'Aakash Choudhary', '2001-01-12', 'Male', 'Indian', 103, 1103),
(1046, 'Priyanka Singh', '2002-02-11', 'Female', 'Indian', 101, 1102),
(1047, 'Aditya Sharma', '2001-03-10', 'Male', 'Indian', 104, 1101),
(1048, 'Pooja Mishra', '2002-04-09', 'Female', 'Indian', 105, 1103),
(1049, 'Rahul Kumar', '2003-05-08', 'Male', 'Indian', 102, 1102),
(1050, 'Anjali Gupta', '2000-06-07', 'Female', 'Indian', 101, 1101),
(1051, 'Saurabh Patel', '2001-07-06', 'Male', 'Indian', 103, 1102),
(1052, 'Aarti Sharma', '2002-08-05', 'Female', 'Indian', 104, 1103),
(1053, 'Rajat Verma', '2001-09-04', 'Male', 'Indian', 105, 1101),
(1054, 'Nisha Singh', '2000-10-03', 'Female', 'Indian', 101, 1103),
(1055, 'Ankit Tiwari', '2001-01-02', 'Male', 'Indian', 102, 1102),
(1056, 'Swati Sharma', '2002-02-03', 'Female', 'Indian', 103, 1101),
(1057, 'Siddharth Patel', '2002-03-04', 'Male', 'Indian', 104, 1103),
(1058, 'Komal Gupta', '2001-04-05', 'Female', 'Indian', 105, 1101),
(1059, 'Harsh Verma', '2003-05-06', 'Male', 'Indian', 101, 1102),
(1060, 'Tanvi Singh', '2002-06-07', 'Female', 'Indian', 102, 1103),
(1061, 'Akash Kumar', '2002-07-08', 'Male', 'Indian', 103, 1101),
(1062, 'Aditi Choudhary', '2000-08-09', 'Female', 'Indian', 104, 1102),
(1063, 'Kunal Sharma', '2001-09-10', 'Male', 'Indian', 105, 1103),
(1064, 'Surbhi Patel', '2000-10-11', 'Female', 'Indian', 101, 1101),
(1065, 'Rajiv Gupta', '2001-01-12', 'Male', 'Indian', 104, 1102);

CREATE TABLE Student_Address (
  student_id INT NOT NULL,
  door_no VARCHAR(50),
  street VARCHAR(100),
  city VARCHAR(100),
  state VARCHAR(100),
  pin_code INT,
  PRIMARY KEY (student_id)
);

INSERT INTO Student_Address (student_id, door_no, street, city, state, pin_code)
VALUES 
  (1001, '123', 'Main St', 'Mumbai', 'Maharashtra', 400001),
  (1002, '456', '2nd Ave', 'Delhi', 'Delhi', 110001),
  (1003, '789', '3rd St', 'Chennai', 'Tamil Nadu', 600001),
  (1004, '101', '4th Ave', 'Kolkata', 'West Bengal', 700001),
  (1005, '202', '5th St', 'Bengaluru', 'Karnataka', 560001),
  (1006, '303', '6th Ave', 'Hyderabad', 'Telangana', 500001),
  (1007, '404', '7th St', 'Pune', 'Maharashtra', 411001),
  (1008, '505', '8th Ave', 'Jaipur', 'Rajasthan', 302001),
  (1009, '606', '9th St', 'Lucknow', 'Uttar Pradesh', 226001),
  (1010, '707', '10th Ave', 'Ahmedabad', 'Gujarat', 380001),
  (1011, '808', '11th St', 'Kochi', 'Kerala', 682001),
  (1012, '909', '12th Ave', 'Bhopal', 'Madhya Pradesh', 462001),
  (1013, '111', '13th St', 'Nagpur', 'Maharashtra', 440001),
  (1014, '222', '14th Ave', 'Indore', 'Madhya Pradesh', 452001),
  (1015, '333', '15th St', 'Visakhapatnam', 'Andhra Pradesh', 530001),
  (1016, '444', '16th Ave', 'Chandigarh', 'Chandigarh', 160001),
  (1017, '555', '17th St', 'Bhubaneswar', 'Odisha', 751001),
  (1018, '666', '18th Ave', 'Patna', 'Bihar', 800001),
  (1019, '777', '19th St', 'Raipur', 'Chhattisgarh', 492001),
  (1020, '888', '20th Ave', 'Guwahati', 'Assam', 781001),
  (1021, '111', '1st St', 'Lucknow', 'Uttar Pradesh', 226001),
  (1022, '222', '2nd Ave', 'Indore', 'Madhya Pradesh', 452001),
  (1023, '333', '3rd St', 'Bhubaneswar', 'Odisha', 751001),
  (1024, '444', '4th Ave', 'Kochi', 'Kerala', 682001),
  (1025, '555', '5th St', 'Patna', 'Bihar', 800001),
  (1026, '666', '6th Ave', 'Visakhapatnam', 'Andhra Pradesh', 530001),
  (1027, '777', '7th St', 'Hyderabad', 'Telangana', 500001),
  (1028, '888', '8th Ave', 'Delhi', 'Delhi', 110001),
  (1029, '999', '9th St', 'Chandigarh', 'Chandigarh', 160001),
  (1030, '1010', '10th Ave', 'Bhopal', 'Madhya Pradesh', 462001),
  (1031, '1111', '11th St', 'Ahmedabad', 'Gujarat', 380001),
  (1032, '1212', '12th Ave', 'Mumbai', 'Maharashtra', 400001),
  (1033, '1313', '13th St', 'Jaipur', 'Rajasthan', 302001),
  (1034, '1414', '14th Ave', 'Bengaluru', 'Karnataka', 560001),
  (1035, '1515', '15th St', 'Kolkata', 'West Bengal', 700001),
  (1036, '1616', '16th Ave', 'Chennai', 'Tamil Nadu', 600001),
  (1037, '1717', '17th St', 'Pune', 'Maharashtra', 411001),
  (1038, '1818', '18th Ave', 'Guwahati', 'Assam', 781001),
  (1039, '1919', '19th St', 'Raipur', 'Chhattisgarh', 492001),
  (1040, '2020', '20th Ave', 'Nagpur', 'Maharashtra', 440001),
  (1041, '2121', '21st St', 'Lucknow', 'Uttar Pradesh', 226001),
  (1042, '2222', '22nd Ave', 'Indore', 'Madhya Pradesh', 452001),
  (1043, '2323', '23rd St', 'Bhubaneswar', 'Odisha', 751001),
  (1044, '2424', '24th Ave', 'Kochi', 'Kerala', 682001),
  (1045, '2525', '25th St', 'Patna', 'Bihar', 800001),
  (1046, '131', '23rd St', 'Bhubaneswar', 'Odisha', 751001),
  (1047, '242', '24th Ave', 'Pune', 'Maharashtra', 411001),
  (1048, '353', '25th St', 'Bengaluru', 'Karnataka', 560001),
  (1049, '464', '26th Ave', 'Delhi', 'Delhi', 110001),
  (1050, '575', '27th St', 'Raipur', 'Chhattisgarh', 492001),
  (1051, '686', '28th Ave', 'Kolkata', 'West Bengal', 700001),
  (1052, '797', '29th St', 'Nagpur', 'Maharashtra', 440001),
  (1053, '808', '30th Ave', 'Guwahati', 'Assam', 781001),
  (1054, '919', '31st St', 'Jaipur', 'Rajasthan', 302001),
  (1055, '303', '32nd Ave', 'Visakhapatnam', 'Andhra Pradesh', 530001),
  (1056, '414', '33rd St', 'Chennai', 'Tamil Nadu', 600001),
  (1057, '525', '34th Ave', 'Hyderabad', 'Telangana', 500001),
  (1058, '636', '35th St', 'Lucknow', 'Uttar Pradesh', 226001),
  (1059, '747', '36th Ave', 'Chandigarh', 'Chandigarh', 160001),
  (1060, '858', '37th St', 'Kochi', 'Kerala', 682001),
  (1061, '969', '38th Ave', 'Bhopal', 'Madhya Pradesh', 462001),
  (1062, '1010', '39th St', 'Ahmedabad', 'Gujarat', 380001),
  (1063, '1121', '40th Ave', 'Indore', 'Madhya Pradesh', 452001),
  (1064, '1232', '41st St', 'Patna', 'Bihar', 800001),
  (1065, '1343', '42nd Ave', 'Chennai', 'Tamil Nadu', 600001);





-- Create Classroom Table
CREATE TABLE Classroom (
  ClassroomID INT PRIMARY KEY,
  ClassroomName VARCHAR(50) NOT NULL,
  ClassroomCapacity INT NOT NULL,
  ClassroomLocation VARCHAR(100) NOT NULL
);

INSERT INTO Classroom (ClassroomID, ClassroomName, ClassroomCapacity, ClassroomLocation) VALUES
(1, 'MBA Classroom', 30, 'Block A, Room 101'),
(2, 'MCA Classroom', 40, 'Block B, Room 202'),
(3, 'LLB Classroom', 25, 'Block C, Room 303'),
(4, 'BCom Classroom', 35, 'Block A, Room 404'),
(5, 'BBA Classroom', 20, 'Block A, Room 505');




-- Create Staff Table
CREATE TABLE Staff (
  StaffID INT PRIMARY KEY,
  StaffName VARCHAR(50) NOT NULL,
  DepartmentID INT NOT NULL,
  FOREIGN KEY (DepartmentID) REFERENCES Department(DepartmentID)
);

INSERT INTO Staff (StaffID, StaffName, DepartmentID) VALUES
(211, 'Rajesh Kumar', 1101),
(212, 'Shilpa Gupta', 1102),
(213, 'Amit Singh', 1101),
(214, 'Sarika Sharma', 1103),
(215, 'Sanjay Patel', 1102);

CREATE TABLE StaffAddress (
StaffID INT NOT NULL PRIMARY KEY,
door_no VARCHAR(10),
street VARCHAR(50) NOT NULL,
city VARCHAR(50) NOT NULL,
state VARCHAR(50) NOT NULL,
PinCode INT NOT NULL,
FOREIGN KEY (StaffID) REFERENCES Staff(StaffID)
);

INSERT INTO StaffAddress ( StaffID, door_no, street, city, state, PinCode) VALUES
(211, '123', 'Main St', 'Mumbai', 'Maharashtra', 400001),
(212, '456', 'Elm St', 'Delhi', 'Delhi', 110001),
(213, '789', 'Oak St', 'Ahmedabad', 'Gujarat', 380001),
(214, '987', 'Maple St', 'Bangalore', 'Karnataka', 560001),
(215, '654', 'Pine St', 'Chennai', 'Tamil Nadu', 600001);




-- Create Alumni Table
CREATE TABLE Alumni (
  AlumniID INT PRIMARY KEY,
  AlumniName VARCHAR(50) NOT NULL,
  CourseID INT NOT NULL,
  DepartmentID INT NOT NULL,
  FOREIGN KEY (CourseID) REFERENCES Course(CourseID),
  FOREIGN KEY (DepartmentID) REFERENCES Department(DepartmentID)
);

INSERT INTO Alumni (AlumniID, AlumniName, CourseID, DepartmentID) VALUES
(10011, 'Sneha Gupta', 101, 1101),
(10012, 'Rajesh Kumar', 104, 1101),
(10013, 'Riya Singh', 105, 1101),
(10014, 'Ankit Patel', 102, 1102),
(10015, 'Karan Shah', 103, 1103);

CREATE TABLE AlumniAddress (
  AlumniID INT NOT NULL PRIMARY KEY,
  door_no VARCHAR(10),
  street VARCHAR(50) NOT NULL,
  city VARCHAR(50) NOT NULL,
  state VARCHAR(50) NOT NULL,
  PinCode INT NOT NULL,
  FOREIGN KEY (AlumniID) REFERENCES Alumni(AlumniID)
);
INSERT INTO AlumniAddress (AlumniID, door_no, street, city, state, PinCode) VALUES
(10011, '123', 'Main St', 'Mumbai', 'Maharashtra', 456787),
(10012, '456', 'Elm St', 'Delhi', 'Delhi', 110011),
(10013, '789', 'Oak St', 'Ahmedabad', 'Gujarat', 380015),
(10014, '987', 'Maple St', 'Bangalore', 'Karnataka', 560001),
(10015, '654', 'Pine St', 'Chennai', 'Tamil Nadu', 600001);




-- Create Library Table
CREATE TABLE Library (
  LibraryID INT PRIMARY KEY,
  LibraryName VARCHAR(50) NOT NULL,
  LibraryLocation VARCHAR(100) NOT NULL
);

INSERT INTO Library (LibraryID, LibraryName, LibraryLocation) VALUES
(6, 'National Library of India', 'Management Block'),
(7, 'Indira Gandhi National Centre for the Arts', 'Law Block');




-- Create Fees Table
CREATE TABLE Fees (
  FeesID INT PRIMARY KEY,
  student_id INT NOT NULL,
  Amount DECIMAL(8,2) NOT NULL,
  DatePaid DATE NOT NULL,
  FOREIGN KEY (student_id) REFERENCES Student(student_id)
);

INSERT INTO Fees (FeesID, student_id, Amount, DatePaid) VALUES
(1244, 1003, 500000.00, '2023-04-01'),
(5478, 1007, 750000.00, '2023-04-02'),
(9551, 1002, 100000.00, '2023-04-03'),
(1122, 1009, 600000.00, '2023-04-04'),
(2251, 1004, 800000.00, '2023-04-05'),
(3361, 1008, 900000.00, '2023-04-06'),
(7781, 1001, 120000.00, '2023-04-07'),
(9166, 1006, 450000.00, '2023-04-08'),
(7622, 1005, 550000.00, '2023-04-09'),
(2433, 1010, 650000.00, '2023-04-10'),
(1476, 1011, 400000.00, '2023-04-11'),
(1579, 1019, 250000.00, '2023-04-12'),
(6686, 1020, 50000.00, '2023-04-13'),
(7787, 1018, 350000.00, '2023-04-14'),
(8488, 1012, 600000.00, '2023-04-15'),
(3399, 1016, 700000.00, '2023-04-16'),
(1010, 1015, 90000.00, '2023-04-17'),
(1111, 1014, 250000.00, '2023-04-18'),
(1142, 1013, 300000.00, '2023-04-19'),
(1133, 1017, 400000.00, '2023-04-20'),
(1245, 1021, 500000.00, '2023-04-21'),
(1246, 1022, 750000.00, '2023-04-22'),
(1247, 1023, 100000.00, '2023-04-23'),
(1248, 1024, 600000.00, '2023-04-24'),
(1249, 1025, 800000.00, '2023-04-25'),
(1250, 1026, 900000.00, '2023-04-26'),
(1251, 1027, 120000.00, '2023-04-27'),
(1252, 1028, 450000.00, '2023-04-28'),
(1253, 1029, 550000.00, '2023-04-29'),
(1254, 1030, 650000.00, '2023-04-30'),
(1255, 1031, 400000.00, '2023-05-01'),
(1256, 1032, 250000.00, '2023-05-02'),
(1257, 1033, 50000.00, '2023-05-03'),
(1258, 1034, 350000.00, '2023-05-04'),
(1259, 1035, 600000.00, '2023-05-05'),
(1260, 1036, 700000.00, '2023-05-06'),
(1261, 1037, 90000.00, '2023-05-07'),
(1262, 1038, 250000.00, '2023-05-08'),
(1263, 1039, 300000.00, '2023-05-09'),
(1264, 1040, 400000.00, '2023-05-10'),
(1265, 1041, 500000.00, '2023-05-11'),
(1266, 1042, 750000.00, '2023-05-12'),
(1267, 1043, 100000.00, '2023-05-13'),
(1268, 1044, 600000.00, '2023-05-14'),
(1269, 1045, 800000.00, '2023-05-15'),
(1270, 1046, 900000.00, '2023-05-16'),
(1271, 1047, 120000.00, '2023-05-17'),
(1272, 1048, 450000.00, '2023-05-18'),
(1273, 1049, 550000.00, '2023-05-19'),
(1274, 1050, 650000.00, '2023-05-20'),
(1275, 1051, 400000.00, '2023-05-21'),
(1276, 1052, 250000.00, '2023-05-22'),
(1277, 1053, 50000.00, '2023-05-23'),
(8711, 1054, 550000.00, '2023-05-10'),
(9622, 1055, 800000.00, '2023-05-11'),
(6543, 1056, 400000.00, '2023-05-12'),
(7454, 1057, 350000.00, '2023-05-13'),
(8365, 1058, 600000.00, '2023-05-14'),
(9276, 1059, 750000.00, '2023-05-15'),
(1187, 1060, 250000.00, '2023-05-16'),
(2198, 1061, 90000.00, '2023-05-17'),
(3209, 1062, 150000.00, '2023-05-18'),
(4220, 1063, 500000.00, '2023-05-19'),
(5231, 1064, 650000.00, '2023-05-20'),
(6242, 1065, 350000.00, '2023-05-21');




-- Create College Table
CREATE TABLE College (
  CollegeID INT PRIMARY KEY,
  CollegeName VARCHAR(50) NOT NULL,
  CollegeAddress VARCHAR(100) NOT NULL,
  CollegeWebsite VARCHAR(50) NOT NULL
);

INSERT INTO College (CollegeID, CollegeName, CollegeAddress, CollegeWebsite) VALUES
(601, 'SS Institute Pune', 'Lavsa, Pune, Maharashtra', 'www.ssi.ac.in');




CREATE TABLE Phonenumber (
   id INT NOT NULL AUTO_INCREMENT,
   student_id INT,
   FacultyID INT,
   StaffID INT,
   AlumniID INT,
   phonenumber_1 VARCHAR(20),
   phonenumber_2 varchar (20),
   PRIMARY KEY (id),
   FOREIGN KEY (student_id) REFERENCES Student (student_id),
   FOREIGN KEY (FacultyID) REFERENCES Faculty (FacultyID),
   FOREIGN KEY (StaffID) REFERENCES Staff(StaffID),
   FOREIGN KEY (AlumniID) REFERENCES Alumni(AlumniID)
);

INSERT INTO Phonenumber (id, student_id, phonenumber_1, phonenumber_2) VALUES
(3311, 1001, '+91 9876543210', '+91 1234567890'),
(3312, 1002, '+91 8765432109', '+91 9876543210'),
(3313, 1003, '+91 7654321098', '+91 8765432109'),
(3314, 1004, '+91 6543210987', '+91 7654321098'),
(3315, 1005, '+91 5432109876', '+91 6543210987'),
(3316, 1006, '+91 4321098765', '+91 5432109876'),
(3317, 1007, '+91 3210987654', '+91 4321098765'),
(3318, 1008, '+91 2109876543', '+91 3210987654'),
(3319, 1009, '+91 1098765432', '+91 2109876543'),
(3320, 1010, '+91 0987654321', '+91 1098765432'),
(3321, 1011, '+91 9876543211', '+91 0987654321'),
(3322, 1012, '+91 8765432110', '+91 9876543211'),
(3323, 1013, '+91 7654321099', '+91 8765432110'),
(3324, 1014, '+91 6543210988', '+91 7654321099'),
(3325, 1015, '+91 5432109877', '+91 6543210988'),
(3326, 1016, '+91 4321098766', '+91 5432109877'),
(3327, 1017, '+91 3210987655', '+91 4321098766'),
(3328, 1018, '+91 2109876544', '+91 3210987655'),
(3329, 1019, '+91 1098765433', '+91 2109876544'),
(3330, 1020, '+91 0987654322', '+91 1098765433'),
(3352, 1021, '+91 9876543210', '+91 1234567890'),
(3353, 1022, '+91 8765432109', '+91 9876543210'),
(3354, 1023, '+91 7654321098', '+91 8765432109'),
(3355, 1024, '+91 6543210987', '+91 7654321098'),
(3356, 1025, '+91 5432109876', '+91 6543210987'),
(3357, 1026, '+91 4321098765', '+91 5432109876'),
(3358, 1027, '+91 3210987654', '+91 4321098765'),
(3359, 1028, '+91 2109876543', '+91 3210987654'),
(3360, 1029, '+91 1098765432', '+91 2109876543'),
(3361, 1030, '+91 0987654321', '+91 1098765432'),
(3362, 1031, '+91 9876543211', '+91 0987654321'),
(3363, 1032, '+91 8765432110', '+91 9876543211'),
(3364, 1033, '+91 7654321099', '+91 8765432110'),
(3365, 1034, '+91 6543210988', '+91 7654321099'),
(3366, 1035, '+91 5432109877', '+91 6543210988'),
(3367, 1036, '+91 4321098766', '+91 5432109877'),
(3368, 1037, '+91 3210987655', '+91 4321098766'),
(3369, 1038, '+91 2109876544', '+91 3210987655'),
(3370, 1039, '+91 1098765433', '+91 2109876544'),
(3371, 1040, '+91 0987654322', '+91 1098765433'),
(3372, 1041, '+91 9876543212', '+91 0987654322'),
(3373, 1042, '+91 8765432111', '+91 9876543212'),
(3374, 1043, '+91 7654321100', '+91 8765432111'),
(3375, 1044, '+91 6543210989', '+91 7654321100'),
(3376, 1045, '+91 5432109878', '+91 6543210989'),
(3377, 1046, '+91 4321098767', '+91 5432109878'),
(3378, 1047, '+91 3210987656', '+91 4321098767'),
(3379, 1048, '+91 2109876545', '+91 3210987656'),
(3380, 1049, '+91 1098765434', '+91 2109876545'),
(3381, 1050, '+91 0987654323', '+91 1098765434'),
(3382, 1051, '+91 9876543223', '+91 8765432112'),
(3383, 1052, '+91 8765432122', '+91 7654321101'),
(3384, 1053, '+91 7654321111', '+91 6543210990'),
(3385, 1054, '+91 6543211000', '+91 5432109879'),
(3386, 1055, '+91 5432109889', '+91 4321098768'),
(3387, 1056, '+91 4321098778', '+91 3210987657'),
(3388, 1057, '+91 3210987667', '+91 2109876546'),
(3389, 1058, '+91 2109876556', '+91 1098765435'),
(3390, 1059, '+91 1098765445', '+91 0987654324'),
(3391, 1060, '+91 9876543334', '+91 9876543224'),
(3392, 1061, '+91 8765432223', '+91 8765432111'),
(3393, 1062, '+91 7654321112', '+91 7654321001'),
(3394, 1063, '+91 6543211001', '+91 6543210890'),
(3395, 1064, '+91 5432109890', '+91 5432108779'),
(3396, 1065, '+91 4321098789', '+91 4321097678');




INSERT INTO Phonenumber (id, FacultyID, phonenumber_1, phonenumber_2) VALUES
(3331, 1, '+91 9876543210', '+91 8765432109'),
(3332, 2, '+91 7654321098', NULL),
(3333, 3, '+91 6543210987', NULL),
(3334, 4, '+91 5432109876', '+91 4321098765'),
(3335, 5, '+91 3210987654', '+91 2109876543'),
(3336, 6, '+91 8567687987', NULL),
(3337, 7, '+91 8976754534', NULL),
(3338, 8, '+91 3546567878', NULL),
(3339, 9, NULL, NULL),
(3340, 10, '+91 1098765432', NULL);

INSERT INTO Phonenumber (id, StaffID, phonenumber_1, phonenumber_2) VALUES
(3341, 211, '+91 9876543210', '+91 8765432109'),
(3342, 212, '+91 7654321098', '+91 6543210987'),
(3343, 213, '+91 5432109876', '+91 4321098765'),
(3344, 214, '+91 3210987654', '+91 2109876543'),
(3345, 215, '+91 1098765432', '+91 0987654321');

INSERT INTO Phonenumber (id, AlumniID, phonenumber_1, phonenumber_2) VALUES
(3347, 10011, '+91 9876543210', '+91 8765432109'),
(3348, 10012, '+91 7654321098', NULL),
(3349, 10013, '+91 6543210987', '+91 5432109876'),
(3350, 10014, '+91 1234567890', '+91 2345678901'),
(3351, 10015, '+91 3456789012', NULL);




CREATE TABLE Email (
   id INT NOT NULL AUTO_INCREMENT,
   student_id INT,
   FacultyID INT,
   StaffID INT,
   AlumniID INT,
   emailaddress_1 VARCHAR(50),
   emailaddress_2 varchar (50),
   PRIMARY KEY (id),
   FOREIGN KEY (student_id) REFERENCES Student (student_id),
   FOREIGN KEY (FacultyID) REFERENCES Faculty (FacultyID),
   FOREIGN KEY (StaffID) REFERENCES Staff(StaffID),
   FOREIGN KEY (AlumniID) REFERENCES Alumni(AlumniID)
   
);

INSERT INTO Email (id, student_id, emailaddress_1, emailaddress_2)
VALUES
(4452, 1001, 'aryansharma2@example.com', 'aryansharma3@example.com'),
(4453, 1002, 'nehasingh2@example.com', 'nehasingh3@example.com'),
(4454, 1003, 'rahuldesai2@example.com', 'rahuldesai3@example.com'),
(4455, 1004, 'priyapatel2@example.com', 'priyapatel3@example.com'),
(4456, 1005, 'karangupta2@example.com', 'karangupta3@example.com'),
(4457, 1006, 'anjalishah2@example.com', 'anjalishah3@example.com'),
(4458, 1007, 'amitpatel2@example.com', 'amitpatel3@example.com'),
(4459, 1008, 'divyamishra2@example.com', 'divyamishra3@example.com'),
(4460, 1009, 'rohankumar2@example.com', 'rohankumar3@example.com'),
(4461, 1010, 'soniachoudhary2@example.com', 'soniachoudhary3@example.com'),
(4462, 1011, 'aloktiwari2@example.com', 'aloktiwari3@example.com'),
(4463, 1012, 'poojasharma2@example.com', 'poojasharma3@example.com'),
(4464, 1013, 'rohitverma2@example.com', 'rohitverma3@example.com'),
(4465, 1014, 'shreyasingh2@example.com', 'shreyasingh3@example.com'),
(4466, 1015, 'ankitsharma2@example.com', 'ankitsharma3@example.com'),
(4467, 1016, 'nidhigupta2@example.com', 'nidhigupta3@example.com'),
(4468, 1017, 'vikaspatel2@example.com', 'vikaspatel3@example.com'),
(4469, 1018, 'ritusharma2@example.com', 'ritusharma3@example.com'),
(4470, 1019, 'sahilgupta2@example.com', 'sahilgupta3@example.com'),
(4471, 1020, 'monikasingh2@example.com', 'monikasingh3@example.com'),
(4492, 1021, 'thegodfather2@example.com', 'thegodfather3@example.com'),
(4493, 1022, 'avatar2@example.com', 'avatar3@example.com'),
(4494, 1023, 'forrestgump2@example.com', 'forrestgump3@example.com'),
(4495, 1024, 'inception2@example.com', 'inception3@example.com'),
(4496, 1025, 'pulpfiction2@example.com', 'pulpfiction3@example.com'),
(4497, 1026, 'jurassicpark2@example.com', 'jurassicpark3@example.com'),
(4498, 1027, 'titanic2@example.com', 'titanic3@example.com'),
(4499, 1028, 'missionimpossible2@example.com', 'missionimpossible3@example.com'),
(4500, 1029, 'indianajones2@example.com', 'indianajones3@example.com'),
(4501, 1030, 'starwars2@example.com', 'starwars3@example.com'),
(4502, 1031, 'backtothefuture2@example.com', 'backtothefuture3@example.com'),
(4503, 1032, 'rocky2@example.com', 'rocky3@example.com'),
(4504, 1033, 'jaws2@example.com', 'jaws3@example.com'),
(4505, 1034, 'harrypotter2@example.com', 'harrypotter3@example.com'),
(4506, 1035, 'frozen2@example.com', 'frozen3@example.com'),
(4507, 1036, 'findingnemo2@example.com', 'findingnemo3@example.com'),
(4508, 1037, 'thelionking2@example.com', 'thelionking3@example.com'),
(4509, 1038, 'toystory2@example.com', 'toystory3@example.com'),
(4510, 1039, 'aladdin2@example.com', 'aladdin3@example.com'),
(4511, 1040, 'mrsdoubtfire2@example.com', 'mrsdoubtfire3@example.com'),
(4512, 1041, 'homealone2@example.com', 'homealone3@example.com'),
(4513, 1042, 'ferrisbuellersdayoff2@example.com', 'ferrisbuellersdayoff3@example.com'),
(4514, 1043, 'clueless2@example.com', 'clueless3@example.com'),
(4515, 1044, 'dazedandconfused2@example.com', 'dazedandconfused3@example.com'),
(4516, 1045, 'thebreakfastclub2@example.com', 'thebreakfastclub3@example.com'),
(4517, 1046, 'fightclub2@example.com', 'fightclub3@example.com'),
(4518, 1047, 'theshawshankredemption2@example.com', 'theshawshankredemption3@example.com'),
(4519, 1048, 'goodfellas2@example.com', 'goodfellas3@example.com'),
(4520, 1049, 'thesilenceofthelambs2@example.com', 'thesilenceofthelambs3@example.com'),
(4521, 1050, 'joker2@example.com', 'joker3@example.com'),
(4522, 1051, 'inception2@example.com', 'inception3@example.com'),
(4523, 1052, 'avengers2@example.com', 'avengers3@example.com'),
(4524, 1053, 'titanic2@example.com', 'titanic3@example.com'),
(4525, 1054, 'thegodfather2@example.com', 'thegodfather3@example.com'),
(4526, 1055, 'fightclub2@example.com', 'fightclub3@example.com'),
(4527, 1056, 'forrestgump2@example.com', 'forrestgump3@example.com'),
(4528, 1057, 'pulpfiction2@example.com', 'pulpfiction3@example.com'),
(4529, 1058, 'thehateful8@example.com', 'thehateful9@example.com'),
(4530, 1059, 'starwars2@example.com', 'starwars3@example.com'),
(4531, 1060, 'rocky2@example.com', 'rocky3@example.com'),
(4532, 1061, 'thenotebook2@example.com', 'thenotebook3@example.com'),
(4533, 1062, 'jurassicpark2@example.com', 'jurassicpark3@example.com'),
(4534, 1063, 'missionimpossible2@example.com', 'missionimpossible3@example.com'),
(4535, 1064, 'theexorcist2@example.com', 'theexorcist3@example.com'),
(4536, 1065, 'gladiator2@example.com', 'gladiator3@example.com');

INSERT INTO Email (id,FacultyID, emailaddress_1, emailaddress_2) VALUES
(4472, 1, 'ravikumar@example.com', 'ravi.kumar@example.com'),
(4473, 2, 'snehasharma@example.com', NULL),
(4474, 3, 'sameerdesai@example.com', 'sameer.desai@example.com'),
(4475, 4, 'radhapatel@example.com', NULL),
(4476, 5, 'ajaygupta@example.com', 'ajay.gupta@example.com'),
(4477, 6, 'meerashah@example.com', NULL),
(4478, 7, 'anilpatel@example.com', 'anil.patel@example.com'),
(4479, 8, 'smitamishra@example.com', NULL),
(4480, 9, 'vikaskumar@example.com', 'vikas.kumar@example.com'),
(4481, 10, 'priyachoudhary@example.com', NULL);

INSERT INTO Email (id,StaffID, emailaddress_1, emailaddress_2) VALUES
(4482, 211, 'rajesh.kumar@example.com', 'rajesh.kumar2@example.com'),
(4483, 212, 'shilpa.gupta@example.com', NULL),
(4484, 213, 'amit.singh@example.com', 'amit.singh2@example.com'),
(4485, 214, 'sarika.sharma@example.com', 'sarika.sharma2@example.com'),
(4486, 215, 'sanjay.patel@example.com', NULL);

INSERT INTO Email (id,AlumniID, emailaddress_1, emailaddress_2) VALUES
(4487, 10011, 'snehagupta@example.com', 'sneha.gupta@example.com'),
(4488, 10012, 'rajeshkumar@example.com', 'rajeshkumar@example.com'),
(4489, 10013, 'riyasingh@example.com', 'riyasingh@example.com'),
(4490, 10014, 'ankitpatel@example.com', 'ankitpatel@example.com'),
(4491, 10015, 'karanshah@example.com', 'karanshah@example.com');



