---
toc: true
layout: post
comments: true
author: You Quan
description: A tutorial to create a Master Page in ASP.NET.
categories: [visual studio, asp.net, master page, web, programming]
title: 'Creating a Master Page in ASP.NET'
---

## Learning Outcomes
In this tutorial, we will:
- Learn what is a web page layout and a sitemap.
- Learn how to create a Master page for a multiple pages web site in ASP.NET.
- Learn how to use Bootstrap to design the Master page, with focus on the navigation bar.

## Prerequisite
If you are new to ASP.NET, I suggest you to look into this [tutorial](https://you3quan2.github.io/youquan-blog/visual%20studio/asp.net/c%23/web/programming/2020/03/31/start-aspnet-c-web.html) to learn how to create a ASP.NET web project with Microsoft Visual Studio.

## Why we need to learn this?
I believe you have know learn how to create a single ASP.NET web page. However, in real life, a web site is made up from multiple web pages. Take Twitter as example:
![]({{ site.baseurl }}/images/blog3_twitterpages.png)  

If we login to our Twitter account, we can see a menu on the left hand side of the page. We call it as navigation bar, which helps us to navigate throughout the web site (e.g. from **Home** page to the **Explore** page). Everytime we browse from one page to another, the navigation bar remain the same, and only a specific portion of the web page changed.

Hence, it is impractical if we write the codes for the navigation bar in every single web pages within our web site, and change each pages manually everytime we change the design of our web site. ASP.NET offers us a solution - the **Master Page**. By using the Master page, we will only need to code the standard layout in the `Site.Master`, and this will be implemented to the rest of the pages within our web site.

## Requirements
1. Microsoft Visual Studio (I am using the 2019 version). See [here](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2019) on how to download and install.
1. Bootstrap package

## A Web page Layout
Let's start by understanding the basic concept of the layout of a web page. The sample below shows a web page which has five regions: **Header**, **Content**, **Advertisement**, **Recommended Book** and **Footer**.
![]({{ site.baseurl }}/images/blog3_webpagelayout.png) 

For the sake of simplicity, we will focus only on three regions: **Header**, **Content** and **Footer**. Recall the example of the Twitter page discussed above, a web application usually has the same **Header** and **Footer** across all pages. The **Content** is the region where the unique content for each individual web page is located.

Hence, we will define the **Header** and **Footer** region in our ASP.NET Master page and create the unique content in the rest of the web pages within the same web application.

## The Sitemap
Before we start to develop our web site, we need to first have a [sitemap](https://en.wikipedia.org/wiki/Site_map) , which lists all the web pages in the web site and how these pages are interrelate. Just like the Twitter web site above which has pages like **Home** page, **Explorer** page, **Profile** page, now we are going to create a sitemap for our own web site.

Our web site, which I known as **ASP.NET Tutorial** website has the following web pages:
- Home page
- Profile page
- Contact
  - Web Chat page
  - Online Enquiry page

The sitemap above shows that we have four web pages: **Home**, **Profile**, **Web Chat** and **Online Enquiry** page. Note that in this example, we do not have a page for **Contact**. The users can directly access the **Web Chat** page and **Online Enquiry** page, which are categorised under **Contact**. 

By now, we can have a rough idea that our website is going to look something like the one below:
![]({{ site.baseurl }}/images/blog3_webpagelayout.png) 

- Header region (with a navigation bar, which created based on our sitemap)
- Content region (a simple text which indicates what page it is)
- Footer region (website's info, copyright etc.)

## Create a Masterpage with ASP.NET
*Note*: We can still use the **ASP.NetTutorial** project which we have created in the previous tutorial.

1. Right click on the project (e.g. **ASP.NetTutorial**) and select **Add** &rarr; **New Item**. Under **Web**, select **Web Forms** and then click on **Web Forms Master Page**. We can specifiy the name for the Master page. I maintain its default name - `Site1`.
![]({{ site.baseurl }}/images/blog3_masterpage.png)  
A `Site1.Master` page will be created automatically with the codes as follow:  

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
    
1. Next, we create the rest of the pages in our web site. Right click on the project (e.g. **ASP.NetTutorial**) and select **Add** &rarr; **New Item**. Under **Web**, select **Web Forms** and then click on **Web Form with Master Page**. Name these web pages as `Home.aspx`, `Profile.aspx`, `WebChat.aspx` and `EnquiryForm.aspx` respectively. We will be asked to select the Master page for each of the web pages we created. In this case, we need to select `Site1.Master`, which is the Master page which we have created earlier.
![]({{ site.baseurl }}/images/blog3_selectmasterpage.png)  

Note that the web page which we have created only a few lines of codes as follow:

    ```python
    <%@ Page Title="" Language="C#" MasterPageFile="~/Site1.Master" AutoEventWireup="true" CodeBehind="Home.aspx.cs" Inherits="ASPNetTutorial.Home" %>
    <asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
    </asp:Content>
    <asp:Content ID="Content2" ContentPlaceHolderID="ContentPlaceHolder1" runat="server">
    </asp:Content>
    ```


