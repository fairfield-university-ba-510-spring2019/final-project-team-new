# BA 510 Course Data Project
# Team New
__Spring 2019__

## Entity Relationship Diagram (ERD)

![](Courses.jpeg)

## Data Dictionary - Database

### Courses
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __CRN__     | Primary Key - A code given by the university to identify each class   |   smallint   |
| __Term__     | Primary Key - The term in which in course is offered   |   varchar(20)   |
| *Cat_ID*  | Foreign Key - The course ID which identifies each course offered by the university   |   varchar(10)   |
| *FID*  | Foreign Key - The primary instructor for each course/section   |   varchar(50)   |
| Section | The section of the course   |   varchar(10)   |
| Credits  | The amount of credits each course is worth   |   tinyint   |   
| Capacity     | The maximum capacity for each section of course   |   smallint   |
| Actual  | The number of students registered for that section of course   |   smallint   |
| Remaining  | The number of seats still available in each section     |   smallint   |

### Course_Meeting
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __MID__     | Primary Key - this is a surrogate key assigned to each course meeting   |   integer   |
| *CRN*  | Foreign Key - as above   |   smallint  |
| *Term*  | Foreign Key - as above   |   varchar(20)   |
| *LID*    | Foreign Key - as below   |   smallint   |
| Day  | The day of each meeting   |   text NOT NULL   |
| Start_Time     | The start time of each meeting   |   time   |
| End_Time  | The end time of each meeting   |   time   |


### Location
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __LID__     | Primary key - this is a surrogate key assigned to each room  |   integer   |
| Room | The location for each class time meeting   |   varchar(20)   |

### Faculty
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __FID__     | Primary key - this is a surrogate key assigned to each faculty  | integer   |
| Faculty_Name | The name of the primary instructor for each course   |   varchar(50)   |


### Catalog_ID
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __Cat_ID__     | Primary key - The course ID which identifies each course offered by the university   |   varchar(10)   |
| *Prg_Code*    | Foreign key - As below   |   varchar(5)   |
| Title  | The name of each course   |   varchar(150)   |
| Prerequisites  | The Cat_ID that must be taken prior to taking the course   |   varchar(10)   |   
| Corequisites  | The Cat_ID that must be taken at the same time as the course   |   varchar(10)   |

### Program
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __Prg_Code__     | Primary key - The code for each Program type   |   varchar(5)   |
| Program_Name | The name of the program the University offers   |  varchar(150)   | 

### Fees
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __Cat_ID__     | Primary key - The Catalog ID   |   varchar(10)   |
| __Term__     | Primary Key - The term in which in course is offered   |   varchar(20)   |
| Fee | Additional fees required during each course   |   decimal   |


######################################################################################################
## Data Dictionary - Data Warehouse

### CourseFacts
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __CRN__     | Primary Key - A code given by the university to identify each class   |   smallint   |
| __Term__     | Primary Key - The term in which in course is offered   |   varchar(20)   |
| Faculty_Name | The name of the primary instructor for each course   |   varchar(50)   |
| Title  | The name of each course   |   varchar(150)   |
| Cat_ID | The course ID which identifies each course offered by the university   |   varchar(10)   |
| *LID*    | Foreign Key - as below   |   smallint   |
| *MID*   | Foreign Key - as below   |   smallint   |
| *PID*  | Foreign Key - as below   |   smallint   |
| *FeeID* | Foreign Key - as below   | smallint   |
| Section | The section of the course   |   varchar(10)   |
| Capacity     | The maximum capacity for each section of course   |   smallint   |
| Actual  | The number of students registered for that section of course   |   smallint   |
| Remaining  | The number of seats still available in each section     |   smallint   |

### Meeting
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __MID__     | Primary Key - this is a surrogate key assigned to each course meeting   |   integer   |
| Day  | The day of each meeting   |   text NOT NULL   |
| Start_Time     | The start time of each meeting   |   time   |
| End_Time  | The end time of each meeting   |   time   |


### Location
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __LID__     | Primary key - this is a surrogate key assigned to each room  |   integer   |
| Room | The location for each class time meeting   |   varchar(20)   |

### FeeID
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __FeeID__     | Primary key - this is a surrogate key assigned to each fee from the catalog | integer   |
| Cat_ID | The course ID which identifies each course offered by the university   |   varchar(10)   |
| Academic_Year   | The year for which the course fee exists   |   varchar(15)   |
| Amount   |   The text from the "fees" field in the Course Catalog   | varchar(30)   |


### Program1
| Column      | Description | Datatype |
| ----------- | ----------- | -------- |
| __PID__   |   Primary key - this is a surrogate key assigned to each Prg_Code   |  integer   |
| Prg_Code     | The code for each Program type   |   varchar(5)   |
| Program_Name | The name of the program the University offers   |  varchar(150)   | 



