---
title: Download rpm packages from repository on CentOS7
description: Use yumdownloader to download rpm packages from repository.
categories:
 - CentOS
tags:
 - Tools
---

Sometime we need to have a copy of the rpm package.  There are many ways to acquire the packages such as `wget` or directly from repository url from browser.  But if you don't know the url or too lazy to find out, you can use `yumdownloader` command and it will do the rest for you.

Install `yum-utils` to obtain `yumdownloader` command.
```bash
yum install yum-utils
```
![yumdownloader](/assets/images/2018051704.png)  
![yumdownloader](/assets/images/2018051705.png)

{% include ads3.html %}

Then we can download the rpm package with command
```bash
yumdownloader httpd
```
![yumdownloader](/assets/images/2018051706.png)

And there you go, now you can do whatever you want with it.  
![yumdownloader](/assets/images/2018051707.png)
