---
node_id: 548
title: File permissions on Cloud Sites
type: article
created_date: '2011-03-16'
created_by: Rackspace Support
last_modified_date: '2016-01-15'
last_modified_by: Nate Archer
product: Cloud Sites
product_url: cloud-sites
---

<p><a id="Foreward" name="Foreward"></a>Directory permissions in a shared environment are exponentially more important than in a dedicated environment. A shared environment uses shared resources, and to keep those resources protected, you must enforce strong file-level access controls. Cloud Sites treats content storage as a UNIX file system. UNIX file permissions can set <em>who</em> can access a file and <em>what</em> that access level is.</p>

<h3><span class="mw-headline">Who can access files? </span></h3>

<p>Who can access files is divided into three categories: user, group, other.</p>

<ul>
	<li><em>User</em>, abbreviated as <em>U</em> is generally the person who created the file. Another common term for user is <em>owner</em>.</li>
	<li><em>Group</em>, abbreviated as <em>G</em> is anyone who belongs to the same group to which the file is assigned. By default, when a file is created it inherits the same group membership as the default group of the creator.</li>
	<li>Other, abbreviated as <em>O</em>, is everyone else and is often referred to as ‘world’, because it’s the rest of the world. User, group, and other are collectively referred to as ‘UGO’.</li>
</ul>

<p><a id="The_What" name="The_What"></a></p>

<h3><span class="mw-headline">What can they access? </span></h3>

<p>The access level is divided into three categories: read, write, execute. Collectively, these are referred to as <em>RWX</em> (X for execute). These attributes have a slightly different context for files than for directories.</p>

<p>For a file, read is the access to view the contents, write is access to modify the contents, and execute is the ability to execute the file.</p>

<p>For a directory, read is access to list the contents of the directory, write is access to add or remove entries from the directory, and execute is access to traverse the directory. If you think of a directory as nothing more than a special file that contains directory entries, then read and write make more sense. Having write access to a directory allows you to add or remove entries, but does not mean that you can edit the contents of the file, which would require write access to the file. The execute access on a file controls two things. If a directory is not set to execute, then you can't change directory (cd) to it. Also, if a directory is not set to execute, you do not have access to change to any directory below it, regardless of those directories' permissions.</p>

<p><img alt="" border="2" height="151" src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/fileperms1a.png" width="546" /></p>

<p><a id="Representing_Access_with_Numbers" name="Representing_Access_with_Numbers"></a></p>

<h3><span class="mw-headline">Representing access with numbers </span></h3>

<p>Three digits represent all file access controls for UGO, one digit for each. The RWX are included in a single, three-bit wide digit by using a technique called <em>bit-mapping</em>. In bit-mapping, each bit has special meaning that represents a value of either ON or OFF. The following illustration provides a quick overview of binary notation.</p>

<p><img alt="" border="2" height="" src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/fileperms2.png" width="600" /></p>

<p>The three access levels are assigned to a single to bit in the following order, from high to low: read write execute. Three bits (binary digits) can represent any eight values from 0-7. A range from 0-7 is called octal, as opposed to dealing with 0-9, which is called decimal. Read is in the 4’s column. Write is in the 2’s column. Execute is in the 1’s column. The following table provides a reference:</p>

| Ocal | Read | Write | Execute |
| ---- | ---- | ----- | ------- |
| 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 |
| 2 | 0 | 1 | 0 |
| 3 | 0 | 1 | 1 |
| 4 | 1 | 0 | 0 |
| 5 | 1 | 0 | 1 |
| 6 | 1 | 1 | 0 |
| 7 | 1 | 1 | 1 |

<p>Each entity with access (who) is given one of these octal bit-maps in the following order from high to low: User Group Other. So each <em>who</em> has a way to represent, in octal, the read, write, and execute access for it. The following graphic provides an illustration:</p>

<p><img alt="" height="" norder="2" src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/fileperms3.png" width="600" /></p>

<p>A single octal digit represents the RWX ON and OFF values. Three of these octal values represent all three of the ‘who’. So, the number 777, is not literally seven hundred-seventy-seven, it is actually 7, 7, and 7, where each octal digit indicates that all three bits have been set ON (4+2+1 = 7), thus giving full permissions to User, Group and Other.</p>

<p><a id="File_Creation" name="File_Creation"></a></p>

<h3><span class="mw-headline">File creation </span></h3>

<p>When a file is created, it takes its owner as the person who created the file, and its group is the default group of the user who created the file. The permissions are set against a mask that might specify whether certain bits, and thus permissions, should be turned OFF by default. Most services, such as FTP or Bash, mask OFF the world writable bit, making it impossible to create a file that is world writable. The Rackspace Cloud Sites FTP and &nbsp;SFTP all behave in this manner. The owner can change the permissions after file creation to anything from 000 to 777. As a result, within the Rackspace Cloud Sites environment, there is usually no reason to give Other write permissions to any file or any directory.</p>

<p><a id="Cloud_Sites_Scenarios" name="Cloud_Sites_Scenarios"></a></p>

<h3><span class="mw-headline">Cloud Sites scenarios </span></h3>

<p>Cloud Sites is continually working to improve security. Following are a few special cases that you need to know about to properly secure files.</p>

<ul>
	<li>If you are using Cloud Sites only as a PHP solution, you can completely remove all Other permissions from all files and directories. So files could be 600 and directories could be 700.</li>
	<li>When you are using multiple FTP users to manage the content of the site, the Group permissions must be considered. FTP users are in the same group as the primary account owner. Their ability to access files is determined through the Group permissions, and in general they should be set the same as the User permissions. 770 is standard for directories, and 660 is standard for files.</li>
	<li>When you are using CGI, the CGI files must be set to Executable. So 700 or 770 is the standard for files in the <strong>cgi-bin</strong> directory.</li>
	<li>If you are using Cloud Sites classic ASP/.Net solution, we recommend that you use impersonation. Contact our Support for assistance with this.</li>
</ul>

<p>The following table provides a reference for each scenario.</p>

| Type | Permission | User | Group | Other | Description |
| ---- | ---------- | ---- | ----- | ----- | ----------- |
| **Directory** | 700 | RWX | --- | --- | Gives only the user (owner) full permission. This is a good option if you are not using FTP users. |
| **File** | 600 | RW- | --- | --- | Gives only the user full permissions to the file that is not a script or a binary. |
| **Directory** | 770 | RWX | RWX | --- | Gives the group and user full permissions. This is a good option if you are using FTP. |
| **File** | 660 | RW- | RW- | --- | Gives the group and user full permissions. |
| **File** | 700 | RWX | --- | --- | Gives the user full permissions and marks the file as an executable. |
| **File** | 770 | RWX | RWX | --- | Gives the user full permissions and marks the file as executable. |
| **Directory** | 755 | RWX | R-X | R-X | Gives the user full permissions and allows everyone else to traverse and list directory contents. Required when using .NET w/o impersonation. |
| **Directory** | 775	 | RWX | RWX | R-X | Gives full read write and execute permissions to both user and group, but limits access to read-only to all others. |
| **File** | 644 | RW- | R-- | R-- | Gives the user read and write permissions, and give reader permissions to group read and other. |
