---
node_id: 672
title: Installing WordPress on Cloud Sites
type: article
created_date: '2011-03-16'
created_by: Rackspace Support
last_modified_date: '2015-12-30'
last_modified_by: Stephanie Fillmon
product: Cloud Sites
body_format: tinymce
---

**NOTE:** This article refers to the [Cloud Sites Control
Panel](https://manage.rackspacecloud.com/). You can access this
interface from the [Cloud Control Panel](https://mycloud.rackspace.com/)
by clicking your username in the upper-right corner of the control panel
and selecting Cloud Sites Control Panel.

This article shows how to manually install WordPress on Cloud Sites.

**Prerequisites**

-   Administrative access to the Rackspace Cloud to create domains and
    add databases
-   WordPress software from
    <a href="http://wordpress.org/download/" class="uri" class="external free" title="http://wordpress.org/download/">http://wordpress.org/download/</a>
    uncompressed in a local repository
-   FTP access to website, and a FTP client like ExpanDrive

**Procedure**

1.  Login to the [<span class="external text">Cloud Sites Control
    Panel</span>](https://manage.rackspacecloud.com). If you are new the
    Rackspace Cloud, please refer to the article <span
    class="external text">[Adding a new
    website](/how-to/getting-started-with-cloud-sites-how-to-add-a-new-website).</span>

2.  <span class="external text">Navigate the Hosting-&gt;Cloud Sites
    menu to the website hyperlink on which WordPress is to be
    installed

    **NOTE:** The domain must have database feature selected. The
    database feature can be added by using the CHANGE PLAN hyperlink on
    the domain **General Settings** tab.</span>

3.  <span class="external text">Upload WordPress software files to the
    desired location on the website using FTP - Refer to
    <a href="/how-to/getting-started-with-cloud-sites-uploading-your-content" class="external text" title="/knowledge_center/index.php/Uploading_content_to_a_website_using_FTP">Upload content to a website using FTP</a></span>

4.  To integrate WordPress to the root of domain (e.g.
    http://example.com/), place all contents of the uncompressed
    wordpress directory (excluding the directory itself) into the
    /web/content/ directory which is the root directory of the site.

5.  To have the WordPress installation in its own subdirectory on the
    website (e.g. http://example.com/blog/), rename the uncompressed
    wordpress directory to the name of choice and place it on the
    web server. For e.g. to create a WordPress installation in a
    directory called "blog", rename the directory called "wordpress" to
    "blog" and upload it to the root directory of the web site.

6.  Next create a new Mysql database (e.g. *prefix*\_wp20) with
    user (e.g. *prefix*\_wp20 ).  To create the database within the
    Cloud Sites infrastructure please refer to our article
    on <a href="/how-to/rackspace-cloud-sites-essentials-mysql-databases" class="external text" title="/knowledge_center/index.php/Adding_a_MySQL_database_to_a_website_or_domain">Adding a MySQL database to a website or domain</a>.


    If you prefer to use our Cloud Databases service you can follow the
    instructions in this article on [using Cloud Databases with Cloud
    Sites](/how-to/using-cloud-databases-with-your-cloud-site).

7.  Note the database information *database name*,** ***user name*,
    *password,*  and *hostname* (not localhost) for use during the
    WordPress installation. This can be found by clicking on the
    hyperlink for the new database just created in the
    **Databases** section of the website **Features **tab.

8.  Run the WordPress installation script by accessing WordPress for the
    first time in your favorite web browser.

-   If WordPress files are placed in the root directory, e.g. visit:
    [http://www.example.com/wp-admin/install.ph](http://www.example.com/wp-admin/install.php)p
-   If WordPress is in its own sub-directory called blog, e.g. visit:
    <http://www.example.com/blog/wp-admin/install.php>
-   <span>If DNS is not setup for the domain, use the Testing
    URL provided in the Cloud Sites Control Panel under the General
    Settings
    tab, e.g. http://www.example.com.php5-7.dfw1-1.websitetestlink.com/blog/wp-admin/install.php</span>

With this, Cloud Sites specific steps are complete. Now follow on screen
prompts to continue the installation.

-   Provide the necessary database information recorded during the
    preparation phase and press the **Submit** button
-   Provide details such as blog name , admin email address and press
    the **Install** button
-   Use the generated password to login as admin and then change the
    password if needed.

WordPress should now be fully functional and accessible based on the
install location

-   If WordPress files are placed in the root directory, e.g. visit:
    http://www.example.com
-   If WordPress is in its own subdirectory called blog, e.g. visit:
    http://www.example.com/blog
-   If DNS is not setup for the domain, visit the Testing URL, e.g.
    http://www.example.com.php5-7.dfw1-1.websitetestlink.com/blog
    provided in the Classic Cloud Control Panel under the General
    Settings tab.


**Additional Resources**

-   <a href="http://wordpress.org/download/" class="external text" title="http://wordpress.org/download/">More about Word Press</a>

