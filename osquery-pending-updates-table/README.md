# osquery-pending-updates-table

Example of finding all the apt packages that are waiting to be updated (that are known locally to apt). This query is slow, please don't run it too often.

This plugin could be improved to use Python libraries specifically for interacting with apt rather than subprocess.

The `source` column is particularly useful to filter e.g. security updates from other kinds of update, or to find updates to third party packages specifically.

This plugin assumes that your hosts are reliably able to run `apt update` at least semi-frequently.


```
osquery> select * from pending_updates where source like '%security%';
+------+---------------------+---------------------+-----------------------------------------------------------+
| name | installed           | pending             | source                                                    |
+------+---------------------+---------------------+-----------------------------------------------------------+
| git  | 1:2.17.1-1ubuntu0.5 | 1:2.17.1-1ubuntu0.7 | Ubuntu:18.04/bionic-updates, Ubuntu:18.04/bionic-security |
+------+---------------------+---------------------+-----------------------------------------------------------+
osquery> select * from pending_updates where source not like '%Ubuntu%'; 
+-------------------+--------------------+--------------------+----------------------------+
| name              | installed          | pending            | source                     |
+-------------------+--------------------+--------------------+----------------------------+
| pdns-backend-pipe | 4.2.1-1pdns.bionic | 4.2.2-1pdns.bionic | PowerDNS:repo.powerdns.com |
+-------------------+--------------------+--------------------+----------------------------+

```
