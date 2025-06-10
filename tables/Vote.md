| Column        | Type         | Attribute                          | Index       |
| ------------- | ------------ | ---------------------------------- | ----------- |
| id            | bigint       | auto increment, not null, unsigned | PRIMARY KEY |
| id_appeal     | bigint       | auto increment, not null, unsigned | FOREIGN KEY |
| name          | varchar(255) | not null                           |             |
| vote          | char(2)      | not null                           |             |
| type          | varchar(210) | not null                           |             |
| appeal_passed | boolean      | not null                           |             |
