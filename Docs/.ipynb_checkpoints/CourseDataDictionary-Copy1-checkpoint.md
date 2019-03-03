# BA 510 Course Data Project
__Spring 2019__

## Data Dictionary 

## Courses
| Column      | Description |
| ----------- | ----------- |
| CRN     | Primary Key - A unique code given by the university to identify each class       |
| Cat_ID  | Foreign Key - The course ID which identifies each course offered by the university        |
| Term     | The terms in which in course is offered       |
| Credits  | The amount of credits each course is worth        |
| Section     | The section of the course       |
| Faculty  | The instructor/s for each course/section        |
| Capacity     | The maximum capacity for each section of course       |
| Actual  | The number of students registered for that section of course        |
| Remaining  | The number of seats still available in each section        |

## Course_Meeting
| Column      | Description |
| ----------- | ----------- |
| MID     | Primary Key - this is a surrogate key assigned to each course meeting       |
| CRN  | Foreign Key - as above        |
| Location     | The location for each class time meeting      |
| Day  | The day of each meeting        |
| Start Time     | The start time of each meeting      |
| End Time  | The end time of each meeting        |

## Catolog
| Column      | Description |
| ----------- | ----------- |
| Cat_ID     | Primary key - The course ID which identifies each course offered by the university      |
| Title  | The name of each course        |

