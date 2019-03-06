# BA 510 Course Data Project
__Spring 2019__

## Entity Relationship Diagram (ERD)

![](Courses.jpeg)

## Data Dictionary 

## Courses
| Column      | Description |
| ----------- | ----------- |
| __CRN__     | Primary Key - A unique code given by the university to identify each class       |
| __Term__     | Primary Key - The term in which in course is offered       |
| *Cat_ID*  | Foreign Key - The course ID which identifies each course offered by the university        |
| *FID*  | Foreign Key - The instructor/s for each course/section        |
| Credits  | The amount of credits each course is worth        |
| Section     | The section of the course       |
| Faculty  | The instructor/s for each course/section        |
| Capacity     | The maximum capacity for each section of course       |
| Actual  | The number of students registered for that section of course        |
| Remaining  | The number of seats still available in each section        |

## Course_Meeting
| Column      | Description |
| ----------- | ----------- |
| __MID__     | Primary Key - this is a surrogate key assigned to each course meeting       |
| *CRN*  | Foreign Key - as above        |
| *Term*  | Foreign Key - as above        |
| *LID*    | Foreign Key - as above      |
| Day  | The day of each meeting        |
| Start Time     | The start time of each meeting      |
| End Time  | The end time of each meeting        |
The location for each class time meeting

## Location
| Column      | Description |
| ----------- | ----------- |
| __LID__     | Primary key - The Location ID       |
| Room | The name of room where the course meeting takes place        |

## Faculty
| Column      | Description |
| ----------- | ----------- |
| __FID__     | Primary key - The Faculty ID       |
| Faculty | The name of the instructor for each course        |


## Catolog
| Column      | Description |
| ----------- | ----------- |
| __Cat_ID__     | Primary key - The Catalog ID      |
| *Prg_Code*    | Foreign key - As below      |
| Title  | The name of each course        |
| Prerequisites  | The name of the courses that must be taken prior to to the course       |
| Corequisites  | The name of the courses that must be taken at the same time to the course        |

## Program
| Column      | Description |
| ----------- | ----------- |
| __Prg_Code__     | Primary key - The code for each Program type       |
| Program Name | The name of each program the University offers        |

## Fees
| Column      | Description |
| ----------- | ----------- |
| __Cat_ID__     | Primary key - The Catalog ID       |
| __Term__     | Primary Key - The term in which in course is offered     |
| Fee | Additional fees required during each course       |
