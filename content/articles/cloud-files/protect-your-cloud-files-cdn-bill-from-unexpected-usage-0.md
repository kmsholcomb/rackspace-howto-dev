---
node_id: 2162
title: Protect Your Cloud Files CDN Bill from Unexpected Usage
type: article
created_date: '2012-09-14'
created_by: David Hendler
last_modified_date: '2016-01-21'
last_modified_by: Catherine Richardson
product: Cloud Files
product_url: cloud-files
---

<span>When choosing to use the content delivery network (CDN) to
accelerate your website and the images and videos on that website, you
are responsible for all bandwidth costs associated with delivery of your
content over the public Internet, including bandwidth incurred because
of piracy. </span><span>This article is designed to help you monitor and
protect your CDN usage.<span>  </span></span>

When you use the CDN, all your assets are assigned a CDN URL.<span> Your
website then has that </span>CDN URL in its source code and displays it
when a user requests to see it.<span> Some</span> companies and
individuals target websites&rsquo; asset URLs and serve them without the site
owner&rsquo;s permission.<span> T</span>his is known as &ldquo;hot linking&rdquo; and can
result in a massive increase to your CDN bill if the problem goes
unnoticed.<span>  </span>

You can protect yourself, your content, and your invoice from hot
linking in the following ways:

-- Constant monitoring and alerts for abnormal CDN bandwidth usage
-- Proactive measures to make it more difficult to access your site&rsquo;s
source code


### Monitor usage in the Cloud Control Panel ******

One way to monitor your current CDN usage is through the Cloud Control
Panel.

1.  Log in
    to [http://mycloud.rackspace.com](http://mycloud.rackspace.com/).
2.  In the upper-right corner of the panel, click the **Account:
    *yourCloudAccountUsername*** menu and select **Usage Overview**.
    On the Current Usage page, you can see the service usage for all of
    your Rackspace products and services.
3.  Next to any service, click the down arrow for more information about
    how you are using your services. If you are using multiple Rackspace
    Cloud products, you might need to scroll down to find your Cloud
    Files usage.

 ![](https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/1560-2162-newimg.png)

###

### Examine CDN logs

Another method for monitoring your CDN usage is by examining the CDN
logs. Every CDN customer can turn on CDN logs for their containers that
are CDN enabled. If you find that your content has been hot linked, you
can use your CDN logs to find which URLs are compromised and take action
immediately. You can also enable these logs via the Cloud Files API or
from your [Cloud Control Panel](http://mycloud.rackspace.com/) by
performing the following steps:

1\. In the top navigation bar, click **Storage &gt; Files**.
2. Click the gear icon next to the container for which you want to
enable CDN logs, and select **Enable Logs**.

![](https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/1560-2162-newimg2.png)

After you have enabled CDN logs for your content, Cloud Files creates a
container for you and delivers logs to that container.  The frequency of
log delivery can vary depending on how heavy traffic is on the CDN, but
logs are usually delivered every four hours.

The log files inside of the .CDN\_ACCESS\_LOGS container will be
prefixed with the name of the container they are logging, followed by
the date and time stamp. This makes it easy to find logs for a specific
time period.

***Third-party log analysis***

Several companies in the market will take the hassle out of parsing the
logs in your CDN log container.  These companies take the raw logs that
Rackspace delivers to your account and make them easy to consume and
understand.  For example, they will show you peak traffic times and
geographic regions that access your data the most.

For monitoring purposes, most of these tools allow you to set up alerts
to indicate when usage reaches a certain level, or if it has increased
by a certain amount.  This is a great way to get monitoring without
having to code a solution yourself.

 Rackspace has two [Cloud Tools
Partners](https://cloudtools.rackspace.com/home) that provide these
features, [Cloud
Ability](https://cloudtools.rackspace.com/apps/445?1601080659) and [QloudStat](https://cloudtools.rackspace.com/apps/399?1814232928).




### Hide source code

Although completely hiding your source code is impossible, following are
some common tools that can serve as a first line of defense against
those trying to steal content.  Although someone with more technical
knowledge will find ways around these defenses, it might take long
enough for them to give up.

**<span>No right-click scripts</span>**

There are scripts that will prevent visitors from using the right-click
menu to copy your content&rsquo;s link or view your site&rsquo;s source code.
Although there are other ways to find this information, preventing
right-click access can be an easy first step to protecting your site.
If you attempt this method, be sure to check its functionality in a
variety of browsers, because the code can be difficult to implement
across all of them.

 **<span>JavaScript encryption</span>**

The method involves taking your code, using a custom-made function to
"encrypt" it, and then putting it in an HTML file along with a function
that will decrypt it for the browser. While website visitors will still
be able to view your source code, they will not be able to use it
without decrypting.  There are several tools online that will help
encrypt your source code.  Here are some links and examples that might
be helpful: <span> </span>

-   [Encrypting source
    code](http://www.blackbeltcoder.com/Articles/mfc/encrypting-source-code)
-   [Simple encrypting
    tool](http://www.webtoolhub.com/tn561359-html-encrypter.aspx)<span> </span>
-   [Article discussing options for
    encryption](http://www.htmlguard.com/articles/about-html-source-code-encryption/)

This method requires the use of JavaScript, meaning that you need to
expect your legitimate website traffic to be using browsers and settings
that support it. <span> </span>



