# Cybersecurity
My Cybersecurity Portfolio. 
This project is initialized with Google Cybersecurity course. 
This project will also include contents learned from Fullstack.
This project will include walkthroughs for Hack The Box. 
This project will have write-ups written in the Medium.com platform. 

## Manage Authorization
### Checking the details of the files and directories
This project is about Exploring Permissions in a directory and file. This project is from the Google Cybersecurity activity. This lab starts with the **home** directory, the user is **researcher2**, and the group is **research_team**. 
After navigating to the **projects** directory, I listed the contents and permissions of the **projects** directory. The permissions of the files in **projects** are listed below:
![Screenshot of commands to list permissions of different files in the project file.](https://github.com/mshahrin/Cybersecurity/assets/25282034/6a2e0683-32fd-4d18-b41a-9293dda388ac)
`drwxrwxrwx` is a 10 character string which indicates the permissions on the files are set. If the directory has full permissions for all owner types such as User, Group, and Other, then the permissions will display drwxrwxrwx. 
The `d` stands for directory. `r` stands for Read permission. `w` stands for Write permission. `x` stands for Execute if an execution is acceptable by the file. 
When there is no `d` and it's replaced with a hyphen (-) then the file is regular. 
When the read, write, and execute is replaced with a hyphen then the user, group, or other does not have permission for the file or directory. 
Was able to find the hidden file .project_x.txt by entering the command `ls -la` that lists all the hidden permissions. 

### Change file permissions
We are able to see a file, **project_k.txt** in the **projects** directory that has write permission for the owner, other. 
![Screenshot of commands that list permissions of files](https://github.com/mshahrin/Cybersecurity/assets/25282034/fe323013-8a11-4b8d-91b9-e6be0e88b660)
To change the permission of the owner of other in the **project_k.txt** file, we need to use:
`chmod o-w project_k.txt`
**project_m.txt** has the permission `-rw-r-----` and it is a restricted file that shouldn't be read. The group permission of the **project_m.txt** is read only. Used `chmod g-r project_m.txt` to remove the read permission on the group of the **project_m.txt** file. 

### Change file permissions on a hidden file
If a there is a hidden file that has incorrect permissions then change the permissions as needed. This action will to change the permissions will remove unauthorized access and make the security stronger. 
The hidden file that has a dot in front of it is the symbol for a hidden file. The file **.project_x.txt** is a hidden file that has been archived and shouldn't have write permission. It's ok if the user and group having permission to read the file. Upon checking **.project_x.txt** file, the file has `-rw--w----` no permission for other, write permission for group, and read and write permissions for the user. 
In order for the user and group to have only read permission, we need to remove the write permission by using the command `chmod u-w .project_x.txt` , `chmod g-w .project_x.txt` , and `chmod g+r .project_x.txt`. The final result for the file is `-r--r-----` .

### Change directory permissions
There is a **drafts** directory in the projects directory. The group permissions for the drafts directory is `drwx--x---`
The group has permission to execute the directory. To remove the execute, we can `chmod g-x drafts` and the directory will only have read, write, and execute permissions to the user only. 

This page explains how to examine file and directory permissions as well as change permissions on files and directories. 

## To conclude 
