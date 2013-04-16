---
layout: post
title: "I built a PGP Key Server on my Raspberry Pi"
date: 2013-04-16 06:46
comments: true
categories: raspberrypi, linux, pgp, gpg
---
I have a [Raspberry Pi](http://www.raspberrypi.org/) which I like to toy with. I have another one that runs [Rasbmc](http://www.raspbmc.com/), but that's just for watching movies on.

Well I was updating my public key records for PGP/GPG and it occured to me that I should be able to run a small key server myself.

I have [Raspbian](http://www.raspbian.org/) on my Pi which is a [Debian](http://debian.org) based distro. Therefore it has the vast majority of the repositories that standard Debian has available to it.

First think I did was setup [no-ip](http://www.no-ip.org) because my ISP doesn't provide static IPs to residential customers.

So from my laptop I start with these commands:

```
ssh pi@x.x.x.x
```

Replace `x.x.x.x` with your Pi's IP. Provide the password to login default is `raspberry`.

Now download and install No-IP.

```
wget http://www.no-ip.com/client/linux/noip-duc-linux.tar.gz
tar xf noip-duc-linux.tar.gz
cd noip-2.1.9-1/
make install
```

You will be prompted to put the login details for your account at No-IP. You will be asked how often to update, I sugest 360 which is 1 hour.

Now we need to set No-IP to run at boot.

```
sudo nano /etc/rc.local
```

Simply add the following line and close and save.

```
/usr/local/bin/noip2
```

Now we have a host we can use and we are ready for the main event.

As SKS is in your base repositories you can use.

```
apt-get install sks
```

Now build the database.

```
sks build
```

Now you need to get SKS to run at boot also.

```
sudo nano /etc/default/sks
```

Find the line.

```
initstart=no
```

Change it to.

```
initstart=yes
```

There you go. You have now got an SKS server running on your machine.

If you are looking for the web front end, then you can use the files from [syslog.tv](https://syslog.tv).

Create your directory.

```
sudo mkdir -p /var/lib/sks/www/
```

Now copy the index file to it.

```
wget http://syslog.tv/downloads/sks-index.html -O /var/lib/sks/www/index.html --no-check-certificate
```

There you go. All setup and running.

You can sometimes access my key server [here](http://antonybailey.no-ip.org:11371/). Though I will probably give up and do something else in a week.