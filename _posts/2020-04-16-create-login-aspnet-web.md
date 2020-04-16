---
toc: true
layout: post
comments: true
author: You Quan
description: A tutorial to create a simple login page using ASP.NET and C#.
categories: [visual studio, asp.net, login, C#, web, programming]
title: 'Creating a Simple Login Page using ASP.NET and C#'
---

# This page is still under construction!!!

## Learning Outcomes
In this tutorial, we will:
- Learn how to create a functional login page using ASP.NET and C#.
- Learn how to establish connection to a database.
- Learn how to manipulate data using C#.

## Prerequisite
This tutorial is based on the Login page and the database which we have created in the previous tutorial. Please refer to:
- Getting Started: ASP.NET Web Programming with C#
- Creating a Simple Database in ASP.NET

I will suggest you to look into the tutorial on xxxx.

## Why do we need to learn this?
Almost all web sites involve a database. If you have just signed up a new [Twitter](https://twitter.com/Twitter) account, where is the information about your account will be stored? Yes, the database! Running a web site involves the operation of inserting, retrieving, updating and deleting data from the database. Hence, if we want to learn how to develop a web application, then we must also learn about the database. 

A **foreign key (FK)** is a key used to link two tables together. It is one or more columns in a table that refers to the primary key in another table. To better explain this, I split our table above into two tables (*User* and *Role*):
![]({{ site.baseurl }}/images/blog6_pkfk.png)  

*role_id* is a primary key in the *Role* table. The same key acts as a *foreign_key* in the *User* table which established a link between the *User* table and the *Role* table. You may question why it is necessary to split the *User* table into two. 

Now, imagine our web site has an interface which allows the web admin to manage (e.g. update, delete) the role of the users. If the admin decides to add a new role (e.g. super admin), how the one *User* table can be updated? We cannot insert a new role into this *User* table without a *user_id* because *user_id* is the primary key of this table and cannot be left null. If we have a *Role* table, then we can easily add or delete a role by updating only the *Role* table.

You can refer to this [link](https://softwareengineering.stackexchange.com/questions/375704/why-should-i-use-foreign-keys-in-database) to read the discussions about *Why should I use foreign keys in database?*.
