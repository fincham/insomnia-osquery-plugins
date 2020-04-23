# osquery-cpu-vulnerabilities-table

Check the new (Jan 2018) sysfs CPU vulnerabilities table on the machine to determine the state of e.g. Spectre and Meltdown bug mitigations.

```
osquery> select * from cpu_vulnerabilities;
+-------------------+----------------------------------------------------------------------+
| name              | state                                                                |
+-------------------+----------------------------------------------------------------------+
| spectre_v2        | Mitigation: Enhanced IBRS, IBPB: conditional, RSB filling            |
| itlb_multihit     | Not affected                                                         |
| mds               | Not affected                                                         |
| l1tf              | Not affected                                                         |
| spec_store_bypass | Mitigation: Speculative Store Bypass disabled via prctl and seccomp  |
| tsx_async_abort   | Not affected                                                         |
| spectre_v1        | Mitigation: usercopy/swapgs barriers and __user pointer sanitization |
| meltdown          | Not affected                                                         |
+-------------------+----------------------------------------------------------------------+
```

