---
layout: blogpost
title: "Monitoring Django Based Website with Munin"
date: 2014-9-2 05:04:20 +0530
categories: tutorials
type: blog
---

Munin is a free and open-source computer system monitoring, network monitoring and infrastructure monitoring software application. Munin offers monitoring and alerting services for servers, switches, applications, and services. It alerts the users when things go wrong and alerts them a second time when the problem has been resolved.

Munin is written in Perl and uses the RRDtool to create graphs, which are accessible over a web interface. Its emphasis is on plug and play capabilities. About 500 monitoring plugins are currently available. Using Munin you can monitor the performance of your computers, networks, SANs, and applications. It is intended to make it easy to determine "what's different today" when a performance problem crops up and to provide visibility into capacity and utilization of resources.

Munin has a master/node architecture in which the master connects to all the nodes at regular intervals and asks them for data. It then stores the data in RRD files, and (if needed) updates the graphs. One of the main goals has been ease of creating new plugins (graphs). <sup>[[1]](http://munin-monitoring.org/)</sup>

---
## Installation
Munin can be installed on Ubuntu by a simple `apt-get`:

    sudo apt-get install munin

and on Fedora by:

    yum install munin

---
## Configuration
As soon as Munin is installed, it begins it's operations. Now, we need the monitoring graphs. These graphs are auto-generated in a folder that can be defined by the user. To do this, we need to change a configuration file.

The file to be changed is `/etc/munin/munin.conf`. In this file, we need to add value to the **htmldir** directive. Since, we are running on Django, it'd be best if we make this directory static.

---
## Getting the graphs by running munin-cron
Now that the directory has been set up, we need to give permissions to the user munin (created by default) to read-write that directory. The following command would work:

    chown -R munin:munin [path to directory]

Next, we need to run `munin-cron`. For this, we need to login as the user munin and execute `munin-cron` o the terminal. And that is it. We'll get graphs at `[path to static directory]/index.html` that change after every 5 minutes.

##Fedora Bug
There is a small bug in Fedora 20 that might cause some issue. The bug looks something like:

    not a reference at /usr/share/perl5/vendor_perl/Munin/Master/Utils.pm line 866.

It has a solution [here](https://bugzilla.redhat.com/show_bug.cgi?id=955902).
