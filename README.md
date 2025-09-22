CREATE DATABASE Library;
USE Library;
CREATE TABLE Books (
 book_id INT AUTO_INCREMENT PRIMARY KEY,
 title VARCHAR(255) NOT NULL,
 author VARCHAR(255) NOT NULL,
 genre VARCHAR(100),
 Published_year YEAR,
 is_available BOOLEAN DEFAULT TRUE);
 INSERT INTO Books(title,author,genre,published_year)values('Jungle Book','Rudyard Kipling','Fiction',1994),
 ('The Great Gatsby','F. Scott Fitzgerald','Fiction',1925),('The Catcher in the Rye','J D Salinger','Claasic',1951);
 
 CREATE TABLE Members (
 member_id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
 name VARCHAR(255)NOT NULL,
 email VARCHAR(255),
 Phone_number VARCHAR(10),
 join_date DATE DEFAULT(CURRENT_DATE) );
 INSERT INTO Members(name, email, Phone_number) values('Alen King','alen12@gmail.com','8789705241'),('Alec Hoffman','alec45@gmail.com','8796845331');
 
 CREATE TABLE Librarians (
 librarian_id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
 name VARCHAR (255) NOT NULL,
 email VARCHAR(255),
 Phone_number VARCHAR(10),
 hire_date DATE DEFAULT(CURRENT_DATE));
 INSERT INTO Librarians(name, email, Phone_number) values ('Ejaj','ejaj63@gmail.com','8789705241'),('Nail Horn','nail52@gmail.com','8796524163');
 
 CREATE TABLE Borrowing(
loan_id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
book_id INT,
member_id INT,
borrow_date DATE DEFAULT(CURRENT_DATE),
return_date DATE,
librarian_id INT,
FOREIGN KEY(book_id) REFERENCES Books(book_id),
FOREIGN KEY(member_id) REFERENCES Members(member_id),
FOREIGN KEY(librarian_id) REFERENCES Librarians(librarian_id) );

INSERT INTO Borrowing( book_id, member_id, librarian_id, borrow_date,return_date) values (1,1,1,CURRENT_DATE,'2025-09-30'),
(2,2,2,CURRENT_DATE,'2025-10-01');


	
 
