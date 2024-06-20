# File/Directory Permissions on Linux

## Project Description 
The goal is to update the file permissions and directory permissions within the project's directory. To keep the system secure it is important to make sure the correct permissions and given to each user, group, and others. 

## Check file and directory details
The following code demonstrates how I used Linux commands to determine the existing
permissions set for a specific directory in the file system.

<img width="644" alt="AD_4nXdpGX7o3tXfd78MQdCK2XAo8gzj8gRaec1ykf93lPNlRl9UpEmugOPZvQNds28xdec1rf_aHf8NjG4o1IEw3LbLOF6KT2CRQSS_YwM4m6ifd5K_OsofaJqT" src="https://github.com/SteveSunny46/File-Directory-Permissions-on-Linux/assets/171859383/2362f135-a35b-4358-8d6e-54a682786c9b">

- The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the project's directory. I used the ls command with the
-la option to display all files and directories and their permissions including any hidden files. The output of my command indicates that there is one directory named drafts, one hidden file
named .project_x.txt, and five other project files. The 10-character string in the first
column represents the permissions set on each file or directory.

## Describing the permissions string
The 10-character permission strings on each file and directory indicates the permissions allowed for the users, groups, and others. 

When the first character is a “d” it indicates that it is a directory, on the other hand, if it displays a “-”, it indicates that it is a file. 

Following the first character, the next 3 characters are assigned to the user permissions. Then the 3 characters after the user permissions would be the group permissions and finally, the last 3 characters would be the other user(s). 

For this part of the string, if there is a “-” it would indicate that the user does not have permission. If there is a letter there, it would indicate the following: 

- r = Read permission 
- w = Write permission 
- x = Execute permission


## Change file permissions

The organization determined that no “other” group should have the write permission. I determined project_k.txt  must have the write access removed for "other".

The following code demonstrates how I used Linux commands to do this:

<img width="644" alt="AD_4nXf94LjFC17_7SxLiaFcXI2GjOqflrHRl9MHqPCuXb2b6nYbi-ut5Pt75Xr0wQstpubz4ufQhZLaJbSo77JfxhO_TnIqYbxdF4LRfLEHk8CppoD0D5cEIikp" src="https://github.com/SteveSunny46/File-Directory-Permissions-on-Linux/assets/171859383/ee2018f3-5b44-49cd-9686-9bf0af854963">

- The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The “chmod” command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the project_k.txt file. After this, I used ls -la to check to see if the permission was updated accordingly. 

## Change file permissions on a hidden file
The research team at the organization recently archived  .project_x.txt They do not want anyone to have write access to this project, but the user and group should have read access. 

The following code demonstrates how I used Linux commands to change the permissions:

<img width="644" alt="AD_4nXeLzWm8SMCiW7xxTfwd93SsXxgFgtLIBTlGImXN40xBmoYn--exh99emVlwD2CdaHxM2AwgWjwz-cQHtxTVoBM8-7jRv5_vHVk3dIce4H05IVO9TGUrvBoC" src="https://github.com/SteveSunny46/File-Directory-Permissions-on-Linux/assets/171859383/c3eab582-6ad8-4f2b-b49d-c284bf9beb13">

- The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know  .project_x.txt  is a hidden file because it starts with a period (.). In this example, I removed write permissions from the user and group and added read permissions to the group. Using “chmod u-w,g-w,g+r .project_x.txt” allowed me to remove the write permissions for the user and group and add the read permission for the group. 

## Change directory permissions

The organization only wants the researcher2 user to have access to the drafts directory and its contents, meaning no one other than researcher2 should have execute permissions. In this case, the group had execute permissions which needed to be removed.

The following code demonstrates how I used Linux commands to change the permissions:

<img width="644" alt="AD_4nXdiXkLTWSqp9LBJkVRyJDa2BTLqPmmvXqgrLKJ5pR0qbn4t2VezFV0UeqKqMWjL3wmr6kULRTZJje-c0uPYg3ZFPI2PwkZjFHtnl4Mz5NsZyou1YR54fTu_" src="https://github.com/SteveSunny46/File-Directory-Permissions-on-Linux/assets/171859383/1e45f658-80b7-4369-8c52-28c2662ce367">

- The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I previously determined that the group had execute permissions, so I used the chmod permission to remove the group's access to the execute permission. 

## Summary

I changed multiple permissions to match the level of authorization the organization wanted for files and directories in the projects directory. The first step in this was using “ls -la” to check the permissions for the directory. This helped inform my decisions and make sure the appropriate permissions were granted. This was done by using the “chmod” code multiple times, accordingly to assign the correct permissions. 


