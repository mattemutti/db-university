## Group by

- Contare quanti iscritti ci sono stati ogni anno

SELECT COUNT(id), YEAR(`enrolment_date`) 
FROM `students` 
GROUP BY YEAR(`enrolment_date`);

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT COUNT(id), `office_address` 
FROM `teachers` 
GROUP BY `office_address`;

- Calcolare la media dei voti di ogni appello d'esame



- Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT COUNT(id), `name` 
FROM `degrees` 
GROUP BY `name`;



## Joins

- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT `students`.`id`,`students`.`name`,`students`.`surname`, `degrees`.`name`
FROM `students`
JOIN `degrees` ON `students`.`id` = `degree_id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT `degrees`.`name`, `departments`.`name` 
FROM `degrees` 
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` 
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze';

- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT `course_teacher`.`teacher_id`, `courses`.`id`, `courses`.`name` 
FROM `course_teacher` 
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` 
WHERE `course_teacher`.`teacher_id` = '44';


- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome



- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti



- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)



# BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.
