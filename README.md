# Lab 2 - Conceptual Modeling using Draw.io
This lab will meet the following course objectives:
1. Determine appropriate entity structure for relational databases

2. Apply the correct terminology to an ER Model

3. Design an ER model

## Instructions
In this lab, you will practice writing business rules that describe the relationships between entities. Using the school ER diagram below, write and recreate a conceptual ER diagram that illustrates the relationships shown.

![alt text](https://instructorc.github.io/site/home/images/school_ERD.PNG)

You will record your relationships within this README file.  When writing down the relationships, follow the bullet points below.
- Entity names are uppercase and bolded
- The connecting verb is underlined
- Bidirectionality of the relationship is represented


Once you complete the README.md file, create an ER Diagram based on the relationships you identified. Create the ER Diagram using a free web-based tool called draw.io.  The shapes you will use to create your ER diagram can be found under the "Entity Relation" tab.  Instructions on how to use draw.io are in the assignment resources section below.

## Requirements

### Deliverable 1 (5 Points)
All relationships are identified, including the relationships that are formed when identifying the new **associative entities**


### Deliverable 2 (5 Points)
Update the ReadMe.md file to reflect the relationships. The relationships adhere to the following bullet points below.
- Entity names are uppercase and bolded
- The connecting verb is <ins>underlined</ins>

- Bi-direction of the relationship is represented


### Deliverable 3 (5 Points)
A conceptual Entity Relationship Diagram(ERD) is created to reflect all entities and relationships identified in the write-up

## Submission Guidelines

For this lab, submit 2 items to the repository.  The two items that you will need to submit are listed below: 
1. The README.MD file that identifies the various Entities and briefly describes each entity, including possible attributes, relationships, and assumptions. 
   1. When identifying relationships, be sure to bold and uppercase the entity name, underline the verb, and make sure relationships are bidirectional. 
   2. When identifying assumptions, make sure to formulate assumptions based on what is represented in the school ERD with either a Yes or No. 
   3. You can override this README.md file that contains the instructions or extend this README.md file by listing your requirements below the lab Resources section.

2. The draw.io XML file that contains your ER Diagram.  You will also need to take a snippet of the ER Diagram and add it as an image in your README file.

Once you complete both items above, submit the link to your repository for lab 2 before the due date and time listed.  


## Lab Resources
- [Mark-down Syntax Cheat Sheet](https://enterprise.github.com/downloads/en/markdown-cheatsheet.pdf)
- [Make a ReadMe file Web-based Editor](https://www.makeareadme.com/)
- [Draw.io Web-based diagramming tool](https://app.diagrams.net/)
- [Creating Entity Relationship Diagrams using Draw.io](https://www.youtube.com/watch?v=lAtCySGDD48)


## Completed Work

### Requirements

#### Entities and Possible Attributes

- **STUDENT** represents a student attending the school. Possible attributes include:
  - `StudentId`: Unique ID of a student and the Primary Key. This is required and must be unique.
  - `StudentFirstName`: First name of the student. This is required.
  - `StudentMiddleName`: Middle name of the student. This is optional.
  - `StudentLastName`: Last name of the student. This is required.
  - `StudentAddressLine1`: First line of the student address. Usually contains a street number and street. This is required.
  - `StudentAddressLine2`: Second line of a student address. Usually contains an apartment number and is optional.
  - `StudentAddressCity`: City of the student's address. This is required.
  - `StudentAddressState`: State of the student's address. This is required.
  - `StudentAddressZip`: Zip code of the student's address. This is required.
  - `StudentSeatId`: The seat id assigned to the student. A foreign key to **SEAT**.
- **SEAT** represents a seat occupied by a student. Possible attributes include:
  - `SeatId`: Unique ID of a seat and the Primary Key. This is required and must be unique.
  - `SeatRow`: The row the seat is located in. This is required.
  - `SeatNumber`: The number of the seat in the row. This is required.
- **COURSE** represents a course offered by the school. Possible attributes include:
  - `CourseId`: Unique ID of a course and the Primary Key. This is required and must be unique.
  - `CourseNumber`: The number of the course. This is required and must be unique.
  - `CourseName`: The course name. This is required.
  - `CourseDescription`: A description of the course. This is optional.
  - `InstructorId`: The id of the course instructor. A foreign key to **INSTRUCTOR**.
- **STUDENTCOURSE** is an associative entity that resolves the many-to-many relationship between **STUDENT** and **COURSE**. Each instance represents one student taking one course. Possible attributes include:
  - `StudentId`: The student id of the student taking the course. This is the first part of the compound primary key. It is also a foreign key to the **STUDENT** table.
  - `CourseId`: The course id of the course the student is taking. This is the second part of the compound primary key. It is also a foreign key to the **COURSE** table.
- **INSTRUCTOR** represents an instructor responsible for teaching a course. Possible attributes include:
  - `InstructorId`: Unique instructor id and the Primary Key. This is required and must be unique.
  - `InstructorFirstName`: First name of the instructor. This is required.
  - `InstructorMiddleName`: Middle name of the instructor. This is optional.
  - `InstructorLastName`: Last name of the instructor. This is required.
  - `InstructorFaculty`: The instructor's faculty. This is required.
- **SECTION** represents a teaching section associated with one or more courses. Possible attribute inculde:
  - `SectionNumber`: Unique number of a section and the Primary Key. This is required and must be unique.
  - `ProfessorId`: The id of the section professor. A foreign key to **PROFESSOR**.
- **COURSESECTION** is an associative entity that resolves the many-to-many relationship between **COURSE** and **SECTION**. Each instance represents one course paired with one section. Possible attributes include:
  - `CourseId`, The course id of the course the section has. This is the first part of the compound primary key. It is also a foreign key to the **COURSE** table.
  - `SectionNumber`: The section number of the section the course has. This is the second part of the compound primary key. It is also a foreign key to the **SECTION** table.
- **PROFESSOR** represents a professor who may be assigned to teach sections. Possible attributes include:
  - `ProfessorId`: Unique professor id and the Primary Key. This is required and must be unique.
  - `ProfessorFirstName`: First name of the professor. This is required.
  - `ProfessorMiddleName`: Middle name of the professor. This is optional.
  - `ProfessorLastName`: Last name of the professor. This is required.
  - `ProfessorFaculty`: The professor's faculty. This is required.
  
#### Relationships

- Each **STUDENT** <ins>fills</ins> exactly one **SEAT**. Each **SEAT** <ins>is filled by</ins> exactly one **STUDENT**.
- Each **STUDENT** <ins>has</ins> one or more **STUDENTCOURSE** instances. Each **STUDENTCOURSE** <ins>belongs to</ins> exactly one **STUDENT**.
- Each **COURSE** <ins>has</ins> one or more **STUDENTCOURSE** instances. Each **STUDENTCOURSE** <ins>is for</ins> exactly one **COURSE**.
- Each **INSTRUCTOR** <ins>teaches</ins> one or more **COURSE** instances. Each **COURSE** <ins>is taught by</ins> exactly one **INSTRUCTOR**.
- Each **COURSE** <ins>has</ins> one or more **COURSESECTION** instances. Each **COURSESECTION** <ins>belongs to</ins> exactly one **COURSE**.
- Each **SECTION** <ins>has</ins> one or more **COURSESECTION** instances. Each **COURSESECTION** <ins>references</ins> exactly one **SECTION**.
- Each **PROFESSOR** <ins>teaches</ins> zero or more **SECTION** instances. Each **SECTION** <ins>is taught by</ins> exactly one **PROFESSOR**.

#### Assumptions

- Must each **STUDENT** fill exactly one **SEAT**? **Yes.** A student cannot have no seat or multiple seats.
- Must each **SEAT** be filled by exactly one **STUDENT**? **Yes.** A seat cannot be empty or shared by multiple students.
- Can a **STUDENT** take multiple **COURSE** instances? **Yes.** Each student must take at least one course and may take several.
- Can a **COURSE** have multiple **STUDENT** instances? **Yes.** Each course must have at least one student and may have several.
- Is `CourseNumber` unique in the **COURSE** table? **No.** The concept of department may be introduced later. If this occurs, the course numbers could be used more than once.
- Can an **INSTRUCTOR** teach multiple **COURSE** instances? **Yes.** Each instructor must teach at least one course and may teach several.
- Can a **COURSE** be taught by multiple **INSTRUCTOR** instances? **No.** Each course must be taught by exactly one instructor.
- Can a **COURSE** have multiple **SECTION** instances? **Yes.** Each course must have at least one section and may have several.
- Can a **SECTION** belong to multiple **COURSE** instances? **Yes.** Each section must be associated with at least one course and may be associated with several.
- Can a **PROFESSOR** have no assigned **SECTION** instances? **Yes.** A professor may teach zero, one, or multiple sections.
- Can a **SECTION** be taught by multiple **PROFESSOR** instances? **No.** Each section must be taught by exactly one professor.

### Entity Relationship Diagram(ERD)

![Entity Relationship Diagram(ERD)](https://github.com/mbonhamluc/luc_comp251_lab2/blob/main/Lab2.png)