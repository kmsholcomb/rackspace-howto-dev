---
node_id: 2020
title: Features introduced in RackConnect v2.0
type: article
created_date: '2012-08-21 16:49:40'
created_by: juan.perez
last_modified_date: '2015-12-31 14:2206'
last_modified_by: stephanie.fillmon
product: RackConnect
body_format: tinymce
---

### Previous section

[Introducing RackConnect
v2.0](https://www.rackspace.com/knowledge_center/article/introducing-rackconnect-v20)

**Applies to:** RackConnect v2.0

The 2.0 version of RackConnect added the following automation and
security features:

**Support for next generation Rackspace Cloud Servers**, powered by
OpenStack&reg;^

**RackConnect API**, which gives you a way to programmatically access
certain read-only information about your cloud servers and their
RackConnect configuration from within your cloud servers

**Improved RackConnect automation responsiveness to cloud server
events**, which means that RackConnect picks up changes in your Cloud
environment much faster

**A RackConnect Management Interface in the MyRackspac&reg; Portal**, where
you can perform the following tasks:

-   Set RackConnect network policies
-   Manage cloud servers
-   View configuration details
-   View automation tasks and event logs

**Network security policies:**

-   Set once, applied automatically
-   Manages dedicated firewall, load balancer, and cloud server software
    firewalls

**Managed software firewalls for Cloud Servers:**

-   Iptables for Linux
-   Advanced firewall for Windows

**Automation features:**

-   *(Optional)* Provision public IP addresses: Cloud servers are
    automatically provisioned with a public IP address from your
    Dedicated networ&rsquo;s public IP block.

-   *(Optional)* Configure network stack: Cloud servers are
    automatically configured with network connectivity to your Dedicated
    environment.

-   *(Optional)* Manage software firewall: Cloud servers can be
    automatically load balanced based on server name matching or
    metadata.

**IMPORTANT:** RackConnect adds a service-level user account called
**rackconnect** to each cloud server in a RackConnect solution. This
account enables RackConnect to automate network connectivity and
software firewalls on cloud servers as part of the RackConnect solution.
This account is for use only by the automated system, not by actual
Rackers (support techs). It should not be deleted under any
circumstances.

Next steps

[RackConnect Key
Terms](https://www.rackspace.com/knowledge_center/article/rackconnect-key-terms)
