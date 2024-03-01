# LinuxFilePermissionsPortfolio

File permissions in Linux

Project description

Upon examination of the file permissions on the research team’s system. It is found that certain group members have more permissions than they need to. According to the principle of least privilege these permissions will be assessed and given as required by the members. 
Check file and directory details
The original permissions of the projects directory are as follows:

![1](https://github.com/RafUrera/LinuxFilePermissionsPortfolio/assets/161657613/76fe2238-5ec3-4b0d-bc7b-89bc76a7ba24)

Using the command ls -la displays all the files in the projects directory including hidden files. Notably, there is a drafts directory, a hidden file named .project_x.txt, and four other project files. The first 10 characters of each line of text displays the permissions of each directory or file on display.
Throughout the document the command chmod will be used. This command will allow changes to the permissions of a file or document to be changed. This is used to either give or deny a user type access to a file or directory. 
Describe the permissions string
The permission string is a 10 character string that displays the permissions for each file indicating which users can access or manipulate the file. An explanation of the string are as follows:
The First Character - Represented by the letter d or a hyphen - , this can either indicate the file type of a directory (d) or a regular file (-). 
Note on characters 2-10: The following characters use the same 4 possible characters of r , w ,  x , or a -. 
r means that the user type has read permissions for the file, meaning they can view the file. 
w means that the user type has write permissions meaning they edit the directory or file. 
x means that the user type has execute permissions meaning they view the directory or they can execute the file.
- means that the user type does not have the permission type.
2nd-4th Characters - The User’s read, write, and execute permissions represented by rwx , a hyphen indicates the user type does not have that permission.
5th-7th Characters - The Group’s read, write, and execute permissions represented by rwx , a hyphen indicates the user type does not have that permission.
8th-10th Characters - The Other’s read, write, and execute permissions represented by rwx , a hyphen indicates the user type does not have that permission.


Change file permissions
According to company policy the user type ‘other’ should not have write access to any of the files. In reference to the original permissions, project_k.txt must have its write permission removed for the ‘other’ user type.
This is done by using the command chmod o-w projects_k.txt which changes the permissions for the specified file. 

![2](https://github.com/RafUrera/LinuxFilePermissionsPortfolio/assets/161657613/bd1c1247-d3d8-4cf3-b7e1-6ebbd16887ed)

The command ls -la displays the permissions, which ensures that the permissions were changed correctly.

Change file permissions on a hidden file

Another change that must be made is for the hidden file .projects_x.txt which is an archived file. It should have read permissions to both the user and the group, but not write permissions to both. 
To correct the permissions for this file, the command chmod u-w,g-w,g+r .project_x.txt was used. This command removes the write permissions for both user types and gives the group permission to read the hidden file.

![3](https://github.com/RafUrera/LinuxFilePermissionsPortfolio/assets/161657613/a2fe2692-df06-42b3-a456-3ec75397852b)

Change directory permissions
The final change to be addressed is access to the directories. The drafts directory in particular should only be accessible to the user, researcher2. To correct the permissions the following command was used: chmod g-x drafts . This removes the execute permission from the group type users leaving only researcher2 as the only user with access to the directory.

![4](https://github.com/RafUrera/LinuxFilePermissionsPortfolio/assets/161657613/5b8a24f0-9217-4e66-8d4c-2cda102d5f0a)

Summary
The changes made in this document are as follows: 
Permissions for the files in the projects directory remain editable only to reseacher2 and the research group. 
Permissions for the hidden files are set to read only for appropriate users.
Permissions for the drafts directory are only accessible to the primary user, researcher2.
These permissions were all set using the chmod command and manually checked by using the ls -la command to display the permissions of files and directories.

