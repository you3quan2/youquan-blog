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
The Login page is an essential part for a web site. It helps to ensure that only the authenticated users will have access to our web site. In this tutorial, we are going to adopt a traditional approach in developing a functional Login page, where we will create almost everything from scratch. 

I know many of you may question WHY we need to do this since we can easily create a Login page using a readily available [Login class](https://docs.microsoft.com/en-us/dotnet/api/system.web.ui.webcontrols.login?view=netframework-4.8) or the [ASP.NET MVC framework](https://docs.microsoft.com/en-us/aspnet/mvc/overview/security/create-an-aspnet-mvc-5-web-app-with-email-confirmation-and-password-reset). In fact, using the Login class and ASP.NET results in a more secure web application.

However, I found that creating a simple Login page from scratch is a perfect working example for us to learn about ASP.NET web programming with C#. Using the Login class or ASP.NET MVC framework might help us to accomplish the task quickly (which is best for a professional software developer). But, if we want to learn, then I believe we need to start from the basic to build a stronger foundation.

By working on this simple Login page, we will learn how to connect and retrieve data from the database. We will also learn how to use C# to manipulate this data. Finally, this simple Login page provides us with some examples of the design and security flaws in a web site, and we will then learn how to fix these flaws in the upcoming tutorials.

## Adding ASP.NET Controls in the Login page
I see **Control** as a useful feature in ASP.NET which helps us to speed up our web development process. Of course, it also provides a more structured programming model for the web site. We are going to add three controls (two **Label** controls and one **SQL Data Source** control) in our Login page:  
![]({{ site.baseurl }}/images/blog7/blog7_dslbl.png)  

{% include info.html text="Make sure you are in the <b>Split</b> mode so that you can see both your design and codes." %}

1. To add a Control, first open the **Toolbox** by selecting **Add** &rarr; **Toolbox**. Under **Data**, select **SqlDataSource**. Drag-and-drop it to the area under the **LOGIN** button. This control represents a connection to a database, which we will define later. 

1. Next, go to **Standard** and click on **Label**. Drag-and-drop it right to the *Username* textbox. Add another label for the *Password* textbox. We will use these labels to display the error message if an user enters the incorrect user name or password.

1. Once we have added the labels, we will notice that in our ASP.NET codes, a new line of code is added under each of the text box:  
    ```python
    <asp:TextBox ID="username_txtbox" runat="server"></asp:TextBox>
    <asp:Label ID="Label1" runat="server" Text="Label"></asp:Label>
    ```  
1. Now, we are going to modify the properties for label which is beside the *Username* textbox. There are two ways we can do this. First, modify the codes above directy or change the Label's properties through the Properties window. For the first method, we can update the codes as follow:  
    ```python
    <asp:TextBox ID="username_txtbox" runat="server"></asp:TextBox>
    <asp:Label ID="username_msg" Visible="false" runat="server" Text=""></asp:Label>
    ```  
    
    For the second method, we just need to click on the Label in Design model and update the properties through the Properties window:  
    ![]({{ site.baseurl }}/images/blog7/blog7_llbprop.png) 
    
    The three properties which we have udpated are:  
    - Text: The text to be shown for the label (We change it to "" as no error message is required when user first visit the Login page)
    - Visible: Indicates whether the label is visible (We set it to false so the label is not visible when user first visit the Login page)
    - ID: Programmatic name of the label (We change it to username_msg for the Username's label for better readability of the codes)

1. Repeat the step above for the 
    

