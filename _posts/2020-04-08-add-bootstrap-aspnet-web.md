---
toc: true
layout: post
comments: true
author: You Quan
description: A quick guide on how to add Bootstrap in ASP.NET.
categories: [visual studio, asp.net, Bootstrap, web, programming]
title: 'How To Add Bootstrap In ASP.NET'
---


Follow the steps below to add Bootstrap to our ASP.NET web project:
1. In the Solution Explorer, right click on the project (e.g. **ASPNetTutorial) and select **Manage NuGet Packages**.  
![]({{ site.baseurl }}/images/blog4_managenuget.png)  

1. Under the NuGet window, click on Browse and search for Bootstrap using the Search. Once we get the Bootstrap package , click on &darr; to add the package ro our web project.  
![]({{ site.baseurl }}/images/blog4_installbs.png)  

1. We will be asked to confirm installation, where the following files will be added into our web project:  
   - jQuery.3.0.0
   - popper.js.1.16.0
   - bootstrap.4.4.1  
![]({{ site.baseurl }}/images/blog4_preview.png)  

1. If the installation is successful, we will see multiple files (.css, map, .js) aaded to the **Content** and **Scripts** folder under our web project.  
![]({{ site.baseurl }}/images/blog4_newfiles.png)  

1. Drag and drop these three specific files from the **Content** and **Scripts** into the `<head></head>` section of the web page where we want to code with Bootstrap.
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
