| Column     | Type         | Attribute                          | Index       |
| ---------- | ------------ | ---------------------------------- | ----------- |
| id         | bigint       | auto increment, not null, unsigned | PRIMARY KEY |
| id_student | bigint       | auto increment, not null, unsigned | FOREIGN KEY |
| id_course  | bigint       | auto increment, not null, unsigned | FOREIGN KEY |
| name       | varchar(255) | not null                           |             |
| date       | date         | not null                           |             |
| time       | time         | not null                           |             |
| building   | varchar(50)  | not null                           |             |
| room       | varchar(20)  | not null                           |             |
| duration   | time         |                                    |             |
