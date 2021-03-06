# ORM Mapping Database Rows to Ruby Objects

## Objectives

1. Write a method that turns database rows into Ruby objects 
2. Write methods that allow you to search a database

## Overview

We are going to continue building out the `Student` class of our app. We are in the middle of building an app to help a public school's adminstrators keep track of their students. In this app we have a `Student` class. Each individual students has two attributes, a `name` and a `grade`, i.e. 9th, 10th, 11th, etc. 

Our administrators need to save the student objects that this class produces to a database. We've set up the database for you in the `config/environment.rb` file. 

Let's take a look:

```ruby
require 'sqlite3'
require_relative '../lib/student'

DB = {:conn => SQLite3::Database.new("db/students.db")}
```
Your connection to the database can be referred to, throughout your program, like this: `DB[:conn]`. 

So far we built the ability to create the students table in the database (`Student.create_table`), drop that table (`Student.drop_table`), and `#save` a student to the database.

Now, we will need to create a method that takes a row from the database and turns it back into a Student object. We will call this `.new_from_db`.

Next, we want to build a couple of methods to get information from the database. We will call these `.find_by_name` and `.all`. 

Let's get started!

## Instructions

### The `.new_from_db` Method

This is a class method that accepts a row from the database as an argument. It then creates a new student object based on the information in the row. Remember, our database doesn't store Ruby objects, so we have to manually convert it ourself.

### The `.find_by_name` Method

This is a class method that accepts a name of a student. You will first run a SQL query to run get the result from the database where the student's name matches the name passed into the argument.

Next you will take the result and create a new student instance using the `.new_from_db` method you just created.

### The `.all` Method
This is a class method that is very similar to the `.find_by_name` method. You will not need an argument since we are returning everything in the database. Run the SQL to return everything (`*`) from a table. 

Again, you will use the `.new_from_db` method to create an student instance for each row that comes back from the database. 








