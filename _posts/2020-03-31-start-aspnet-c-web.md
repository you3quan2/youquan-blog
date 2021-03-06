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
- Familiarise with the components in Visual Studio, including **Solution Explorer**, **Toolbox**, **Properties** and **Project View**.
- Learn how to to develop a single ASP.NET webpage with Visual Studio.

## Why we need to learn this?
I believe you are here because you want/have to learn [ASP.NET Web Programming](https://dotnet.microsoft.com/apps/aspnet). To learn ASP.NET, we need to use its de facto IDE - [Microsoft Visual Studio](https://visualstudio.microsoft.com/).

My experience tells me that it is always better to start by having a brief tour of the tool which we are going to use in developing a project. By mastering the tools, it is going to save a huge amount of time throughout the learning process.

## Requirements
Microsoft Visual Studio (I am using the 2019 version). See [here](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2019) on how to download and install.

## Create the Project
1. Open our **Visual Studio IDE** and click on:  
  ![]({{ site.baseurl }}/images/blog2_createproject.png)  
  Alternatively, click on **FILE** &rarr; **New Project**.

1. Choose the **ASP.NET Web Application (.NET Framework)**. Make sure it is the **C#** template.  
  ![]({{ site.baseurl }}/images/blog2_createprojectnetframework.png)

1. Configure the project by having a **Project name** and **Solution name**. Take note on the location where the project is going to be saved. The version of the framework which I am using is **.NET Framework 4.7.2**.  Click **Create**.  
![]({{ site.baseurl }}/images/blog2_configureproject.png)  

1. Create a new ASP.NET web application by choosing the **Empty** template. Click **Create** again.  
![]({{ site.baseurl }}/images/blog2_createwebapp.png)  

1. The new project will be opened and the **Solution Explorer** will display the details of this project (my project is **ASPNetTutorial**). That is fine if you cannot find your **Solution Explorer** now, I will give you a tour of Visual Studio in the next section.

## Familiarise with Visual Studio
1. There are four must-know components in Visual Studio: **Solution Explorer**, **Toolbox**, **Properties** and **Project View**. Usually, the **Solution Explorer** will be readily available when we open a project. When we click on the project name in the **Solution Explorer** (mine is **ASPNetTutorial** which highlighted in blue), we will also see the **Project Properties**:
![]({{ site.baseurl }}/images/blog2_newproject.png)  
However, if you cannot see your **Solution Explorer**, go to the top of the Visual Studio and click on **View** &rarr; **Solution Explorer**. 
  
1. To introduce the functionalities of other components, we need to first create an empty web form. Right click on the project's name (mine is **ASPNetTutorial**), then click **Add** &rarr; **Web Form**. Name the item as **Login** because we are going to create a simple Login interface. Now, we are supposed to have a `Login.aspx` file. This file contains basic HTML codes with `<head></head>`, `<form></form>` and `<body></body>`.

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

1. Below the `Login.aspx` file, there is a component which I call it as **Project View**. It allows us to view our project in three different views: **Design**, **Split** and **Source**. Personally, I like **Split** view which provides us with **Source** and **Design** in the same window.
![]({{ site.baseurl }}/images/blog2_projectview.png) 

1. Another important component which we will use frequently is the **Toolbox**. To add this component, go to the top of the Visual Studio and click on **View** &rarr; **Toolbox**. In the **Toolbox**, there are various types of elements which we know as **Controls** in ASP.NET. These controls help to speed up our development process. We will see how **Toolbox** and **Controls** work in the next section.  
![]({{ site.baseurl }}/images/blog2_toolbox.png) 

## Our First ASP.NET Web Page
Now, we are going to familiarise with the components in **Visual Studio** by creating a simple **Login** interface. This **Login** interface will have a *username text box*, a *password textbox* and a *login button*. The text boxes and the button will be placed in a **3 (rows) x 2 (columns)** table:

|Username:    |Username's Textbox  |
|:----------: |:------------------:|
|Password:    |Password's Textbox  |
|Login button |                    |

If you have learnt [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), then you must know the we can manually code the layout presented above using HTML syntax such as `<form></form>`, `<table></table>`, `<tr></tr>`, `<td></td>`, `<input type="text">` and `<input type="submit">`.
 
However, with **Visual Studio**, this layout can be developed with very little manual coding or no manual coding at all.

1. Let's start by adding a **3 (rows) x 2 (columns)** table inside the `<div></div>` tag. Move our mouse cursor inside the `<div>` box:  
![]({{ site.baseurl }}/images/blog2_div.png)  
Go to the top of the **Visual Studio** and click on **Table** &rarr; **Insert Table**. Create a 3 (rows) x 2 (columns) table.

1. Type the text `Username` and `Password` into the designated table cells.

1. We are going to use the **Toolbox** to create our textboxes and button. In the **Toolbox**, select **Standard** &rarr; **TextBox**. Click on the **TextBox**, and drag-and-drop it into the designated `Username's Textbox` cell. Repeat for `Password's Textbox`.

1. To add the Login button, select **Standard** &rarr; **Button**. Click on the **Button**, and drag-and-drop it into the designated `Login button` cell. By now, we should have a layout as follow:  
![]({{ site.baseurl }}/images/blog2_loginv1.png) 

1. Note that the text inside the **Login** button is `Button`. To change the text to `Login`, click on the **Login** button. The **Properties** window of the **Login** button will be shown right below the **Solution Explorer**. Change the `Text` of the button to `LOGIN`.  
![]({{ site.baseurl }}/images/blog2_buttonproperties.png)

1. We can always make changes on this **Login** page by adding or modifying the HTML codes, without using the **Toolbox**. Let say if I want to add a title to this page, I can add the `<h1></h1>` directly to the existing HTML codes:  
    ```python
    <form id="form1" runat="server">
        <div>
            <h1>My First Login Page</h1>
            <table style="width: 100%">
                <tr>
                    <td>Username:</td>
                ... other codes here ....
                </tr>
            </table>
        </div>
    </form>
    ```  
    
    Every time we make changes to the code, a warning message *Design view is out of sync with Source view. Click here to synchronize views will be displayed*. Click on the message and we will see the changes we made reflected in the **Design view**.
    
1. Now, let's try to run the project and check if everything is working as intended. By default, we will see a green arrow and IIS Express (Microsoft Edge) on top of our Microsoft Visual Studio. Personally, I prefer to run everything in Google Chrome. To change the default setting, click on the down arrow and select Google Chrome (if you have Google Chrome installed). 
![]({{ site.baseurl }}/images/blog2_runproject.png) 

1. Click on `IIS Express (Google Chrome)`. Google Chrome will open shortly with our very first Login page developed using ASP.NET:  
![]({{ site.baseurl }}/images/blog2_firstloginpage.png) 

## Best Practices 
There are many best coding practices (which you can read [here](https://en.wikipedia.org/wiki/Best_coding_practices)). But, I just want to focus on one of these practices in this tutorial - **Naming conventions**. Using meaningless naming can cause confusion to reduce the readability of our codes. Take our Login page for example, if we browse through these HTML codes, we will notice some meaningless naming as follow:

```python
<form id="form1" runat="server">
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox>
<asp:Button ID="Button1" runat="server" Text="LOGIN" />
```

The names which are automatically assigned to the HTML elements by Visual Studio can cause confusion, especially when our web project grows bigger. Hence, it is always a good practice to replace these IDs with meaningful names:
```python
<form id="login_form" runat="server">
<asp:TextBox ID="username_txtbox" runat="server"></asp:TextBox>
<asp:TextBox ID="pwd_txtbox" runat="server"></asp:TextBox>
<asp:Button ID="login_button" runat="server" Text="LOGIN" />
```
Note that we can change these names by modifying the HTML codes directly, or by changing the properties of these controls (e.g. button, textbox) via the **Properties** window.

## Takeaways
I hope by now:
- You know how to use Visual Studio along with its components: **Solution Explorer**, **Toolbox**, **Properties** and **Project View**.
- You are confident to create a single ASP.NET web page with Visual Studio (e.g. a login page, a form).

Coming up next, we will learn:
- How to create a Master page for a multiple pages web site in ASP.NET. (Click [here](https://you3quan2.github.io/youquan-blog/visual%20studio/asp.net/master%20page/web/programming/2020/04/07/create-masterpage-aspnet-web.html) for the tutorial)

I hope you found this tutorial helpful! If you have more questions about this tutorial, please let me know by commenting below.
