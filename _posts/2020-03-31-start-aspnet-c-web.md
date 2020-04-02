---
toc: true
layout: post
comments: true
author: You Quan
description: A tutorial to familiarise with Visual Studio to learn ASP.NET web programming with C#.
categories: [visual studio, asp.net, c#, web, programming]
title: 'Getting Started: ASP.NET Web Programming with C#'
---

## Learning Outcomes
In this tutorial, we will:
- Learn how to to setup a one-page ASP.NET web application with Visual Studio.
- Familiarise with the components in Visual Studio, including **Solution Explorer**, **Toolbox**, **Properties** and **Project View**.

## Why we need to learn this?
I believe you are here because you want to learn ASP.NET Web Programming, and Microsoft Visual Studio is the tool which you must learn how to use as it is the defacto IDE for ASP.NET. My experience tells me that it is always better to start by having a brief tour on the tool which we are going to use in developing a project. It is going to save a huge amount of time throughout our learning process later on. We can save the questions like: *Where is my toolbox?*, *Where is my button's properties?* etc.

## Requirements
Microsoft Visual Studio (I am using the 2019 version). See [here](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2019) on how to download and install.

## Create the Project
1. Open our Visual Studio IDE and click on:  
  ![]({{ site.baseurl }}/images/blog2_createproject.png)  
  Alternatively, click on **FILE** &rarr; **New Project**.

1. Choose the ASP.NET Web Application (.NET Framework). Make sure it is the C# template.  
  ![]({{ site.baseurl }}/images/blog2_createprojectnetframework.png)

1. Configure the project by having a **Project Name** and **Solution name**. Take note on the location where the project is going to be saved. The version of framework which I am using is **.NET Framework 4.7.2**.  Click **Create**.  
![]({{ site.baseurl }}/images/blog2_configureproject.png)  

1. Create a new ASP.NET web application by choosing the **Empty** template. Click **Create** again.  
![]({{ site.baseurl }}/images/blog2_createwebapp.png)  

1. The new project will be opened and the **Solution Explorer** will display the details of this project (my project is **ASPNetTutorial**). That is fine if you cannot find your **Solution Explorer** now, we will give you a tour on Visual Studio in the next section.

## Familiarise with Visual Studio
1. There are five must-know components in Visual Studio: **Solution Explorer**, **Toolbox**, **Properties** and **Project View**. Usually, we will have the Solution Explorer when a project is opened:  
![]({{ site.baseurl }}/images/blog2_newproject.png)  
However, if you cannot see your **Solution Explorer**, go to the top of the Visual Studio and click on **View** &rarr; **Solution Explorer**.
  
1. To introduce the functionalities of others components, we need to first create an empty web form. Right click on the project name in the **Solution Explorer** (mine one is **ASPNetTutorial** which highlighted in blue, see figure above), then click **Add** &rarr; **Web Form**. Give the item the name **Login** as we are going to create a simple Login interface. Now, we are supposed to have a `Login.aspx`  file as follow:

```python
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Login.aspx.cs" Inherits="ASPNetTutorial.Login" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
    </form>
</body>
</html>
```







