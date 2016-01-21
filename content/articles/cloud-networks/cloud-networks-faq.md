---
node_id: 3717
title: Cloud Networks - FAQ
type: article
created_date: '2013-10-02'
created_by: Sameer Satyam
last_modified_date: '2016-01-20'
last_modified_by: Stephanie Fillmon
product: Cloud Networks
body_format: markdown_w_tinymce
---

####What are the different networks in the Rackspace Cloud?

The Rackspace Cloud contains the following networks:

<ul>
   <li><strong>PublicNet</strong> (public)
   <p>PublicNet connects a cloud server to the Internet. When you create cloud servers with PublicNet, your servers get an IPv4 address and an IPv6 address. Outbound public traffic is billed according to [published rates](http://www.rackspace.com/cloud/public-pricing/#bandwidth). You can create a server without a public network; however, access to operating system updates, Cloud Monitoring remote checks, and so on might not work. For more information about the limitations of not having a public network, see <a href="/how-to/removing-networks-from-a-cloud-server">Removing Networks from a Cloud Server</a>.</p>
   <p><strong>Note</strong>: PublicNet is required for RackConnect and Managed Operations service level customers.</p></li>
   <li><strong>ServiceNet</strong> (Private)
   <p>ServiceNet is an internal, multi-tenant network within each Rackspace Cloud region. It provides cloud servers access to regional services, such as Cloud Files, Cloud Load Balancers, Cloud Databases, and Cloud Backup, at no cost. ServiceNet is currently IPv4 only. Historically, ServiceNet was used for server-to-server communication, but Cloud Networks is now recommended for this purpose. ServiceNet is also required for Windows cloud server activation. We recommend that cloud servers be connected to ServiceNet and that all new connections inbound to the server be denied by a software firewall such as iptables or Windows Firewall. For more information, see <a href="/how-to/removing-networks-from-a-cloud-server">Removing Networks from a Cloud Server</a>.</p>
   <p><strong>Note</strong>: ServiceNet is required for RackConnect and Managed Operations service level customers.</p></li>
   <li><strong>Cloud networks</strong> (isolated)
   <p>Cloud networks are isolated networks that can be used for secure communication between your cloud servers. Cloud networks are completely private and single tenant, and can be either IPv4 or IPv6. Cloud networks are recommended for all communication between cloud servers. Like ServiceNet, all bandwidth on cloud networks is provided at no charge.</p></li>
</ul>

####What are the different networking APIs in the Rackspace Cloud?

The Rackspace Cloud has two networking APIs - Neutron and Nova-Network.

Rackspace first introduced networking services that were based on the OpenStack Nova-Network API. This version of the service is now superseded by the current networking API, based on OpenStack Neutron, which offers a richer suite of networking services. Both APIs continue to function, but the Neutron API will be the base for all the future networking services that Rackspace offers. For more information, see [Networking: Neutron versus Nova-Network](https://developer.rackspace.com/docs/cloud-networks/v2/developer-guide/#networking-neutron-versus-nova-network) in the Cloud Networks Developer Guide.

####How many cloud networks can I create?

Every Rackspace Managed Infrastructure account has a default limit of 10 cloud networks per region. To request an increase, please submit a ticket in the Cloud Control Panel with details about how you intend to use the additional networks.

####Is there a limit on the number of servers that can be attached to a single cloud network?

Yes. A maximum of 250 servers can be attached to a single cloud network.

####What are the other limits in the Cloud Networks service?

The following list shows all the limits defined for the service:

-   Cloud networks per region: 10
-   Subnets per network: 2 (one IPv4 and one IPv6)
-   DNS name servers per subnet: 2
-   Host routes per subnet: 3
-   Allocation pools per subnet: 5
-   Number of fixed IP addresses per port: 4
-   Ports (hosts) per network: 250
-   Security groups per port: 5
-   Security group rules per security group: 20
-   Security group rules per user: 100

####Can I add or remove existing networks from a cloud server?

Yes. You can add or remove any network (PublicNet, ServiceNet, or cloud network) from a server that is in a Managed Infrastructure service level account. However, Managed Operations service level and RackConnect customers are required to have PublicNet and ServiceNet interfaces. This capability means that you can freely make networking changes to your existing deployments without having to rebuild Cloud Servers.

For more information, see the [Virtual Interfaces extension](https://developer.rackspace.com/docs/cloud-servers/v2/developer-guide/#virtual-interfaces-extension) in the Cloud Servers Developer Guide (using the nova-network API) or [Boot a new server with your cloud network](https://developer.rackspace.com/docs/cloud-networks/v2/developer-guide/#document-getting-started/managing-networks/boot-server) in the Cloud Networks Getting Started Guide (using the neutron API).

**Note**: Be aware that removing PublicNet or ServiceNet interfaces might impact certain Rackspace services and capabilities.

####Can I transfer Cloud Networks IP addresses from one Rackspace cloud server to another?

Yes. IP addresses on Cloud Networks are usable by any other cloud server on that network.

####Can I transfer a PublicNet or ServiceNet IP address from one Rackspace cloud server to another?

No. At this time, you cannot transfer a PublicNet or ServiceNet IP address between cloud servers.

####What is the network throughput on Cloud Servers?

The amount of network throughput varies based on the Cloud Server flavor. For more details, see the [Cloud Servers pricing information](http://www.rackspace.com/cloud/public-pricing/#cloud-servers).

####What is the scope of a cloud network?

Cloud networks are regional in scope and can be attached to any of your cloud servers in a given region.
