### 1. Contare quanti iscritti ci sono stati ogni anno

### query:

SELECT YEAR(enrolment_date) AS enrolment_year, COUNT(id) AS count_of_students
FROM students
GROUP BY YEAR(enrolment_date),

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

### query:

SELECT office_address,COUNT(id) AS count_of_teachers
FROM teachers
GROUP BY office_address

### 3. Calcolare la media dei voti di ogni appello d'esame

### query:

SELECT exam_id, AVG(vote) AS avarage_vote
FROM exam_student
GROUP BY exam_id

### 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

### query:

SELECT department_id, COUNT(id) AS number_of_courses
FROM degrees
GROUP BY department_id
