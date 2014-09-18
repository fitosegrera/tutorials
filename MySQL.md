MySQL Tutorials
================ 
General tutorials and references on MySQL databases.


###MySQL Commands
	sudo /etc/init.d/mysql start #stop or restart

	mysql -u root -p #login; notice that the password is not written

	control+l #clear screen

	status #Status of MySQL

	show databases; #Shows all the databases available in the server

	use <DATABASE NAME> #Replace DATABASE NAME with the name of the DB you want to use

	show tables; #Show the tables in a database

	describe <NAME OF TABLE> #Describe the table elements

	CREATE DATABASE project_name DEFAULT CHARACTER SET utf8 COLLATE utf8_bin; #create a new database for a project and set the character set to utf8 binary

	GRANT ALL PRIVILEGES ON project_name.* TO 'the_user'@'localhost' IDENTIFIED BY 'the_password'; #create and grant access to "my_project" database to the_user with "the_password" only when connected from localhost

	drop database my_project; #delete a database

	drop table my_table; #delete a table

	show warnings; #show errors if prompetd if you get errors

To call a .sql file with all the commands necesary for to setup a new user and grant him acces to a specific database... use:

	mysql -u root -p < setup.sql 

And the setup.sql file would look like:

	CREATE DATABASE my_project_database DEFAULT CHARACTER SET utf8 COLLATE utf8_bin;

	USE my_project_database;

	GRANT ALL PRIVILEGES ON my_project_database.* TO 'the_user'@'localhost' IDENTIFIED BY 'the_password';

Another method to load a .sql file will be loging in to mysql as root:

	mysql -u root -p < setup.sql 

Then type:

	source setup.sql

**NOTE: For this last method you should login msql from the folder where your setup.sql file is. The command source stablishes a very smooth workflow**

---------------------------
###NOTES on mysql:

unsigned --> means that you shift the range of numbers to start from 0 (not dealing with negative numbers in your range) 

balance --> Any start tag needs a closing tag

->(arrow) --> Is asking to complete the command

Atomic --> Refers to everything or nothing but no inbetween...

ID --> Unique identificator for a group of tables

---------------------------
###Complementary Stuff
__Terminal Commands__

	history	#shows history
	history -c #clears history
	whoami
	control+l #clear screen
	touch filename.sql #any extension works... this command creates an empty file