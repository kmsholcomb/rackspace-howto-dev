---
node_id: 4141
title: Access slow query and general logs for Cloud Databases
type: article
created_date: '2014-07-17'
created_by: Rose Contreras
last_modified_date: '2016-01-07'
last_modified_by: Nate Archer
product: Cloud Databases
product_url: cloud-databases
---

Database logs can be useful tools when analyzing database performance or troubleshooting issues. You can enable logging slow queries or general database activity for a MySQL Cloud Databases instance by attaching a configuration group to the instance with the appropriate parameters set.

## Prerequisites

The steps in this article require that you have an existing MySQL configuration group or create a new one. A MySQL configuration group holds the values for MySQL options used at startup. To learn more about MySQL configuration groups, see [Managing configuration groups for cloud databases with the Trove command line tool](/how-to/managing-configuration-groups-for-cloud-databases-with-the-trove-command-line-tool).

The examples use trove to make changes to configuration groups. Instructions for installing and configuring trove can be found in [Managing configuration groups for cloud databases with the Trove command line tool](/how-to/managing-configuration-groups-for-cloud-databases-with-the-trove-command-line-tool).

To apply configuration groups you will need to enable root access to the database instance. This can be done through the [Cloud Databases API](http://docs.rackspace.com/cdb/api/v1.0/cdb-devguide/content/POST_createRoot__version___accountId__instances__instanceId__root_Database_Instances.html) or with a trove command:

<pre>trove root-enable <em>instanceID</em></pre>

##Enable the slow query log

You can use the slow query log to find queries that take a long time to execute and are therefore candidates for optimization. You can access the MySQL slow query log by writing it to a table and setting persistent values to appropriate parameters in your configuration group.

For more information about the MySQL slow query log, see the [MySQL documentation on the slow query log](http://dev.mysql.com/doc/refman/5.6/en/slow-query-log.html).

To enable the logging of slow queries:

1.  Grant root access to the `mysql.slow_log` table.

2.  Set the configuration parameters that enable logging slow queries to the `mysql.slow_log` table:

	<table border="1">
		<tbody>
			<tr>
				<th>Parameter name</th>
				<th>Suggested value</th>
				<th>Description</th>
			</tr>
			<tr>
				<td><code>log_output</code></td>
				<td><code>'TABLE'</code></td>
				<td>Tells MySQL to write logs to a table</td>
			</tr>
			<tr>
				<td>slow_query_log</td>
				<td>1</td>
				<td>Enables the slow query log</td>
			</tr>
		</tbody>
	</table>

	For example, to create a new configuration group with trove that enables slow query logging, run:

        trove configuration-create EnableSlowQueryLog '{"log_output":"'TABLE'"}' --datastore MySQL

3.  Optionally, set the configuration parameters that define the conditions under which queries are written to the slow query log:

	<table border="1">
		<tbody>
			<tr>
				<th>Parameter name</th>
				<th>Suggested value</th>
				<th>Description</th>
			</tr>
			<tr>
				<td>long_query_time</td>
				<td>0 or more</td>
				<td>The duration of a query to be logged as slow, in seconds. The default is 10 seconds.</td>
			</tr>
			<tr>
				<td>log_queries_not_using_indexes</td>
				<td>0 or 1</td>
				<td>Whether or not to log slow queries that use indexes. &nbsp;Default is 0 (off)</td>
			</tr>
			<tr>
				<td>expire_logs_days</td>
				<td>0 to 99</td>
				<td>The number of days to keep logs before deletion. The default is 0 (no automatic removal).</td>
			</tr>
		</tbody>
	</table>

	For example, to add parameters to the configuration group created in the previous step that set the slow query duration to 15 seconds and cause logs to be deleted after one day, run:

	<pre>trove configuration-patch <em>configID</em> '{"long_query_time":15,"expire_logs_days":1}'</pre>

4.  If necessary, attach the configuration group with these parameters to the instance for which you want to enable slow query logging. To attach the configuration using trove, run:

	<pre>trove configuration-attach <em>instanceID</em> <em>configID</em></pre>

5.  After the configuration is applied to your server, you can retrieve the slow query log from the database with a query. For example:

		mysql -e "select * from mysql.slow_log order by start_time desc limit 1\G"

## Enable the general query log

You can use the general query log to track all activity, including any connections to the database and all queries sent to the database. It can be useful when you want to check the queries being sent by a client for troubleshooting purposes.

For more information about the MySQL general query log, see the [MySQL documentation on the general query log](http://dev.mysql.com/doc/refman/5.6/en/query-log.html).

### To enable the general query log

1.  Grant root access to the `mysql.general_log` table.

2.  Set the configuration parameters that enable logging server activity to the `mysql.general_log` table:

	<table border="1">
			<tbody>
				<tr>
					<th>Parameter name</th>
					<th>Suggested value</th>
					<th>Description</th>
				</tr>
				<tr>
					<td>log_output</td>
					<td>'TABLE'</td>
					<td>Tells MySQL to write logs to a table</td>
				</tr>
			</tbody>
		</table>

	For example, to create a new configuration group with trove that enables general query logging, run:

		trove configuration-create EnableGeneralLog '{"log_output":"'TABLE'","slow_query_log":1}' --datastore MySQL

3.  Optionally, set the configuration parameter that tells MySQL how long to keep logs.

	<table border="1">
				<tbody>
					<tr>
						<th>Parameter name</th>
						<th>Suggested value</th>
						<th>Description</th>
					</tr>
					<tr>
						<td>expire_logs_days</td>
						<td>0 to 99</td>
						<td>The number of days to keep logs before deletion. The default is 0 (no automatic removal).</td>
					</tr>
				</tbody>
			</table>

	For example, to add a parameter to the configuration group created in the previous step that will cause logs to be deleted after one day, run:

    <pre>trove configuration-patch <em>configID</em> '{"expire_logs_days":1}'</pre>

4.  If necessary, attach the configuration group with these parameters to the instance for which you want to enable general query logging. To attach the configuration using trove, run:

    <pre>trove configuration-attach <em>instanceID</em> <em>configID</em></pre>

5. After the configuration group is attached, you can now enable general logging by running this command:

    <pre>mysql -e "set global general_log = 1"</pre>

    At the moment, the above variable can only be set dynamically on a running instance due to the overwhelming amount of data this change may generate.

    You can also disable general log with this command:

    <pre>mysql -e "set global general_log = 0"</pre>

**Note:** General logging will be disable when you restart a MySQL instance.

6.  After the configuration is applied to your server, you can retrieve the general query log from the database with a query. For example:

        mysql -e "select * from mysql.general_log order by event_time desc limit 1\G"
