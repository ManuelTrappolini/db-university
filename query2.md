## 1. Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(`enrolment_date`) AS `year`, COUNT(`id`) AS `enrolments`
FROM `students`
GROUP BY `year`


## 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT `office_address` AS `office`, COUNT(`id`) AS `teachers`
FROM `teachers`
GROUP BY `office_address`


## 3. Calcolare la media dei voti di ogni appello d'esame

SELECT AVG(vote) AS `media`,  `exam_id`
FROM `exam_student`
GROUP BY `exam_id`


## 4.Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT  COUNT(`degrees`.`id`) AS `number_of_degrees`, `departments`.`name`
FROM `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
GROUP BY `departments`.`name`


## 5. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT  `students`.*,
`degrees`.`name` AS `degree_name`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'


## 6. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT  `departments`.`name` AS `department_name`,
`degrees`.`name` AS `degree_name`
FROM `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `degrees`.`name` LIKE '%Corso di Laurea Magistrale%'
AND `departments`.`name` = 'Dipartimento di Neuroscienze'


## 7. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT  `teachers`.`surname` AS `teacher_surname`,
`teachers`.`name` AS `teacher_name`,
`courses`.`name` AS `courses_name`
FROM `teachers`
JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
WHERE `teachers`.`id` = 44


## 8. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT  `students`.*,
`degrees`.*,
`departments`.`name`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `degrees`.`name` LIKE '%Corso di Laurea%'
ORDER BY `students`.`surname` ASC, `students`.`name` ASC;


# 9. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT  `teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teacher_surname`,
`degrees`.`name` AS `degree_name`,
`courses`.`name`AS `courses_name`
FROM `degrees`
JOIN `courses` ON `courses`.`degree_id` = `degrees`.`id`
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`;


# 10.Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

SELECT DISTINCT `teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teacher_surname`,
`departments`.`name` AS `department_name`
FROM `teachers`
JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `courses` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Matematica'
