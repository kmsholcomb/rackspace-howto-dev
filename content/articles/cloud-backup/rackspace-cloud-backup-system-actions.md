---
node_id: 2036
title: Rackspace Cloud Backup - System Actions
type: article
created_date: '2012-08-22 17:23:38'
created_by: David Hendler
last_modified_date: '2015-12-31 14:1917'
last_modified_by: stephanie.fillmon
product: Cloud Backup
body_format: tinymce
---

### Previous section

[Rackspace Cloud Backup - Backup
actions](https://www.rackspace.com/knowledge_center/article/rackspace-cloud-backup-backup-actions-0)

How to Use System Actions
-------------------------

**Important**: The system actions are for users who are familiar with
Rackspace Cloud Backup. Users with Managed Cloud Service Level accounts
might want to contact their account manager before performing any of the
following actions.

You may perform several actions on your system. This article describes
them.

You can access the System Actions drop-down menu from the gear widget
next to the system name on the Systems List or from the "Actions" button
on the System Details Screen. This menu is *not* the one that appears on
the Single Backup screens.

The System Actions menu offers the following actions:

-   [Create Backup](#createbackup)
-   [Restore Backup](#restorebackup)
-   [Encrypt System](#encryptsystem)
-   [Cleanup System](#cleanupsystem)
-   [Disable System](#disablesystem)
-   [Delete System](#deletesystem)

 

#### Create Backup

Clicking **Create Backup** from the System Actions menu is the same as
clicking Create Backup on the system screen. For complete instructions,
see [Create a
Backup](http://www.rackspace.com/knowledge_center/article/rackspace-cloud-backup-create-a-backup-0)
in this guide.

-   Note: You cannot back up restore a system that is offline. If the
    system status displays&ldquo;offlin&rdquo; and your server is active, contact
    support.

 

#### Restore Backup

Clicking **Restore Backup** from the System Actions menu is the same as
clicking Restore Backup from the Single Backup Action menu. For complete
instructions, see [*Restore
Backup*](http://www.rackspace.com/knowledge_center/article/rackspace-cloud-backup-backup-actions-0#restorebackup)
in this guide.

-   Note: You cannot back up or restore to a system with an offline
    status. If the system status displays&ldquo;offlin&rdquo; and your server is
    active, please contact support.

 

#### Encrypt System

You may encrypt your backups with AES-256 encryption. The key or
passphrase you that create is known only to you. If you lose or forget
your passphrase, you cannot recover your backups.

Let's state that again:

### If you lose or forget your passphrase, you cannot recover your backups.

Also, after you turn on encryption, **you cannot turn it off**. You can
only change your passphrase. This is a security measure. If anyone ever
gained access to your account, they would not be able to access your
backups without your passphrase.

When you use a passphrase, we encrypt it locally on your browser using a
javascript RSA library before it is even submitted over the web.
Rackspace will never know your passphrase. All communication between
your computer and Rackspace servers for Cloud Backup is done over SSL,
which means that no one can intercept and read your messages.

To encrypt your backups, perform the following steps:

1.  From the Systems Actions menu, select **Encrypt**.

![RCBU Encryption - Enter
passphrase](http://www.rackspace.com/knowledge_center/sites/default/files/field/image/rcbu_begin_encryption.png)

2.  Enter a passphrase that only you know.
3.  Enter your passphrase again.
4.  Click **Save Passphrase**.

You can confirm that you have enabled encryption by clicking
**Encrypt...**from the System Actions. On the Backup encryption screen,
your system name will have the encrypted flag next to it. Also, your
encrypted backups will display "This is an encrypted backup," on the
Single Backup Details screen.

You can change your passphrase for encryption as follows:

1.  Select **Encrypt...**from the System Actions.
2.  Enter your current passphrase.
3.  Enter a new passphrase that only you know.
4.  Enter your new passphrase again.
5.  Click **Save Passphrase**.

 

#### Cleanup System

The Cleanup Vault allows you to manually start a cleanup at any time,
even if you have an automatic backup scheduled. A cleanup frees unused
space in your Cloud Files account, where you backups are stored.

1.  If your system is encrypted, confirm your passphrase when
    prompted**.**
2.  After you enter your passphrase, click the**Check** button.

 

#### Disable System

When you disable a system, you prevent all future backups from running.
You can re-enable the system at any time and no data will be deleted. To
re-enable the system, select Enable System from the System Actions menu.

 

#### Delete System

The Delete System command permanently deletes all backups and any data
associated with this system. A confirmation prompt requires you to
verify that this is your intention.

### Next steps

[Rackspace Cloud Backup -
Preferences](http://www.rackspace.com/knowledge_center/article/rackspace-cloud-backup-preferences-0)
