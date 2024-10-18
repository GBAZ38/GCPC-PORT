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

From this we can see what the current file permisions are. The first colum of each line contains the file type, permisssions for the user, group, and other. We can see that `.project_x.txt` is not a directory because the first letter in the string is a "-" instead of a "d". We can also see that the user has read and write permission, the group has write permission, and other has no permissions. The user permissions are represented by the 2nd - 4th characters "rw-". The group permissions are represented by the 5th - 7th characters "-w-".  The other permissions are represented by the 8th - 10th characters "---". We can see that the file is owned by the user "researcher2" in the second colum. The third colum tells us that the group owner of the file is "research_team".

---

## CHANGE FILE PERMISSIONS

The organization does not allow others to have write access to any files. Based on the permissions established in Step 3, identify which file needs to have its permissions modified. Use a Linux command to modify these permissions.

As per the organizations policy we need to change the write permissions for other on the file "project_k.txt" using the command
`chmod o-w project_k.txt`

