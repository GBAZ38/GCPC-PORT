# ACTIVITY 

A new employee with the username `researcher9` joins the organization. Add them to the system and continue to manage their access during their time with the organization.

##   FIRST: 

Add the new employee to the system and then assign their primary group.

## SECOND: 

Make the employee the owner of a file related to a particular project

## THIRD: 

Add the new employee to a supplementary group.

## FINALLY: 

Delete the employee from the system.

### NOTE: 

The lab starts with you logged in as user `analyst`, with your home directory, `/home/analyst`, as the current working directory.

---

To begin we start each command by using the `sudo` command to access super user privileges, followed by the `useradd` command followed by the username to create the new user on the system.

`sudo useradd researcher9`

To change the new user's primary group we use the command `usermod` followed by the `-g` option and the name of the group we want to assign(in our case `research_team`), and finish with the username.

`sudo usermod -g research_team researcher9`

To assign `researcher9` the ownership of the `project_r.txt` we use the `chown` command and list the files root directory `/home/researcher2/projects/project_r.txt`

`sudo chown researcher9 /home/researcher2/projects/project_r.txt`

To add the user into a secondary group we can use the `usermod` command again, but instead use the `-G` and `-a` options followed by the secondary group we wish to assign them, and the username.

`sudo usermod -a -G sales_team researcher9`

to remove the user from the system we can use the `userdel` command:

`sudo userdel researcher9`

After executing this command we get the following message:

`userdel: group researcher9 not removed because it is not the primary group of user researcher9.`

This is expected because Each time a new user is created in Linux, a group with the same name as the user is automatically created and the user is the only member of that group. It is good practice to clean up any empty groups after removing users.

To delet the empty group use the `groupdel` command:

`sudo groupdel researcher9`
