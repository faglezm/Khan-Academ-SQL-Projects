# Khan-Academ-SQL-Projects
Khan Academy SQL Module provides the technical skills and foundations for SQL query composition. Topics like querying, database management and managing data, 

In this course 4 projects were developed with certain grade of tecchnical difficulty. This technical skills set the base of great foundations for future projects.

## Project: App Basic library booking system

In this project, I create a sample query for a Library booking app that stores your data in a SQL database (which is pretty likely!) and write SQL statements that might look like their own SQL.

I have CREATE(ed) tables, INSERT(ed) columns and information as well creating a possible structure of a book store loan system that helps to track where the books are, name, author and the status together with the person that loans it.


CREATE TABLE user (id INTEGER PRIMARY KEY,
    name TEXT,
    email TEXT);
    
INSERT INTO user (name, email)
    VALUES ("Chris Mior", "chris.mr08@hotmail.com");
INSERT INTO user (name, email)
    VALUES ("Zara Lauren", "laurenza.79@hotmail.com");
INSERT INTO user (name, email)
    VALUES ("Michael Hilfiger", "milauren9023@icloud.com");
INSERT INTO user (name, email)
    VALUES ("Karl Klein", "Kk.leinco@gmail.com");
    
CREATE TABLE books (id INTEGER PRIMARY KEY,
    name TEXT,
    author TEXT,
    pages INTEGER,
    year INTEGER,
    status INTEGER);
    
INSERT INTO books (name, author, pages, year, status)
    VALUES ("Powerarchy", "Melanie Joy", 197, 2017, "Shelve");
INSERT INTO books (name, author, pages, year, status)
    VALUES ("Practical SQL: A beginner guide to storytelling with data", "ANthony DeBarros", 349, 2018, "Loan");
INSERT INTO books (name, author, pages, year, status)
    VALUES ("Business Diagnosis", "Richard Mimick", 250, 2014, "On hold");
INSERT INTO books (name, author, pages, year, status)
    VALUES ("HomoDeus", "Yuval Noah Sharari", 387, 2018, "Loan");
    
SELECT * FROM books;

/* UPDATE */
UPDATE books SET status = "On hold" WHERE name = "Powerarchy";

SELECT * FROM books;

/* DELETE */
DELETE FROM books WHERE id = 3;

SELECT * FROM books;

*/

