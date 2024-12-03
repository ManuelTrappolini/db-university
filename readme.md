## table names
- department
- degree_course
- Course
- Teachers
- Exams
- Students


## department table structure

- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- department_name       | VARCHAR(30) NOT NULL
- degree course's_ID    |  BIGINT - (UNSIGNED)

# degree course table structure
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- department's_ID       | BIGINT - (UNSIGNED)
- students'ID           | BIGINT - (UNSIGNED)
- name                  | VARCHAR(30) NOTNULL

## courses table structure
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- name                  | VARCHAR(30) NOTNULL
- degree_course's_ID    | BIGINT - (UNSIGNED)
- Teacher's_ID          | BIGINT - (UNSIGNED)
- Exams_ID              | BIGINT - (UNSIGNED)
- Student's_ID          | BIGINT - (UNSIGNED)
 
## Teachers table structure
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- firstname             | VARCHAR(30) NOTNULL
- lastname              | VARCHAR(30) NOTNULL
- address               | VARCHAR() - NOTNULL


# Exams table structure
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- exam_name             | VARCHAR(30) -  NOT NULL
- Rate                  | TINYINT -  NOT NULL
- course_ID             | BIGINT - (UNSIGNED)
- student's_ID          | BIGINT - (UNSIGNED)
- date                  |

## - Students table structure
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- student's_ID          | BIGINT - (UNSIGNED)
- degree_course's_ID    | BIGINT - (UNSIGNED)
- Exams_ID              | BIGINT - (UNSIGNED)
- firstname             | VARCHAR(30) NOTNULL
- lastname              | VARCHAR(30) NOTNULL
- adress                | VARCHAR() - NOTNULL