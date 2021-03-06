## Permission Management
Accessing clients must be in the same network with the file system. Permission groups can be configured to further control the access permission and read and write permissions of the clients.

### Creating a permission group
Click **Create** to create a permission group under the Permission Group tab.
![](https://mc.qcloudimg.com/static/img/97e13cd68ef5222536a0fef699cf41c7/image.png)

Set a name and note for the permission group in the popup window.
![](https://mc.qcloudimg.com/static/img/384cd8ccc219798ffd7eb1cef7c3018e/image.png)

### Managing permission group rules
You can add, edit or delete rules in the rule list. If no rule is added to the permission group, all IPs in your network are allowed.

Accessing Address: You can enter a single IP or a single IP address range, such as 10.1.10.11 or 10.10.1.0/24. * indicates that all IPs are allowed. Please note that the IP entered should be CVM's private IP.
Read and Write Permissions: Read-only or read and write permissions. 
User Permission: You can select one of the following 4 options to control the permissions of accessing users. **Note: This permission option is not supported for CIFS/SMB file systems and will not take effect after configured.**

* 	all_squash: All access users are mapped as anonymous users or user groups.
* 	no_all_squash: Access users will match local users first and be mapped to anonymous users or user groups after matching failed.
* 	root_squash: Map access root users to anonymous users or user groups.
* 	no_root_squash: Access root users keep root account permission.

**Note: The default permission for each file system is 755, and nfsnobody users do not have write permission. We recommend that you select no_root_squash if there is no special requirements.**

**If you create a file directory and mount a file system as a root user, and set all_squash or root_squash for accessing IPs, the accessing IPs can only read the files (because the mount path is configured with root permission and the accessing IPs are mapped as anonymous users).**

Priority: You can configure an integer from 1-100 as the priority level, where 1 indicates the highest priority. When the permission of a single IP conflicts with that of an IP address range containing this single IP in the same permission group, the permission with a higher priority shall prevail. If the priority is the same, the permission of the single IP shall prevail. If two IP address ranges that have overlaps are configured with different permissions but the same priority, the permissions of the overlapped range will take effect randomly. Please avoid configuring IP address ranges with overlaps. **Note: Priority configuration is not supported for CIFS/SMB file systems and it will not take effect after configured.**
![](https://mc.qcloudimg.com/static/img/1c2662c3a4ab972aa4f1cdc42806116b/image.png)


### Configuring a permission group for the file system

* You can create a permission group in advance and select it when creating a file system.
* You can also select the default permission group when creating a file system and modify it in the file system details page after the creation.

**Note: If the file system is mounted using the NFS v4 protocol, the modification to the permission group rules of the file system will take effect in 2 minutes.**

![](https://mc.qcloudimg.com/static/img/b22d7373fb7838ed63b8a176f4616461/image.png)

### Modifying permission group information
You can modify the name and the note of the permission group in the permission group details page.
![](https://mc.qcloudimg.com/static/img/1a738d689985e7d85daf72422b707929/image.png)


