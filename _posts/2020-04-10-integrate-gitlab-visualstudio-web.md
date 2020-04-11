---
toc: true
layout: post
comments: true
author: You Quan
description: A quick guide on how to integrate Gitlab with Microsoft Visual Studio.
categories: [gitlab, visual studio, asp.net, web, programming]
title: 'How To Integrate Gitlab with Microsoft Visual Studio'
---

Under Construction!!!

I have explained in one of my [blog posts](https://you3quan2.github.io/youquan-blog/git/gitlab/ubuntu/clion/c/programming/2020/03/26/setup-git-gitlab-clion-c.html#why-we-need-to-learn-this) on how Gitlab can be a useful tool for a team of software developers to manage a single software project from anywhere on the earth efficiently. However, if you are a student, Gitlab can also be used as your own personal project repositiory, where you can keep track on your programming coursework, and as the same time, use it as a backup. In this short tutorial, we will learn how to integrate Gitlab with Microsoft Visual Studio, where we will synchronise a ASP.NET web project between our personal workstation and Gitlab.

## Requirements
- Microsoft Visual Studio (I am using the 2019 version). See [here](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2019) on how to download and install.
- Gitlab. Create an account [here](https://about.gitlab.com/).

## Creating a Gitlab Project
1. Login to our Gitlab and clik the `New Project` button in the upper right corner of the page.
1. Give a name to our project (e.g. `ASPNetTutorial`) and click on `Create Project`. We can give a description to the project but it is optional.
![]({{ site.baseurl }}/images/blog5_createproject.png)  

1. We will be redirected to the project page. This project should be empty. Click on the down arrow in the `Clone` button and copy the URL under `Clone with HTTPS` and paster it somewhere else (e.g. a text file). We will need this URL later.  
![]({{ site.baseurl }}/images/blog5_giturl.png)  

## Setting Up Gitlab in Microsoft Visual Studio
1. Open/Create a project using Microsoft Visual Studio. If you are not sure how to do this, then please refer to this [link](bit.ly/2x6DLTQ).

1. Once the project is ready, go to the top of the Visual Studio and click on **File** &rarr; **Add to Source Control**. 

1. If we do not have the **Team Explorer** opened, then click on **View** &rarr; **Team Explorer**. Within the **Team Explorer**, we are supposed to see our project is now under the **Local Git Repositories**.  
![]({{ site.baseurl }}/images/blog5_localgit.png)  

## Push our project from Visual Studio to Gitlab
1. Double click on our project under the **Local Git Repositories** and we will get to the **Team Explorer - Home**:  
![]({{ site.baseurl }}/images/blog5_tehome.png)  

1. Click on **Settings** and set up our *User Name* and *Email Address*. This information is used to identify us as the author of the project.  
![]({{ site.baseurl }}/images/blog5_repositorysettings.png)  

1. Go back to **Team Explorer - Home** by clicking on the **Home icon** button. Now, click on **Sync** and go to **Push to Remote Repository**. Key in the URL which we have copied from our Gitlab account earlier (e.g. `https://gitlab.com/you3quan2/aspnettutorial.git`) and click on **Publish**.
![]({{ site.baseurl }}/images/blog5_enterurl.png) 

1. We will be asked to enter the *User name* and *Password* for our Gitlab's account.  
![]({{ site.baseurl }}/images/blog5_pwd.png) 

1. Visit our Gitlab account again and check on the empty project which we have created earlier. We are supposed to see the ASP.NET project which we have created in this Gitlab project's repository.

## Update changes in Visual Studio to Gitlab
Now, we have the exact same project in our Visual Studio and Gitlab. But, we still need to update the Gitlab's project every time we made changes on the project in Visual Studio. I will show you an example how we can do this.

In my `ASPNetTutorial` project, there is a `Home.aspx` file which contains the following codes:
```python
   <%@ Page Title="" Language="C#" MasterPageFile="~/Site1.Master" AutoEventWireup="true" CodeBehind="Home.aspx.cs" Inherits="ASPNetTutorial.Home" %>
<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="ContentPlaceHolder1" runat="server">
    <h2> This is my HOME page. </h2>
</asp:Content>
```

I updated my `Home.aspx` file and adding `(GitLab Test)` to `<h2></h2>`:
```python
   <%@ Page Title="" Language="C#" MasterPageFile="~/Site1.Master" AutoEventWireup="true" CodeBehind="Home.aspx.cs" Inherits="ASPNetTutorial.Home" %>
<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="ContentPlaceHolder1" runat="server">
    <h2> This is my HOME page (GitLab Test). </h2>
</asp:Content>
```
*Note:* You can make changes in any files you like within your project.

To update these changes, I perform the following steps:
1. Go to **Team Explorer - Home** and click on **Changes**. If we have made changes to our project, we will see a list of files which are affected by the changes we made under **Changes**. Under **Branch: master**, key in a commit message (e.g. `Changes made to ome.aspx for Gitlab testing`). Click on **Commit All**.  
![]({{ site.baseurl }}/images/blog5_changecomment.png)  

1. We will see a message as follow. Click on **Sync** so that the changes we have made will be reflected in our Gitlab's project repository.  
![]({{ site.baseurl }}/images/blog5_sync.png)  

Go to the Gitlab account and check on the specific file which we have modified. We are supposed to see the changes which we have made. If we click on the `History` button, we will see our commit changes:  
![]({{ site.baseurl }}/images/blog5_gitlabhistory.png)  

## Takeaways
By now, you should know how to setup your Visual Studio and Gitlab in order to push your project from your workstation to Gitlab.

I hope you found this tutorial helpful. Have more questions about this? Let me know by commenting below!
