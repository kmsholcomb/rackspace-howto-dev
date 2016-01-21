---
node_id: 4778
title: Working with checks
type: article
created_date: '2015-08-05'
created_by: Constanze Kratel
last_modified_date: '2015-08-27'
last_modified_by: Constanze Kratel
product: Rackspace Intelligence
product_url: rackspace-intelligence
---

Rackspace Intelligence provides an interface that you can use to create
new checks to generate metrics for your entities, and to update existing
checks.

Each check has a designated *type*. The check type instructs the
monitoring system how to check the monitored resource. For more
information, see [Check
types](http://ttp://docs.rackspace.com/cm/api/v1.0/cm-devguide/content/service-check-types.html.).

Checks types are divided into two categories:

-   *Agent* checks monitor an entity's resource utilization. Agent
    checks are performed by the monitoring agent running on a server.
    For example, a Memory check can trigger an alarm if it detects
    memory usage above a specified percentage. Agent checks require the
    monitoring agent to be installed on the server. For a list of
    available agent check types, see [Agent check
    types](http://docs.rackspace.com/cm/api/v1.0/cm-devguide/content/appendix-check-types-agent.html).
    For information on how to install the monitoring agent, see [Install
    and
    configure](http://docs.rackspace.com/cm/api/v1.0/cm-devguide/content/install-configure.html).
    Rackspace Intelligence supports the following types of agent checks:
    -   Apache
    -   CPU
    -   Custom Plugin
    -   Disk
    -   Filesystem
    -   Load Average
    -   Memory
    -   SQL Plan Cache
    -   SQL Memory Manager
    -   SQL Buffer Manager
    -   SQL Version
    -   SQL Statistics
    -   MySQL
    -   Network
    -   Redis
    -   Windows PerfOS
-   *Remote* checks monitor an entity's internet connectivity. Remote
    checks are performed by attempting to contact the entity from
    outside the entity.
    For example, Ping check can trigger an alarm if it detects packet
    loss above a specified percentage. For a list of available remote
    check types, see [Remote check
    types](http://docs.rackspace.com/cm/api/v1.0/cm-devguide/content/appendix-check-types-remote.html).
    Rackspace Intelligence supports the following types of remote
    checks:
    -   DNS
    -   FTP Banner
    -   HTTP
    -   IMAP Banner
    -   Ping
    -   POP3 Banner
    -   SMTP Banner
    -   SMTP
    -   SSH
    -   TCP
    -   Telnet Banner

Some checks that cannot be created with the Rackspace Intelligence
interface can be created by using the Cloud Monitoring CLI or API. These
checks are listed at [Rackspace Cloud Monitoring Checks and
Alarms](/how-to/rackspace-monitoring-checks-and-alarms).

Checks can generate alerts. You can observe open alerts within the
Rackspace Intelligence dashboard. You can also choose to notify someone
(for example, on-call technical support) or to suppress notification
(for example, during scheduled maintenance).

Create a check
------------------

To create a new check, complete the following steps:

1.  Log in to the [Rackspace Intelligence
    interface](http://intelligence.rackspace.com).
2.  On the **Monitoring** page, click the entity for which you want to
    create the check.
3.  In the **Monitoring Checks** section of the entity details page,
    click **Create Check**.
    <img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/intelligence-checks-create-check.png" width="655" height="127" />
4.  In the popup dialog box, click the **Check Type** box and select the
    appropriate check type from the list.
5.  In the **Check Name** box, type a name for the check.
6.  Specify any other values for the type of check that you are
    creating, and then click **Create Check**.
    After successfully creating the check, Rackspace Intelligence
    displays a details page with the name of your check. This page
    provides relevant information about your check.

Edit a check
----------------

To edit your check, click the **Actions** menu on the check details
page.

You can perform the following editing actions for checks:

-   [Rename a check](#renaming)
-   [Add an alarm](#addingalarm)
-   [Modify the status of your check](#modify)
-   [Modify the parameters of your check](#modifyparams)
-   [Delete the check](#deleting)

### Rename a check

1.  From the **Actions** menu on the check details page, select **Rename
    Check**.
2.  In the Rename Check dialog box, type the new name and then
    click **Rename**.

### Add an alarm

For instructions on adding an alarm for a check, see the &ldquo;Create an
alarm&rdquo; section of [Working with Alarms in Rackspace
Intelligence](/how-to/working-with-alarms).

### Modify the status of a check

1.  From the **Actions** menu on the check details page, select **Modify
    Status**.
2.  To enable the check, select **Enabled**. To disable the check,
    select **Disabled**.
3.  Click **Save Status**.

### Modify the parameters of a check

1.  From the **Actions** menu on the check details page, select **Modify
    Parameters**.
2.  In the dialog box, type the new parameter values, and then
    click **Save Parameters**.

### Delete a check

1.  From the **Actions** menu on the check details page, select **Delete
    Check**.
2.  To permanently delete the check, click **Delete Check**.


