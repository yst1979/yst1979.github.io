---
title: MongoDB-3.6 Community Edition Installation
description: Mongodb-3.6 community edition installation with yum on CentOS7.
categories:
 - CentOS
tags:
 - Mongodb
---

In this post, I am going to use yum to install MongoDB-3.6 from MongoDB's official repository.  First we start with adding a .repo file at location `/etc/yum.repos.d/`.  You can name the file anyway you wish but the extension has to be `.repo`.
```bash
vim /etc/yum.repos.d/mongodb.repo
```
![mongodb installation](/assets/images/2018043002.png)

Paste the follow code into the .repo file you created, save and exit. You can change `3.6` to the version you want.  For instance, `3.4` or `3.2`.
```
[mongodb-org-3.6]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.6/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-3.6.asc
```
![mongodb installation](/assets/images/2018043001.png)

Check if the repository is successfully added.
```bash
yum repolist
```
![mongodb installation](/assets/images/2018043003.png)

Start installing MongoDB.
```bash
yum install mongodb-org
```
![mongodb installation](/assets/images/2018043004.png)

The functionality of each installed packages.
<br>![mongodb installation](/assets/images/201804311.png)

After installation, let's check the initial status of `mongod`.
```bash
systemctl status mongod
```
![mongodb installation](/assets/images/201804310.png)

{% include ads3.html %}

For more usage of systemctl, please refer: [CentOS7 Systemctl Cheat Sheet](https://www.bulafish.com/centos/2018/04/27/centos7-systemctl-cheat-sheet/)

Mongod is enabled initially.  If the service is not enabled, use command below to enable and start the service.
```bash
systemctl enable mongod
systemctl start mongod
```
![mongodb installation](/assets/images/201804306.png)

Check the version of mongod.
```bash
mongo -version
```
![mongodb installation](/assets/images/201804309.png)

Locations related to Mongodb.
1. `/etc/mongod.conf`; config file of mongod.
2. `/var/log/mongodb/`; log file of mongod.
3. `/var/lib/mongo/`; db path of mongod, all data files are store here.

![mongodb installation](/assets/images/201804308.png)

Connect to mongod.
```bash
mongo
```
![mongodb installation](/assets/images/201804307.png)

REFERENCES:
<br>[
Install MongoDB Community Edition on Red Hat Enterprise or CentOS Linux](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/#run-mongodb-community-edition)
