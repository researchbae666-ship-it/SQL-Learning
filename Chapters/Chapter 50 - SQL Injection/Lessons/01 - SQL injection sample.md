---
lesson_id: C50-L01
chapter: 50
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C50-L01: SQL injection sample

## Textbook excerpt

Chapter 50: SQL Injection
Introduction
SQL injection is an attempt to access a website's database tables by injecting SQL into a form
field. If a web server does not protect against SQL injection attacks, a hacker can trick the
database into running the additional SQL code. By executing their own SQL code, hackers can
upgrade their account access, view someone else's private information, or make any other
modifications to the database.


Examples
SQL injection sample

Assuming the call to your web application's login handler looks like this:

 https://somepage.com/ajax/login.ashx?username=admin&password=123


Now in login.ashx, you read these values:

 strUserName = getHttpsRequestParameterString("username");
 strPassword = getHttpsRequestParameterString("password");


and query your database to determine whether a user with that password exists.

So you construct an SQL query string:

 txtSQL = "SELECT * FROM Users WHERE username = '" + strUserName + "' AND password = '"+
 strPassword +"'";


This will work if the username and password do not contain a quote.

However, if one of the parameters does contain a quote, the SQL that gets sent to the database
will look like this:

 -- strUserName = "d'Alambert";
 txtSQL = "SELECT * FROM Users WHERE username = 'd'Alambert' AND password = '123'";


This will result in a syntax error, because the quote after the d in d'Alambert ends the SQL string.

You could correct this by escaping quotes in username and password, e.g.:

 strUserName = strUserName.Replace("'", "''");
 strPassword = strPassword.Replace("'", "''");


However, it's more appropriate to use parameters:



 cmd.CommandText = "SELECT * FROM Users WHERE username = @username AND password = @password";

 cmd.Parameters.Add("@username", strUserName);
 cmd.Parameters.Add("@password", strPassword);


If you do not use parameters, and forget to replace quote in even one of the values, then a
malicious user (aka hacker) can use this to execute SQL commands on your database.

For example, if an attacker is evil, he/she will set the password to

 lol'; DROP DATABASE master; --


and then the SQL will look like this:

 "SELECT * FROM Users WHERE username = 'somebody' AND password = 'lol'; DROP DATABASE master; -
 -'";


Unfortunately for you, this is valid SQL, and the DB will execute this!

This type of exploit is called an SQL injection.

There are many other things a malicious user could do, such as stealing every user's email
address, steal everyone's password, steal credit card numbers, steal any amount of data in your
database, etc.

This is why you always need to escape your strings.
And the fact that you'll invariably forget to do so sooner or later is exactly why you should use
parameters. Because if you use parameters, then your programming language framework will do
any necessary escaping for you.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
