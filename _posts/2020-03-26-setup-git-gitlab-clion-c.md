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
The command tells us which Git version we have on our workstation. If you don't receive a `Git version` message, it means that you need to install Git (check on the `Requirements` section).


https://about.gitlab.com/



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

