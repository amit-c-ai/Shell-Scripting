# File Permissions/Access modes

   Three types of permissions

    1) Owner Permission : The owner's permissions determine what actions the owner of the
			  file can perform on the file.

    2) Group Permission : The group's permissions determine what actions a user, who is a
		          member of the group that a file belongs to, can perform on the file.

    3) Other(world) Permission : The permissions for others indicate what action all other users
			       can perform on the file.

   Permission indicator

   ls -l command

    $ls -l /home/amit
    -rwxr-xr--  1 amit   users 1024  Nov 2 00:10  myfile
    drwxr-xr--- 1 amit   users 1024  Nov 2 00:10  mydir

   First column of output

   * The first three characters (2-4) represent the permissions for the file's owner. For example,
     **-rwxr-xr--** represents that the owner has read (r), write (w) and execute (x) permission.

   * The second group of three characters (5-7) consists of the permissions for the group to which the
     file belongs. For example, **-rwxr-xr--** represents that the group has read (r), execute (x) permission,
     but no write permission.

   * The last group of three characters (8-10) represents the permissions for everyone else. For example,
     **-rwxr-xr--** represents that there is read (r) only permission.

   File access modes

   * Read : able to view the contents of the file.

   * Write: able to edit the contents of the file.

   * Execute : able to run the file as program.

   Directory access modes

   * Read : read the contents, able to look at the filenames in directory.

   * Write : able to add or delete files from the directory.

   * Execute : Executing a directory doesn't really make sense, so think of this as a traverse permission.
	       A user must have execute access to the bin directory in order to execute the ls or the cd command.

   Changing Permissions

   We can use chmod(change mode) command. There are two ways to use chmod :
   * Symbolic mode

   * Absolute mode

   Using chmod in symbolic mode

   | Sr. no. | chmod operator & description |
   |---|---|
   | 1 | + (Adds the designated permission(s) to a file or directory.) |
   | 2 | - (Removes the designated permission(s) to a file or directory.) |
   | 3 | = (Sets the designated permission(s)) |

   Example using testfile :

    $ls -l testfile
    -rwxrwxr--  1 amit   users 1024  Nov 2 00:10  testfile

    $chmod o+wx testfile
    $ls -l testfile
    -rwxrwxrwx  1 amit   users 1024  Nov 2 00:10  testfile

    $chmod u-x testfile
    $ls -l testfile
    -rw-rwxrwx  1 amit   users 1024  Nov 2 00:10  testfile

    $chmod g = rx testfile
    $ls -l testfile
    -rw-r-xrwx  1 amit   users 1024  Nov 2 00:10  testfile

   We can combine these in one line as

    $chmod u-x,o+wx,g=rx testfile
    $ls -l testfile
    -rw-r-xrwx  1 amrood   users 1024  Nov 2 00:10  testfile

   Using chmod in Absolute mode

   | Number | Octal permission representation | Ref |
   |---|---|---|
   | 0 | No permission | --- |
   | 1 | Execute permission | --x |
   | 2 | Write permission | -w- |
   | 3 | Write and Execute permission (write(2) + execute(1)=3) | -wx |
   | 4 | Read permission | r-- |
   | 5 | Read and Execute permission (read(4) + execute(1)=5) | r-x |
   | 6 | Read and Write permission (read(4) + write(2)=6) | rw- |
   | 7 | All permissions (read(4) + write(2) + execute(1)=7) | rwx |

   Example using the testfile :

    $ls -l testfile
    -rwxrwxr--  1 amit   users 1024  Nov 2 00:10  testfile

    $ chmod 755 testfile
    $ls -l testfile
    -rwxr-xr-x  1 amit   users 1024  Nov 2 00:10  testfile

    $chmod 743 testfile
    $ls -l testfile
    -rwxr---wx  1 amit   users 1024  Nov 2 00:10  testfile

    $chmod 043 testfile
    $ls -l testfile
    ----r---wx  1 amit   users 1024  Nov 2 00:10  testfile

   Changing owners and groups

   * chown − The chown command stands for "change owner" and is used to change the owner of a file.

   * chgrp − The chgrp command stands for "change group" and is used to change the group of a file.

    $chown user filelist 

   The value of the user can be either the name of a user on the system or the user id (**uid**) of a user on the system.

    $chown amit testfile	//changes the owner of testfile to amit

   **NOTE** − The super user, root, has the unrestricted capability to change the ownership of any file but
              normal users can change the ownership of only those files that they own.

   Changing group ownership has the same procedure just commnad is **chgrp**.








