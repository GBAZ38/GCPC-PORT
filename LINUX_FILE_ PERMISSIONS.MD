# SCENARIO:

You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure. 

Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access. 

NOTE: This scenario involves investigating and updating the same file permissions as the ones in the Manage authorization lab( TOOLS OF THE TRADE: LINUX AND SQL / MODULE 3 / MANAGE FILE PERMISSIONS).

---

# STARTING FILE PERMISSIONS: 

This document displays the file structure of the '/home/researcher2/projects' directory and the permissions of the files and subdirectory it contains.

In the '/home/researcher2/projects directory', there are five files with the following names and permissions: 
- 'project_k.txt'
  - user = read, write, 
  - group = read, write, 
  - other = read, write, 
- 'project_m.txt'
  - user = read, write, 
  - group = read
  - other = none
- 'project_r.txt'
  - user = read, write, 
  - group = read, write, 
  - other = read
- 'project_t.txt'
  - user = read, write, 
  - group = read, write, 
  - other = read
- '.project_x.txt'
  - user = read, write, 
  - group = write, 
  - other = none

There is also one subdirectory inside the 'projects' directory named 'drafts'. The permissions on 'drafts' are: 
- user = read, write, execute
- group = execute
- other = none

---

# ACTIVITY:

## CHECK FILE AND DIRECTORY DETAILS

In the Manage authorization lab, check the permissions set for files and subdirectories in the 'projects' directory. Make sure you display all permissions, including hidden files.

To check the permissions set in the 'projects' directory, use the cd command: 
'cd projects' 
This allows us to move into '/home/researcher2/projects' and we can check this by typing 'pwd' to print the working directory. We then use the ls command with the l and a options: 
'ls -la' 
This lists subdirectories and files contained within the 'projects' directory including hidden files. The output should resemble:
![file_permissions1](/home/seb/Pictures/file_permissions1.png)
