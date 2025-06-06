# Scenario
You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure. 

Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.

# Project Description
The research team at my organization needs me to update the file permissions for files and directories within the `projects` directory. Currently, the permissions does not seem to reflect the correct authorizations that should be given. I should check and update these permissions to keep the systems secure. To complete this goal, I performed the following tasks:

# Check file and directory details
I first use
```
cd projects
```
To enter the `projects` directory. I then used
```
ls -la
```
to determine the existing permissions of files and directories inside this directory, including hidden files. The following screenshot shows the list of contents inside the directory (last column), the permissions for the respective files/directory (first column), the owner (`researcher2`), and the group it belongs to (`research_team`). Note that line 1 under "`total 32`" indicates the current directory (`projects`), and line 2 indicates the parent directory (`home`).

![](Images/C4M3/Screenshot%202025-05-24%20171237.png)

# Describe the permissions string
- **1st character**: The two possible characters that can go here is either a `d`, indicating that the entry is a directory, or a hyphen (`-`), indicating the entry is a regular file.
- **2nd-4th characters**: These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the user. When one of these characters is a hyphen (`-`) instead, it indicates that this permission is not granted to the user.
- **5th-7th characters**: These characters should be the same as the 2nd-4th characters, being either the read (`r`), write (`w`), and execute (`x`) permissions, but this time for the group instead of the user. Again, if it is a hyphen (`-`) instead, it means that the respective permission is not granted to the group.
- **8th-10th characters**: These characters should be the same as the 2nd-4th characters, and the 5th-7th characters, being either the read (`r`), write (`w`), and execute (`x`) permissions, but this time for all other users instead of the user or group. Again, if it is a hyphen (`-`) instead, it means that the respective permission is not granted to all other users.

For example, the file permissions for `project_k.txt` are `-rw-rw-rw-`. Since the first character is a hyphen (`-`), this indicates that `project_k.txt` is a file, not a directory. The second, fifth, and eighth characters are all `r`, which indicates that the user, group, and other all have read permissions. The third, sixth, and ninth characters are `w`, which indicates that the user, group, and other all have write permissions. No one has execute permissions for `project_k.txt`.

# Change file permissions
The organization determined that other shouldn't have write access to any of their files. Looking at the list, it seems only `project_k.txt` should not have the write access for all other users. I will use
```
chmod o-w project_k.txt
```
Which yields me the following result when running `ls -la`:

![](Images/C4M3/Screenshot%202025-05-24%20173020.png)

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The `chmod` command changes the permissions on files and directories. The first argument indicates what permissions should be changed, in this case, the minus (`-`) sign indicates I will remove write (`w`) permission from others (`o`), and the second argument specifies the file or directory. In this example, I removed write permissions from all other users for the` project_k.txt` file. After this, I used `ls -la` to review the changes.

## Change file permissions on a hidden file
The research team at my organization recently archived `project_x.txt`. They do not want anyone to have write access to this project, but the user and group should have read access. I will run the following command:
```
chmod u-w,g-w,g+r .project_x.txt
```
Which yields:

![](Images/C4M3/Screenshot%202025-05-24%20173704.png)

Here we can see that only `researcher2` has execute permissions. It was previously determined that the group had execute permissions, so I used the `chmod` command to remove them. The `researcher2` user already had execute permissions, so they did not need to be added.

# Change directory permissions
My organization only wants the `researcher2` user to have access to the drafts directory and its contents. This means that no one other than `researcher2` should have execute permissions. I will run the following command:
```
chmod g-x drafts
```
Which yields:

![](Images/C4M3/Screenshot%202025-05-24%20174017.png)

Here we can see that only `researcher2` has execute permissions. It was previously determined that the group had execute permissions, so I used the `chmod` command to remove them. The `researcher2` user already had execute permissions, so they did not need to be added.

# Summary
Here I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the `projects` directory. I was basically using `ls -la` to check the permissions for the directory -- this informed my decisions in the following steps. I then used the `chmod` command to change the permissions on files and directories.