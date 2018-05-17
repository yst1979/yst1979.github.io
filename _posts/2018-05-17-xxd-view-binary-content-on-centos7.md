---
title: Use xxd to View Binary Content on CentOS7
description: Use xxd to view binary content on centos7.
categories:
 - CentOS
tags:
 - Tools
---

OK, I have two server, one install php from `webtatic` repository with package `php56w-cli`.  The `include_path` value is marked inside php.ini file and phpinfo() show me include_path with value of `/usr/share/php` which is exactly what I need.

Another, install php from `centos-sclo-rh` repository with package `rh-php56-php-cli`.  The `include_path` value is also marked inside php.ini file but phpinfo() show me include_path with value of `/opt/rh/rh-php56/root/usr/share/php` which is not what I want and is causing trouble of my program.

I solved this problem by setting value `/usr/share/php` to varialbe `include_path` inside php.ini but I was satisfy enough.  I want to know why this problem happend, how it happened.  So after a long search, I found the cause.  It is written hard coded in the php binary file.  So I guess the logic is used the hard coded value `/opt/rh/rh-php56/root/usr/share/php` for variable `include_path` IF noting is configured inside php.ini file.

{% include ads3.html %}

To find my solution, xxd helped.  When I had suspicion about the php binary file,  xxd helped to solve and confirm my doubts.  Use command below to view the content of the binary file.
```bash
xxd /opt/rh/rh-php56/root/usr/bin/php | less
```
![xxd](/assets/images/2018051702.png)

Hit `/` to change to search mode, type in the key word you looking for, then hit enter.  You can press `n` to look for next matching result.  Press `q` to quit.  
![xxd](/assets/images/2018051703.png)

Compared this value with the php binary file from `webtatic` and it proved my doubt.  When value is not set for `include_path` in php.ini file, value hard coded in binary file is used.
