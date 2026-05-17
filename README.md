# VAPT
SQL Injection to DVWA.

Step 1: I have injected a “ ‘ ” in the field to check if the file has any vulnerabilities or not. And the return error sms confirmed that there is SQLi possible.
Now, the 2nd step is to bypass the error and get the number of tables and columns in the DB. 




Step 2: “-- -” This means comment out everything after these characters. 
And we will try the “order by x” command one by one to get the number of tables in the database. Here, x is a variable. For my result, I have done 1-100. And got 2 tables.



When I used more than 2, I got an error that means there are 2 columns.

Step 3: 

Union command gave me the column details.
Step 4: It's time to get the Information Schema 

 ' union select 1,(table_name) from information_schema.tables where table_schema=database()-- -

This command 
This gives the schema details.

Step 5: Get the column name from the table



Got the credential 
Now its time to get the password.


Using command is: ' union select 1,group_concat(user,'::',password) from users-- -

Here we see user login credential. 
Username = admin
Password  = 5f4dcc3b5aa765d61d8327deb882cf99

