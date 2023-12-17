database tables: 

use wisdroom; --database Name

CREATE TABLE students (
    id INT NOT NULL AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    student_code VARCHAR(20) NOT NULL,
    PRIMARY KEY (id),
    UNIQUE KEY (student_code)
);

CREATE TABLE studentmessages (
    id int NOT NULL AUTO_INCREMENT,
    student_id int NOT NULL,
    message text,
    file_data LONGBLOB,
    file_extension VARCHAR(50),
    received_flag BOOLEAN DEFAULT FALSE,
    PRIMARY KEY (id),
    FOREIGN KEY (student_id) 
        REFERENCES students_table(student_id)
);
