---
toc: true
layout: post
comments: true
author: You Quan
description: A tutorial to create Master Page in ASP.NET.
categories: [visual studio, asp.net, master page, web, programming]
title: 'Creating Master Page in ASP.NET'
---

## Learning Outcomes
In this tutorial, we will:
- Learn how to create a Master page for a multiple pages web project in ASP.NET.
- Expose to basic web page design using Bootstrap, with focus on navigation menu.

## Prerequisite
If you are new to ASP.NET, I suggest you to look into this [tutorial](https://you3quan2.github.io/youquan-blog/visual%20studio/asp.net/c%23/web/programming/2020/03/31/start-aspnet-c-web.html) to learn how to create a ASP.NET web project with Microsoft Visual Studio.

## Why we need to learn this?
I believe you have know learn how to create a single ASP.NET web page. However, in real life, a web application is made up from multiple web pages. Take Twitter as example:
![]({{ site.baseurl }}/images/blog3_twitterpages.png)  

If we visit our Twitter page, we can see links to multiple pages (e.g. Home, Explore, Notification, Messages etc.) on the left hand side of the page. We call it as navigation bar, which helps us to navigate from one page to another. When we browse from the Home page to the Explore page, the navigation bar remain the same, and only a specific portion of the web page changed.

Hence, it is impractical if we are going to write the codes for the navigation bar in every single web pages within our web application. ASP.NET offers us a solution - the Master Page. By using the Master page, we will only need to code the standard layout in the `Site.Master`, and this will be implemented into the rest of the pages within our web application.

## Requirements
Microsoft Visual Studio (I am using the 2019 version). See [here](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2019) on how to download and install.

## Introduction to Web Layout and the Sitemap
Microsoft Visual Studio (I am using the 2019 version). See [here](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?v
1. To introduce the functionalities of other components, we need to first create an empty web form. Right click on the project's name (mine is **ASPNetTutorial**), then click **Add** &rarr; **Web Form**. Name the item as **Login** because we are going to create a simple Login interface. Now, we are supposed to have a `Login.aspx` file. This file contains basic HTML codes with `<head></head>`, `<form></form>` and `<body></body>`.

    ```python
    <%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site1.master.cs" Inherits="ASPNetTutorial.Site1" %>

    <!DOCTYPE html>

    <html>
    <head runat="server">
        <title></title>
        <asp:ContentPlaceHolder ID="head" runat="server">
        </asp:ContentPlaceHolder>
    </head>
    <body>
        <form id="form1" runat="server">
            <div>
                <asp:ContentPlaceHolder ID="ContentPlaceHolder1" runat="server">
                </asp:ContentPlaceHolder>
            </div>
        </form>
    </body>
    </html>
    ```

## Why we need to learn this?



I believe you are here because you want/have to learn [ASP.NET Web Programming](https://dotnet.microsoft.com/apps/aspnet). To learn ASP.NET, we need to use its defacto IDE - [Microsoft Visual Studio](https://visualstudio.microsoft.com/).

My experience tells me that it is always better to start by having a brief tour on the tool which we are going to use in developing a project. By mastering the tools, it is going to save a huge amount of time throughout the learning process.




1. Bel
