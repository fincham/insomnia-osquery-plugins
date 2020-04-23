# osquery-duo-config-table

Collects the non-sensitive parts of the Duo PAM configuration (if it is configured).

```
osquery> select * from duo_config;
+------------------------------+----------------------+----------+------------+----------+---------+
| host                         | ikey                 | failmode | http_proxy | autopush | prompts |
+------------------------------+----------------------+----------+------------+----------+---------+
| api-4d0443d6.duosecurity.com | DIF99YDXAKRAJMSO1PDV | safe     |            | no       | 3       |
+------------------------------+----------------------+----------+------------+----------+---------+
```

