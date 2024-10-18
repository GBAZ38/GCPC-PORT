# SCENARIO:

You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure. 

Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access. 

NOTE: This scenario involves investigating and updating the same file permissions as the ones in the Manage authorization lab( TOOLS OF THE TRADE: LINUX AND SQL / MODULE 3 / MANAGE FILE PERMISSIONS).

---

# STARTING FILE PERMISSIONS: 

This document displays the file structure of the `/home/researcher2/projects` directory and the permissions of the files and subdirectory it contains.

In the `/home/researcher2/projects directory`, there are five files with the following names and permissions: 
- `project_k.txt`
  - user = read, write, 
  - group = read, write, 
  - other = read, write, 
- `project_m.txt`
  - user = read, write, 
  - group = read
  - other = none
- `project_r.txt`
  - user = read, write, 
  - group = read, write, 
  - other = read
- `project_t.txt`
  - user = read, write, 
  - group = read, write, 
  - other = read
- `.project_x.txt`
  - user = read, write, 
  - group = write, 
  - other = none

There is also one subdirectory inside the `projects` directory named `drafts`. The permissions on `drafts` are: 
- user = read, write, execute
- group = execute
- other = none

---

# ACTIVITY:

## CHECK FILE AND DIRECTORY DETAILS

In the Manage authorization lab, check the permissions set for files and subdirectories in the `projects` directory. Make sure you display all permissions, including hidden files.

To check the permissions set in the `projects` directory, use the cd command: 

`cd projects` 

This allows us to move into `/home/researcher2/projects` and we can check this by typing `pwd` to print the working directory. We then use the ls command with the l and a options: 

`ls -la` 

This lists subdirectories and files contained within the `projects` directory including hidden files. The output should resemble:

![file_permissions1](/SCREENSHOTS/file_permissions1.png)

From this output, we can see what the current file permisions are. The first colum of each line contains the file type, permisssions for the user, group, and other. For example we can see that `.project_x.txt` is not a directory because the 1st character in the string is a `-` instead of a `d` and because of the `.txt` file extension in the name. The period in front of the file name tells us that this is a hidden file. The user permissions are represented by the 2nd - 4th characters `rw-`. The group permissions are represented by the 5th - 7th characters `-w-`.  The other permissions are represented by the 8th - 10th characters `---`. This lets us know that the user has read and write permission, the group has write permission, and other has no permissions. We can see that the file is owned by the user `researcher2` in the second colum. The third colum tells us that the group owner of the file is `research_team`.

---

## CHANGE FILE PERMISSIONS

The organization does not allow others to have write access to any files. Based on the permissions established, identify which file needs to have its permissions modified. Use a Linux command to modify these permissions.

As per the organizations policy we need to change the write permissions for other on the file `project_k.txt` using the command

`chmod o-w project_k.txt`

The research team has archived `.project_x.txt`, which is why it’s a hidden file. This file should not have write permissions for anyone, but the user and group should be able to read the file. Use a Linux command to assign `.project_x.txt` the appropriate authorization.

To change the permissions for the hidden file ".projext_x.txt" we use the commands

`chmod u-w .project_x.txt`

`chmod g-w .project_x.txt`

`chmod g+r .project_x.txt`

The files and directories in the `projects` directory belong to the `researcher2` user. Only `researcher2` should be allowed to access the `drafts` directory and its contents. Use a Linux command to modify the permissions accordingly.

To modify the permissions for the `drafts` directory we use the command

`chmod g-x drafts`

Now we can double check that all permissions have been successfully changeb by using the command

`ls -la`

This gives us the following output: 

![file_permissions2](/SCREENSHOTS/file_permissions2.png)

---

## SUMMARY

In this situation we were successfully able to follow the organizations policies and change the permissions of files and directories. Using the `ls` command with the `-la` option we're able to read file and subdirectory permissions while including hidden files. We then used the `chmod` command to target and change the permissions for different files. 
