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

## Prerequisite
If you are new to ASP.NET, I suggest you to look into this [tutorial](bit.ly/2x6DLTQ) to learn how to create an ASP.NET web project with Microsoft Visual Studio.

## Why we need to learn this?
Almost all web sites involve a database. If you have just signed up a new [Twitter](https://twitter.com/Twitter) account, where is the information about your account will be stored? Yes, the database! Running a web site involves the operation of inserting, retrieving, updating and deleting data from the database. Hence, if we want to learn how to develop a web application, then we must also learn about the database. 

## Basic Concepts of Database
In simple words, a database is made up of one or more tables, and a table consists of one or more rows and columns. Assume that we have a web site which has multiple registered users, and each user has their username, password and role (e.g. *admin*, *normal user*). Then, we can have the user information stored in a *User* table as follow:

|user_id |username |password |role  |
|:-----: |:-------:|:-------:|:----:|
|YQ01    |yquan    |abc123   |admin |

### Data Types
When creating this table, we also need to specify the type of data which can be stored in each column. For example, we can assign the data type `nchar(10)` for the **username** column, which indicates the **username** column can only store a fixed maximum length of 10 characters. There are a few other data types which we commonly used, such as `datetime` to store data and time; `int` to store an integer; `decimal` to store decimal digits. You can refer to [this link](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql-server-data-type-mappings) to access a comprehensive list of data types.

### Primary Key and Foreign Key
A **primary key (PK)** is one or more columns which can uniquely represent each row in a table. In our example above, the `user_id` **YQ01** is exclusive for that specific row, and no other rows within the same table have this same `user_id`. It is very similar to your *Student ID* or *Staff ID*, where no one have the same ID as yours. Note that a table can contain only one primary key (which can be one or more columns) and these columns cannot be left null (a.k.a empty).

A **foreign key (FK)** is a key used to link two tables together. It is one or more columns in a table that refers to the primary key in another table. To better explain this, I split our table above into two tables (*User* and *Role*):
![]({{ site.baseurl }}/images/blog6_pkfk.png)  

*role_id* is primary key in the *Role* table. The same key acts as a *foreign_key* in the *User* table which established a link between the *User* table and the *Role* table. You may question why it is necessary to split the *User* table into two. 

Now, imagine our web site has an interface which allows admin to manage (e.g. update, delete) the role of the users. If the admin decides to add a new role (e.g. super admin), how the one *User* table can be updated? Note that we cannot insert a new role without the user record into this *User* table because *user_id* is the primary key of this table and cannot be left null. If we have a *Role* table, then the role updating task becomes easier as we only need to update the *Role* table whenever the admin adds or deletes a role.

You can refer to this [link](https://softwareengineering.stackexchange.com/questions/375704/why-should-i-use-foreign-keys-in-database) to read the discussions about *Why should I use foreign keys in database?*.

## Creating a Database in ASP.NET
Let's start to create our first database in ASP.NET using Microsoft Visual Studio.
1. In the **Solution Explorer**, right click on the project (e.g. **ASP.NetTutorial**) and select **Add** &rarr; **New Item**. Under **Visual C#**, click on **Data** and select **SQL Server Database**. Change the name of the database to `aspnettutorial.mdf` and click **Add**. `.mdf` stand for **M**aster **D**atabase **F**ile and it is the primary database file of Microsoft SQL Server.  
![]({{ site.baseurl }}/images/blog6_createdb.png)  

1. We are supposed to get a confirmation message as follow. Click **Yes**.  
![]({{ site.baseurl }}/images/blog6_confirmmsg.png)  

1. Go to the top of Visual Studio and click **View** &rarr; **Server Explorer**. The `aspnettutorial.mdf` will appeared under **Data Connection**.  
![]({{ site.baseurl }}/images/blog6_serverexplorer.png)  

## Creating Tables in the Database
Now, we are going to add tables into the database. We will stick with the example above by having two tables: the *User* table and the *Role* table.

1. In **Server Explorer**, go to the **Table** folder under `aspnettutorial.mdf`. Right click on the folder and select **Add New Table**. A design surface for the table will be shown. Rename the table by updating the following line `CREATE TABLE [dbo].[User]` under the **T-SQL** tab. Next, add the following columns into the table, and make sure we get the right data types for these columns:  
   - user_id (*nchar(10)*)
   - username (*nchar(10)*)
   - password (*nvarchar(MAX)*)  
   - role_id (*int*)  
  ![]({{ site.baseurl }}/images/blog6_usertable.png)  
  
1. By following the guidance provided above, create the *Role* table which has the following columns:  
   - role_id (*int*)
   - role_name (*nchar(10)*)  
  ![]({{ site.baseurl }}/images/blog6_roletable.png)  

## Setting the Keys for Tables
There are two primary keys () and one foreign key in the User and Role table. 

CONSTRAINT [FK_User_Role] FOREIGN KEY ([role_id]) REFERENCES [Role]([role_id]) 


CONSTRAINT [FK_User_Role] FOREIGN KEY ([role_id]) REFERENCES [Role]([role_id]) 


```python
   <%@ Page Title="" Language="C#" MasterPageFile="~/Site1.Master" AutoEventWireup="true" CodeBehind="Home.aspx.cs" Inherits="ASPNetTutorial.Home" %>
<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="ContentPlaceHolder1" runat="server">
    <h2> This is my HOME page (GitLab Test). </h2>
</asp:Content>
```

1. 
