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

## Why we need to learn this?
I believe you are here because you want/have to learn [ASP.NET Web Programming](https://dotnet.microsoft.com/apps/aspnet). To learn ASP.NET, we need to use its defacto IDE - [Microsoft Visual Studio](https://visualstudio.microsoft.com/).

My experience tells me that it is always better to start by having a brief tour on the tool which we are going to use in developing a project. By mastering the tools, it is going to save a huge amount of time throughout the learning process.

## Prerequiste

## Requirements
Microsoft Visual Studio (I am using the 2019 version). See [here](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2019) on how to download and install.

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

1. Bel
