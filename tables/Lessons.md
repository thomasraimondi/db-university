| Column      | Type         | Attribute                          | Index       |
| ----------- | ------------ | ---------------------------------- | ----------- |
| id          | bigint       | auto increment, not null, unsigned | PRIMARY KEY |
| name        | varchar(255) | not null                           |             |
| description | text         |                                    |             |
| start_date  | date         | not null                           |             |
| start_time  | time         | not null                           |             |
| end_time    | time         | not null                           |             |
| buildings   | varchar(255) | not null                           |             |
| room        | varchar(50)  | not null                           |             |
