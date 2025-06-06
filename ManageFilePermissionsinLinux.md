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
