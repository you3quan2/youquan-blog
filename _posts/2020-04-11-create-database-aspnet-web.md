---
toc: true
layout: post
comments: true
author: You Quan
description: A tutorial to create a simple database in ASP.NET.
categories: [visual studio, asp.net, master page, web, programming]
title: 'Creating a Simple Database in ASP.NET'
---

# This page is still under construction!

## Learning Outcomes
In this tutorial, we will:
- Learn what is a database along with some simple concepts such as data type, primary key and foreign key.
- Learn how to create a database for an ASP.NET project using Microsoft Visual Studio.

## Why we need to learn this?
Almost all web sites involve a database. If you have just signed up a new [Twitter](https://twitter.com/Twitter) account, where is the information about your account will be stored? Yes, the database! Running a web site involves the operation of inserting, retrieving, updating and deleting data from the database. Hence, if we want to learn how to develop a web application, then we must also learn about the database. 

## Basic Concepts of Database
In simple words, a database is made up of one or more tables, and a table consists of one or more rows and columns. Assume that we have a web site which has multiple registered users, and each user has their username, password and role (e.g. *admin*, *normal user*). Then, we can have the user information stored in a table as follow:

|user_id |username |password |role  |
|:-----: |:-------:|:-------:|:----:|
|YQ01    |yquan    |abc123   |admin |

### Data Types
When creating this table, we also need to specify the type of data which can be stored in each column. For example, we can assign the data type `nchar(10)` for the **username** column, which indicates the **username** column can only store a fixed maximum length of 10 characters. There are a few other data types which we commonly used, such as `datetime` to store data and time; `int` to store an integer; `decimal` to store decimal digits. You can refer to [this link](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql-server-data-type-mappings) to access a comprehensive list of data types.

### Primary Key and Foreign Key
In the table presented above, we define the `user_id` as our primary key. In database, a primary key consists of one or more columns whose data contained within is used to uniquely identify each row in the table. In our example above, the `user_id` **YQ01** is exclusive for that specific role, and no other rows within the same table should have this same `user_id`.


https://www.essentialsql.com/what-is-the-difference-between-a-primary-key-and-a-foreign-key/

The primary key consists of one or more columns whose data contained within is used to uniquely identify each row in the table.  You can think of them as an address.  If the rows in a table were mailboxes, then the primary key would be the listing of street addresses.

When a primary key is composed of multiple columns, the data from each column is used to determine whether a row is unique.

In order to be a primary key, several co



