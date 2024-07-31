# Use Linux Commands to Manage File Permissions

## Scenario

You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure. 

Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.

## Objective

To demonstrate the ability to use Linux commands to manage file permissions. This includes checking current permissions, modifying them to meet organizational requirements, and ensuring that only authorized users have access.

### Skills Learned

- Examining file and directory permissions
- Modifying file and directory permissions
- Handling hidden files
- Ensuring security compliance

### Tools Used

<img src="https://img.shields.io/badge/-Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />

## Steps

### Step 1: Check File and Directory Permissions

I ran the `ls -l` command to list the permissions of files and directories. This command helped me see detailed information about each file and directory, including who owns them and what kind of access permissions are set.

![image4](https://github.com/user-attachments/assets/2a2f6031-4479-4d55-8bcc-8c3f2a5ec02b)

### Step 2: Describe the Permissions String

The output from `ls -l` includes 10-character permission strings (e.g. -rwxr-xr--). Here's how to interpret it:

| Character Position | Symbol | Description                                          |
|--------------------|--------|------------------------------------------------------|
| 1                  | `-` or `d` or `l` | Type: file (-), directory (d), link (l) |
| 2-4                | `rwx`    | Owner: read (r), write (w), execute (x) |
| 5-7                | `rwx`    | Group: read (r), write (w), execute (x) |
| 8-10               | `rwx`    | Others: read (r), write (w), execute (x) |

So, the permissions string of `-rwxr-xr--` means:
- `-`: File
- `rwx`: Owner can read, write, execute
- `r-x`: Group can read, execute
- `r--`: Others can read

### Step 3: Change File Permissions

I identified files where the permissions needed adjustments and used the `chmod` command to modify them. Specifically, I removed write permissions from others to ensure unauthorized users couldn’t make changes.

![image2](https://github.com/user-attachments/assets/bd5947d2-7725-4beb-b357-ba2cf02a2935)

### Step 4: Change File Permissions on a Hidden File

I adjusted permissions for the hidden file, `.project_x.txt`, using the `chmod` command to make sure everyone had the right level of access. Specifically, I set it so that only the owner and group could read the file, but no one could write to it.

![image3](https://github.com/user-attachments/assets/96098df3-fdb7-4bb3-b9a2-888f72f9ec49)

### Step 5: Change Directory Permissions

I made sure that only the specified user, `researcher2`, could access the `drafts` directory and its contents. I used the `chmod` command to set the permissions so that only the owner could access it.

![image1](https://github.com/user-attachments/assets/46c4b534-21d2-4259-a1a2-862ed495d253)

## Summary

I demonstrated how to manage file permissions using Linux commands. I started by checking the current permissions with the ls -l command, interpreting the permissions string to understand file and directory access. I then identified files and directories that needed permission changes and used chmod to adjust these permissions as required. This included removing write access for others, setting appropriate permissions for hidden files, and ensuring that only specific users could access certain directories.
