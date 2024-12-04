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


# degree course table structure (one to many -> departments)
)
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- department_ID       | BIGINT - (UNSIGNED)
- name                  | VARCHAR(30) NOTNULL

## courses table structure (one to many -> degrees)
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- name                  | VARCHAR(30) NOTNULL
- degree_course_ID      | BIGINT - (UNSIGNED)

 
## Teachers table structure (many to many-> course)
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- firstname             | VARCHAR(30) NOTNULL
- lastname              | VARCHAR(30) NOTNULL
- address               | VARCHAR() - NOTNULL

## Pivot: teacher - course
- teacher_ID
- course_ID


# Exams table structure
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- exam_name             | VARCHAR(30) -  NOT NULL
- course_ID             | BIGINT - (UNSIGNED)
- date                  |

## - Students table structure(one to many -> degrees) (many to many -> exams)
- ID                    | BIGINT - AUTO_INCREMENT - PRIMARY KEY(UNIQUE - NOTNULL)
- degree_course_ID      | BIGINT - (UNSIGNED)
- Exams_ID              | BIGINT - (UNSIGNED)
- firstname             | VARCHAR(30) NOTNULL
- lastname              | VARCHAR(30) NOTNULL
- adress                | VARCHAR() - NOTNULL

## Pivot: exam-student
- student_id
- exam_id
- vote