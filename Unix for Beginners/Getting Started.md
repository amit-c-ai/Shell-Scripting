# Getting Started

   ### What is Unix?

    The Unix operating system is a set of programs that act as a link between the computer and the user.

    The computer programs that allocate the system resources and coordinate all the details of the computer's
    internals is called the operating system or the kernel.

   ### The main concept that unites all the versions of Unix is the following four basics :-

    Kernel − The kernel is the heart of the operating system. It interacts with the hardware and
             most of the tasks like memory management, task scheduling and file management.

    Shell − The shell is the utility that processes your requests. When you type in a command
            at your terminal, the shell interprets the command and calls the program that you want.
            The shell uses standard syntax for all commands. 

    Commands and Utilities − There are various commands and utilities which you can make use of
                             in your day to day activities. cp, mv, cat and grep, etc. are few examples
                             of commands and utilities.

    Files and Directories − All the data of Unix is organized into files. All files are then organized into
                            directories. These directories are further organized into a tree-like structure 
                            called the filesystem.

   ### Some Basic Commands :-

   Calendar

    $ cal

   Change Password

    $ passwd
    Changing password for itachi
    (current) Unix password:******
    New UNIX password:*******
    Retype new UNIX password:*******

   Listing Directories and Files

    $ ls		      	   //List directories and file in present directory
    $ ls -l		         //use a long listing format
    $ ls -G		         //in a long listing, don't print group names
    $ ls --help		   //get a list of all such commands

   Who are you?

    $ whoami

   Who logged in?

    $ users			   //list of users logged in to this system same time
    $ who			   //same details with time of login
    $ w		      	   //same details with some more information

   System Shutdown

    $ halt  		   //brings the system down immediately
    $ init 0	   	   //Powers off the system using predefined scripts to synchronize and clean up the system prior to shutting down
    $ init 6		   //Reboots the system by shutting it down completely and then restarting it
    $ poweroff 		   //Shuts down the system by powering off
    $ reboot	   	   //reboots the system
    $ shutdown		   //shuts down the system

