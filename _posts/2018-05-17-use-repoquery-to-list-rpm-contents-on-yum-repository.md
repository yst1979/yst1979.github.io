---
title: Use repoquery to List RPM Contents on Yum repository
description: Use repoquery command to list rpm package contents on yum repository without installing it on CentOS7.
categories:
 - CentOS
tags:
 - Tools
---

If you want to know what are the contents of a rpm package on yum repository before installing it, you can use `repoquery` command to achieve that.  `repoquery` command is provided by `yum-utils` package, so it must be installed first.
```bash
yum install yum-utils
```
![repoquery](/assets/images/2018051709.png)

{% include ads3.html %}

Now you can use `repoquery` to query the content from yum repository.
```bash
repoquery -l packageName
```
![repoquery](/assets/images/2018051710.png)
