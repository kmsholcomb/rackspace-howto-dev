---
node_id: 1282
title: Microsoft Exchange public folders
type: article
created_date: '2012-02-06'
created_by: Rackspace Support
last_modified_date: '2016-01-28'
last_modified_by: Rose Coste
product: Microsoft Exchange
product_url: exchange
---

Public folders are a feature of Microsoft Exchange that are used to
share information with others within your organization. Public folder
administrators can set privileges for users to access a folder, or the
folder can be made available to everyone within your organization.
Public folders can contain contacts, calendar items, messages, journal
entries, or notes.

This article provides instructions for working with public folders in a
[hosted Microsoft
Exchange](http://www.rackspace.com/email-hosting/hosted-exchange/)
environment:


### Enable public folders from within the control panel

1. Log in to your Cloud Office Control Panel and select **Microsoft
   Exchange** from the **Go To Section** menu.

2. Select the **Enable Public Folder** link to set up your
   public folder.

3. Select an administrator for your public folders by selecting any
   mailbox in your control panel and the **Public folder admin** option
   at the bottom.

**Note:** After public folders are enabled, setup takes about 3 to 5
minutes to complete. You must close and reopen Outlook to see your new
public folder.

### Access your public folders within your email client

You can access public folders from email clients on both Windows and
Mac. Following are instructions for accessing public folders through
Outlook and Entourage.

#### Outlook 2003, 2007, 2010 for Windows

1. Open Outlook and log in to your email account.

2. In the navigation pane, click the **Folder List** icon.

3. Expand **Public Folders** &gt; **All Public Folders**, the root
   folder, and your domain.

#### Outlook 2011 for Mac

1. Open Outlook 2011 and log in to your email account.

2. From the **Tools** menu, select **Public Folders**.
   Within the folder browser, select the root folder and your domain.

#### Entourage 2008

1. Open Entourage and log in to your email account.

2. In the navigation pane, expand **Public Folders**, **All Public
   Folders**, the root folder, and  your domain.

### Add folders to your public folders and assign permissions

When you create a public folder, you can assign permissions to limit
how much access others have to that folder.

**Create a public folder**:

1. Open Outlook and log in to your email account.

2. In the navigation pane, click the **Folder List** icon.

3. Expand **Public Folders**, **All Public Folders**, the root folder,
   and your domain.

4. Right-click on your domain and select **New Folder**.

**Assign permissions to a public folder**

1. Right-click the folder and select **Properties**.

2. Click the **Permissions** tab.

3. Click **Add**, select the member you want to grant permission, and
   then click **Add**  again.

4. Select the permission type that will work best for the user.

| Role              | Permission                                                                                                                                   |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Owner             | Create, read, modify, and delete all items and files. Create subfolders. Change the permission levels that other people have for the folder. |
| Publishing Editor | Create, read, modify, and delete all items and files. Create subfolders.                                                                     |
| Editor            | Create, read, modify, and delete all items and files.                                                                                        |
| Publishing Author | Create and read items and files. Create subfolders. Modify and delete items and files that you create.                                       |
| Author            | Create and read items and files. Modify and delete items and files that you create.                                                          |
| Nonediting Author | Create and read items and files. Delete items and files that you create.                                                                     |
| Contributor       | Create items and files only.                                                                                                                 |
| Reviewer          | Read items and files only.                                                                                                                   |
| Custom            | Perform activities defined by the folder owner.                                                                                              |
| None              | You have no permission. You cannot open the folder.                                                                                          |
                                                                                                                                                       

**Note:** You might see a several groups on the **Permissions** tab.
That is normal. It is important to leave these groups intact so that we
can help you if you need help. There are also two special groups called
**FolderAdmins** and **FolderUsers**. These groups allow you to set permissions
for all of your public folder administrators or users at once.
