### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

### query:

SELECT std.\*,deg.name AS deg_name
FROM students std
INNER JOIN degrees deg on std.degree_id = deg.id
WHERE deg.name = "Corso di Laurea in Economia"

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

### query:

SELECT deg.\*,dep.name AS dep_name
FROM degrees deg
INNER JOIN departments dep on deg.department_id = dep.id
WHERE dep.name="Dipartimento di Neuroscienze" and deg.level="magistrale"

### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

### query:

SELECT c.\*,concat(t.name," ",t.surname) AS teacher_fullname
FROM teachers t
INNER JOIN course_teacher ct on t.id=ct.teacher_id
INNER JOIN courses c on c.id = ct.course_id
WHERE t.id=44

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

### query:

SELECT std.\*,deg.name AS degrees_name,dep.name AS dep_name
FROM students std
INNER JOIN degrees deg on std.degree_id = deg.id
INNER JOIN departments dep on deg.department_id = dep.id
ORDER BY std.surname,std.name

### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

### query:

SELECT deg.name AS degrees_name, c.name AS course_name, concat(t.name," ",t.surname) AS teacher_fullname
FROM degrees deg
INNER JOIN courses c on deg.id = c.degree_id
INNER JOIN course_teacher ct on c.id = ct.course_id
INNER JOIN teachers t on t.id = ct.teacher_id

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

### query:

SELECT distinct(t.id),concat(t.name," ",t.surname) AS teacher_fullname,dep.name AS dep_name
FROM teachers t
INNER JOIN course_teacher ct on ct.teacher_id = t.id
INNER JOIN courses c on c.id = ct.course_id
INNER JOIN degrees deg on deg.id = c.degree_id
INNER JOIN departments dep on dep.id = deg.department_id
WHERE dep.name = "Dipartimento di Matematica"

### BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

### query:

SELECT std.id,concat(std.name," ",std.surname) AS std_fullname,count(c.name) AS tentative,c.name AS course_name, max(es.vote) AS max_vote
FROM students std
INNER JOIN exam_student es on std.id = es.student_id
INNER JOIN exams e on es.exam_id = e.id
inner join courses c on e.course_id = c.id
group by std.id,c.id
having max_vote >18
order by c.name,std.name
