---
toc: true
layout: post
description: A tutorial on how to setup Git and Gitlab on Linux Ubuntu.
categories: [git, gitlab, ubuntu, clion, c, programming]
title: Setting Up Git and Gitlab on Linux Ubuntu
---

## Learning Outcomes

In this tutorial, we will learn:
- How to setup Git in our Linux workstation.
- How to push C codes from our workstation to our Gitlab's repository.

## Requirements
- Ubuntu (Mine is 18.04.4 LTS, check yours with the command `cat /etc/os-release`)
- CLion (An IDE for C++ and C by JetBrains)
- Git. It can be installed using the following commands:
```shell
sudo apt-add-repository ppa:git-core/ppa
sudo apt-get update
sudo apt-get install git
```
- xclip for retrieving SSH keys. To install xclip, we can run:
```shell
sudo apt install xclip
```
- Gitlab - Create an account [here](https://about.gitlab.com/)

Once we have all these ready, then we are good to go!

## Setting up Git
First, check if we have Git installed by typing the following command in our terminal:
```shell
Git version
```

The command tells us which Git version we have on our workstation. If you don't receive a `Git version` message, it means that you need to install Git (check on the `Requirements` section). Next, we need to configure our Git username and email address, since every Git commit will use this information to identify us as the author.

Add our Git username and email by using the following commands:
```shell
git config --global user.name "[your_username]"
git config --global user.email "[your_email_address]@[yourdomain].com"
```

## Generating a SSH key pair for our Gitlab account
Open a new terminal on Linux and generate a new ED25519 SSH key pair:
```shell
ssh-keygen -t ed25519 -C "[your_email_address]@[yourdomain].com"
```

ED25519 is the most recommended public-key algorithm available today! You can read more about it [here](https://medium.com/risan/upgrade-your-ssh-key-to-ed25519-c6e8d60d3c54).

We will be asked to input a file path to save our SSH key pair and a passphrase to secure our new SSH key pair. Both of these can be ignore by pressing `ENTER`. If we did this correctly, we will get multiple messages, telling us where our identification and public key have been saved. We will also get our key fingerprint and our key's randomart image.

```shell
Your identification has been saved in ~/.ssh/id_ed25519.
Your public key has been saved in ~/.ssh/id_ed25519.pub.
The key fingerprint is:
SHA256:XXX [your_email_address]@[yourdomain].com
The key's randomart image is:
+--[ED25519 256]--+
|     .*=XXo      |
|     .oOO=o      |
|     .+o+o       |
|   .o..=o.       |
|  E o*.oS.       |
|   .+.+ .        |
|  . o=           |
|.+ o.o.          |
|* o++..          |
+----[SHA256]-----+
```

## Adding our SSH key pair into the Gitlab account
To retrieve our SSH key pair, we first need to save the key pair into a text file using xclip:
```shell
xclip -sel clip < ~/.ssh/id_ed25519.pub -o > ~/gitlabsshkeypair.txt
```

Now, add the SSH key pair into our Gitlab account by following these steps:
1. Open the `gitlabsshkeypair.txt` and copy our SSH key pair.
1. Open the Gitlab account in a browser, click the Gitlab avatar in the upper right corner and select Settings.
1. Navigate to `SSH Keys` and paste the SSH key pair which we have copied to the `Key` field.
1. Fill in the `Title` text box. It can be anything we like. We can leave the `Expires at` text box empty.
1. Click the `Add key` button.

## Testing that everything is set up correctly
Let's test if everything is set up correctly by typing the following line into our terminal:
```shell
ssh -T git@gitlab.com
```

Since it is the first time we connect to Gitlab via SSH, we will be asked to verify the authenticity of the GitLab host we are connecting to. We are supposed to get a message as follow:
```shell
The authenticity of host 'gitlab.com (xxx.xxx.xxx.xxx)' can't be established.
ECDSA key fingerprint is SHA256:XXXX.
Are you sure you want to continue connecting (yes/no)? 
```

Type `yes`. We will get a warning message followed by a welcome message:
```shell
Warning: Permanently added 'gitlab.com (xxx.xxx.xxx.xxx)' (ECDSA) to the list of known hosts.
Welcome to GitLab, [your_Gitlab_username]!
```

## Push our project from our workstation to Gitlab
We are going to push our codes from the our workstation to our Gitlab account. In order to do this, we first need to have:
1. A project created in our workstation. In my case, I have a C Executable project created using CLion IDE and stored in the following directory: `~/CLionProjects/CProject`.
1. An empty project created in our Gitlab account, where we are going to push the project's codes from our workstation into this empty project. 

We can create a project in Gitlab account by following these steps:
1. Clik the `New Project` button in the upper right corner of our Gitlab account.
1. Give a name to our project (I used CProject) and click on `Create Project`.
1. We will be redirected to the project page. This project should be empty.

Now, go back to our workstation and go to the directory where we saved our project. First, we need to use the `init` command for Git to begin tracking the directory:
```shell
cd ~/CLionProjects/CProject
git init
```
Note that your directory can be different than mine. 

Finally, use the following commands to push our project:
```shell
git remote add origin git@gitlab.com:[yourGitLabUsername]/[yourprojectname].git
git add .
git commit -m "Initial commit"
git push -u origin master
```
In my case, I used `git remote add origin git@gitlab.com:you3quan2/cproject.git`.

Go to our Gitlab account and we are supposed to see the same set of codes in our workstation's project folders and the Gitlab's project folders.

## Update changes in our workstation to Gitlab
Now, we have the exact same project in our workstation and Gitlab. But, we still need to update the Gitlab's project every time we made changes on the project in our workstation. Here are the codes in the `main.c` file:
```python
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
In my case, I updated my `main.c` file and changed the line from `Hello, World!` to `Goodbye, World!`:
```python
#include <stdio.h>

int main() {
    printf("Goodbye, World!\n");
    return 0;
}
```
To update these changes to my Gitlab project, I used:
```shell
git add .
git commit -m "COMMENT TO DESCRIBE THE INTENTION OF THE COMMIT"
git push origin master
```
My comment is `Change from Hello World to Goodbye World`.

Go to the Gitlab account and check on the specific file which we have modified. We are supposed to see the changes which we have made. If we click on the `History` button, we will see our commit changes:



Suppose we are working on our workstation and want to keep the Gitlab's project updated with the changes we made in our 









, and Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-filename.md`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `filename` is whatever file name you choose, to remind yourself what this post is about. `.md` is the file extension for markdown files.

The first line of the file should start with a single hash character, then a space, then your title. This is how you create a "*level 1 heading*" in markdown. Then you can create level 2, 3, etc headings as you wish but repeating the hash character, such as you see in the line `## File names` above.

## Basic formatting

You can use *italics*, **bold**, `code font text`, and create [links](https://www.markdownguide.org/cheat-sheet/). Here's a footnote [^1]. Here's a horizontal rule:

---

## Lists

Here's a list:

- item 1
- item 2

And a numbered list:

1. item 1
1. item 2

## Boxes and stuff

> This is a quotation

{% include alert.html text="You can include alert boxes" %}

...and...

{% include info.html text="You can include info boxes" %}

## Images

![]({{ site.baseurl }}/images/logo.png "fast.ai's logo")

## Code

You can format text and code per usual 

General preformatted text:

    # Do a thing
    do_thing()

Python code and output:

```python
# Prints '2'
print(1+1)
```

    2

Formatting text as shell commands:

```shell
echo "hello world"
./some_script.sh --option "value"
wget https://example.com/cat_photo1.png
```

Formatting text as YAML:

```yaml
key: value
- another_key: "another value"
```


## Tables

| Column 1 | Column 2 |
|-|-|
| A thing | Another thing |


## Tweetcards

{% twitter https://twitter.com/jakevdp/status/1204765621767901185?s=20 %}


## Footnotes



[^1]: This is the footnote.

