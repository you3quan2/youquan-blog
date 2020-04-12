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
Almost all web sites involve a database. If you have just signed up a new Twitter account, where is the information about your account will be stored? Yes, the database! Hence, if we want to learn how to develop a web application, then we must also learn about the database. 

## Basic Concepts of Database
In simple words, database is made up from one or more tables, and a table consists of one or more rows and columns. Assume that we have a web site which have multiple registered users, and each user has their own username, password and role (e.g. admin, normal user). Then, we can have the user information stored in a table as follow:

|user_id |username |password |role  |
|:-----: |:-------:|:-------:|:----:|
|YQ01    |yquan    |abc123   |admin |

### Data Types
When creating this table, we also need to specific the type of data which can be stored in each columns. For example, we can assign the data type for nchar(10) for the username column, which indicates the username column can only store a fixed maximum length of 10 characters. There are a few other data type which we commonly used, such as datetime to store data and time; int to store an integer; decimal to store decimal digits. You can refer to [this link](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql-server-data-type-mappings) to retrieve a comprehensive list of data types available.

### Primary Key and Foreign Key



