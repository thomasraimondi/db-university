| Column        | Type         | Attribute                          | Index       |
| ------------- | ------------ | ---------------------------------- | ----------- |
| id            | bigint       | auto increment, not null, unsigned | PRIMARY KEY |
| id_department | bigint       | auto increment, not null, unsigned | FOREIGN KEY |
| name          | varchar(255) | not null                           |             |
| description   | text         |                                    |             |
| title_study   | varchar(255) | not null                           |             |
| duration      | varchar(20)  |                                    |             |
