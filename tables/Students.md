| Column   | Type         | Attribute                          | Index       |
| -------- | ------------ | ---------------------------------- | ----------- |
| id       | bigint       | auto increment, not null, unsigned | PRIMARY KEY |
| id_laura | bigint       | auto increment, not null, unsigned | FOREIGN KEY |
| name     | varchar(255) | not null                           |             |
| surname  | varchar(255) |                                    |             |
| mail     | varchar(255) |                                    |             |
| phone    | varchar(255) |                                    |             |
| address  | varchar(255) |                                    |             |
