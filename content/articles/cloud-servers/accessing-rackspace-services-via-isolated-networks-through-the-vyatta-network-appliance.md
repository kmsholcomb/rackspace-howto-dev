---
node_id: 3454
title: Accessing Rackspace Services Via Isolated Networks through the Vyatta Network Appliance
type: article
created_date: '2013-05-02'
created_by: Sameer Satyam
last_modified_date: '2014-03-06'
last_modified_by: David Hendler
product: Cloud Servers
product_url: cloud-servers
---

Introduction
------------

In order to access Rackspace services from your cloud servers, you
traditionally need the servers to be connected to ServiceNet and/or
Public interfaces. It is possible to detach your servers from either of
these networks and have servers be connected only to isolated network
interfaces if you want to restrict access to them. However, this would
cause you to lose access to some Rackspace services.

The article below describes what services are impacted by disconnecting
Public and/or SNET interfaces from your cloud servers.

</how-to/removing-networks-from-a-cloud-server>

Vyatta Network Appliance
------------------------

The Vyatta network appliance provides you with an easy-to-configure
firewall, advanced networking and VPN capabilities in addition to
increased security in the Cloud. Using this appliance , you can detach
your servers from Public and SNET interfaces and still retain access to
Rackspace services. In this article you will see how this can be
accomplished.

Accessing Rackspace services using NAT on the Vyatta appliance
--------------------------------------------------------------

In the below setup the cloud server is connected only on the isolated
network (cloud network). The Vyatta is also on the same cloud network
and is used as the default gateway by the server in question. The Vyatta
appliance is connected to all three networks (Public, SNET and
Isolated).<span style="line-height: 1.538em;"> </span>

<img src="/knowledge_center/sites/default/files/styles/half_width/public/field/image/Vyatta.jpg" class="image-half_width" width="350" height="224" />

<span style="line-height: 1.538em;">The table below summarizes what
services can be accessed if the Vyatta is configured as described in the
next section:</span>

**Service**

**Works ?**

Cloud Backup

Yes

Cloud Databases

Yes

Cloud Files

Yes

Cloud Monitoring

No

Managed Cloud Service Level

No (Vyatta Network appliance is not supported for accounts with Managed
Cloud Service Level)

Operating System Updates

Yes

RackConnect

No (Vyatta Network Appliance is not supported for RackConnect)

Windows Activiation

Yes



Configuration
-------------

In order for the services listed in the table above to work as explained
, the Vyatta appliance needs to be configured with Source NAT.  For a
more comprehensive explanation of Source NAT configuration , visit the
link below:

</how-to/enable-internet-access-on-cloud-servers-using-snat-on-a-vyatta-network-appliance>

###### Note: The cloud servers are on the isolated interface 192.168.1.0/24 and they are using the Vyatta network appliance as their default gateway

Login to the Vyatta appliance and enter configuration mode<span
style="line-height: 1.538em;"> </span>

    $ ssh vyatta@x.x.x.x
    Welcome to Vyatta
    vyatta@x.x.x.x's password:
    Welcome to Vyatta
    Version:      VSE6.5R2
    Description:  Vyatta Subscription Edition 6.5 R2
    Copyright:    2006-2012 Vyatta, Inc.
    Last login: Thu May  2 04:48:29 2013 from x.x.x.x
    vyatta@vyatta-thefinal:~$
    vyatta@vyatta-thefinal:~$ configure
    [edit]
    vyatta@vyatta-thefinal#

<span
style="font-family: 'Lucida Grande', 'Lucida Sans Unicode', sans-serif; font-size: 13px; line-height: 1.538em;">
Configure Source NAT for ServiceNet traffic. eth1 is the SNET interface
on the Vyatta. Any traffic going out via SNET will now use a source IP
of the SNET interface on the Vyatta.</span>

``` {.p1}
set nat source rule 10 outbound-interface 'eth1'
set nat source rule 10 protocol 'all'
set nat source rule 10 source address '192.168.1.0/24'
set nat source rule 10 translation address 'masquerade'
```

<span
style="font-family: 'Lucida Grande', 'Lucida Sans Unicode', sans-serif; font-size: 13px; line-height: 1.538em;">
Configure Source NAT for PublicNet traffic. eth0 is the Public interface
on the Vyatta. </span><span style="line-height: 1.538em;">Any traffic
going out via PublicNet will now use a source IP of the Public interface
on the Vyatta.</span>

``` {.p1}
set nat source rule 20 outbound-interface 'eth0'
set nat source rule 20 protocol 'all'
set nat source rule 20 source address '192.168.1.0/24'
set nat source rule 20 translation address 'masquerade'
```


This simple configuration should allow you to access the services listed
in the table. You may also want to configure firewall policies on the
Vyatta appliance. For configuration assistance of firewall policies on
Vyatta please visit the URL below:

[http://www.rackspace.com/knowledge\_center/article/configuring-interface-based-firewall-on-the-vyatta-network-appliance
](/how-to/configuring-interface-based-firewall-on-the-vyatta-network-appliance)

