---
title: Showing and Setting Environment Variables on CentOS7
description: Use repoquery command to list rpm package contents on yum repository without installing it on CentOS7.
categories:
 - CentOS
tags:
 - Configuration
---

For some reason, we set values to Environment variable on our system so that our program can work accordingly.  therefore I learn how to show and set environment variables.

To show all the current environment values,
```bash
env
```
![env](/assets/images/2018051711.png)

To show particular environment value, for example `PATH`,
```bash
echo $PATH
```
![env](/assets/images/20180517112.png)

{% include ads3.html %}

To set a custom environment value, for example `bulafish=hi` and verify,
```bash
export bulafish=hi
echo $bulafish
```
![env](/assets/images/20180517113.png)

The value is only validate for the current ssh session by using the command above.  If you want to set the value permanently, modify `/etc/environment`, after that, you must logout the current ssh connection and re-login again to make the change take effect.  
![env](/assets/images/20180517114.png)

REFERENCES:  
[https://tw.godaddy.com/help/centos-12295](https://tw.godaddy.com/help/centos-12295)  
[Environment Variables](https://www.centoshowtos.org/environment-variables/)
