# osquery-virsh-vms-table

List all of the VMs that are known to virsh (part of libvirt-clients).
                                                                                        
This plugin could be improved to use Python libraries specifically for interacting with libvirt rather than subprocess.

This table is useful to build parent / child relationships between VM hosts and VMs in your environent as the UUID returned here for a guest should match the UUID returned inside the guest from `system_info.uuid` (though the case may not match).

```
# On the VM host:
osquery> select name, lower(uuid) as uuid from virsh_vms;
+-----------+--------------------------------------+
| name      | uuid                                 |
+-----------+--------------------------------------+
| example-a | 981b27a1-8b51-4bd5-a4b7-b099b237c394 |
| example-b | d1d220e3-8abc-40bc-a969-580c9469e9d1 |
| example-c | 9db2a112-6daf-44a3-961e-d9b0f7c32cb5 |
| example-d | 48f60ae8-eb82-46b8-8a6a-49246ee76386 |
+-----------+--------------------------------------+

# Then inside the 'example-d' VM:
osquery> select lower(uuid) as uuid from system_info;
+--------------------------------------+
| uuid                                 |
+--------------------------------------+
| 48f60ae8-eb82-46b8-8a6a-49246ee76386 |
+--------------------------------------+
```
