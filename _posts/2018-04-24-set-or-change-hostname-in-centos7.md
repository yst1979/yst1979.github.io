---
title: Set Or Change Hostname In CentOS7
description: Since CentOS7, the way to modify hostname has changed.  Now we use hostnamectl command to do the job.
categories:
 - CentOS
---

In CentOS6, we modify /etc/sysconfig/network to set the servers's hostname but in CentOS7, it was changed to use command line to change or set the hostname.  I did not know this when I first start using CentOS7 until I google about it.  The commands are as below

## Check hostname status
The following command will show you the current hostname status of your server.  Static hostname is the filed we are going to set to a desired name.
```bash
hostnamectl status
```
![hostnamectl](/assets/images/2018042301.png)

{% include ads3.html %}

## Changing or setting hostname
Use the command below to change or set the hostname of the server.  After that, use the status command again to confirm the change.
```bash
hostnamectl set-hostname TheHostnameYouWant
```
![hostnamectl](/assets/images/2018042302.png)

Be aware that you have to re-login in order to make the hostname in your connection to take effect, like the image below.
<br>![hostnamectl](/assets/images/2018042303.png)

And there you go, that's how we change the hostname in CentOS7.
