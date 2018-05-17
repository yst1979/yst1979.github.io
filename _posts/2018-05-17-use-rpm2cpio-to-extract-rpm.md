---
title: Use rpm2cpio to Extract Files from RPM Packages on CentOS7
description: Use rpm2cpio to extract files from rpm packages on centos7.
categories:
 - CentOS
tags:
 - Tools
---

I had needs to confirm certain files or directories are installed from which packages, this is the way to do it and solve my problem.

To extract the files from rpm packages, we need to download it first, please refer here:

Once you have th rpm file, use this command to extract files from rpm package to your local hdd.

{% include ads3.html %}

```bash
rpm2cpio myrpmfile.rpm | cpio -idm
```
![rpm2cpio](/assets/images/2018051708.png)

Now you have all the files from the packages!  You can use -idmv to show the extracting process if you want to.
