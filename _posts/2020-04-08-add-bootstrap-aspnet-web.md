---
toc: true
layout: post
comments: true
author: You Quan
description: A quick guide on how to add Bootstrap in ASP.NET.
categories: [visual studio, asp.net, Bootstrap, web, programming]
title: 'How To Add Bootstrap In ASP.NET'
---

If you have learn basic web design, then you must know about [Cascading Style Sheets](https://www.w3schools.com/css/) (CSS). Commonly, your web project will have a `.css` file, which defines the design of your web pages. For example, if we want to have a button with green background like this: ![]({{ site.baseurl }}/images/blog4_successbtn.png?display=inline-block), we need to have a `.css` file which defines the style of the button[^1]:
```css
.button {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}
```

However, the task of creating a button like this can be simplified with the use of [Bootstrap](https://getbootstrap.com/). **Bootstrap** is a free and open-source CSS framework which contains CSS-based and [JavaScript](https://www.w3schools.com/js/)-based design templates for various interface components, including the button which we want to create. For example, with Bootstrap, we just need to define the class (e.g. `btn-success`) of the button in our `.html` page (or `.aspx` for **ASP.NET**):

```html
<button type="button" class="btn btn-success">Success</button>
```

The [Bootstrap documentation](https://getbootstrap.com/docs/4.4/getting-started/introduction/) provides a comprehensive guide for us to create almost all the design which we can think of.

To unleash the power of **Bootstrap** in our **ASP.NET** web application, we can add **Bootstrap package** to our **ASP.NET** web project by following these steps:
1. In the **Solution Explorer**, right click on the project (e.g. **ASPNetTutorial) and select **Manage NuGet Packages**.  
![]({{ site.baseurl }}/images/blog4_managenuget.png)  

1. Under the **NuGet** window, click on **Browse** and search for *Bootstrap* using the **Search**. Once we get the **Bootstrap** package , click on **&darr**; to add the package to our web project.  
![]({{ site.baseurl }}/images/blog4_installbs.png)  

1. We will be asked to confirm the installation, where the following files will be added into our web project:  
   - jQuery.3.0.0
   - popper.js.1.16.0
   - bootstrap.4.4.1  
  ![]({{ site.baseurl }}/images/blog4_preview.png)  

1. If the installation is successful, we will see multiple files (`.css`, `.map`, `.js`) aaded to the **Content** and **Scripts** folder under our web project.  
![]({{ site.baseurl }}/images/blog4_newfiles.png)  

1. Drag and drop these three specific files from the **Content** and **Scripts** into the `<head></head>` section of the web page where we want to code with **Bootstrap** (I have added it to the `Login.apsx` which we have created in the very first [tutorial](https://you3quan2.github.io/youquan-blog/visual%20studio/asp.net/c%23/web/programming/2020/03/31/start-aspnet-c-web.html).
   - bootstrap.min.css
   - jquery-3.0.0.min.js
   - bootstrap.min.js

    ```python
    <html>
    <head runat="server">
        <title></title>

        <link href="Content/bootstrap.min.css" rel="stylesheet" />
        <script src="Scripts/jquery-3.0.0.min.js"></script>
        <script src="Scripts/bootstrap.min.js"></script>
    
    </head>
    <body>
        ...other codes...
    </body>
    </html>
    ``` 

1. To check if we have added the **Bootstrap** correctly, run the web project and we should be able to spot the differences in the Login page:  
![]({{ site.baseurl }}/images/blog4_comparebs.png)  

1. If the differences (e.g. *font* and *size*) are not obvious for you, let's add a **Boostrap** class to the **Login** button:

    ```python
    <asp:Button ID="login_button" class="btn btn-outline-danger" runat="server" Text="LOGIN" />
    ```  
    Now, run the project again and hopefully you can notice how the design of the **Login** button had changed:  
    ![]({{ site.baseurl }}/images/blog4_dangerbtn.png) 

If you want to explore more about ASP.NET, I will recommend you to refer to [this tutorial](https://you3quan2.github.io/youquan-blog/visual%20studio/asp.net/master%20page/web/programming/2020/04/07/create-masterpage-aspnet-web.html), which shows you how to create a Master page in ASP.NET and develop a navigation bar for the Master page using Bootstrap.

I hope you found this quick guide helpful! If you have more questions about this tutorial, please let me know by commenting below.
