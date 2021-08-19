# Processes Management

   Whenever you issue a command in Unix, it creates, or starts, a new process. When you tried out the ls command
   to list the directory contents, you started a process. A process, in simple terms, is an instance of a running program.

   The operating system tracks processes through a five-digit ID number known as the **pid** or the **process ID**. Each process
   in the system has a unique pid.

   So at max 10^5 processes can run at a time.

   When you start a process (run a command), there are two ways you can run it :

   * Foreground process

   * Background process

   ## Foreground Process

   By default, every process that you start runs in the foreground. It gets its input from the keyboard
   and sends its output to the screen. For example ls command.

   While a program is running in the foreground and is time-consuming, no other commands can be run 
   (start any other processes) because the prompt would not be available until the program finishes 
   processing and comes out.

   ## Background Processes

   A background process runs without being connected to your keyboard. If the background process requires
   any keyboard input, it waits.

   The advantage of running a process in the background is that you can run other commands; you do not have
   to wait until it completes to start another!

   The simplest way to start a background process is to add an ampersand (&) at the end of the command :

    $ls *md &

   This displays all files ending with md. Output : 

    [1] 6439

    '1. Getting Starded.md'  '3. Directories.md'       '5. Environment.md'      '7. Pipes and Filters.md'
    '2. File Management.md'  '4. File Permissions.md'  '6. Basic Utilities.md'  '8. Processes.md'

    [1]+  Done                    ls --color=auto *md

   The first line tells the information about background processes (pid number). Then listing and the last line
   tells that background process is successfully completed.

   ## Listing Running Processes

   It is easy to see your own processes by running the ps (process status) command as follows :

    $ps
    PID       TTY      TIME        CMD
    18358     ttyp3    00:00:00    sh
    18361     ttyp3    00:01:31    abiword
    18789     ttyp3    00:00:00    ps

   One of the most commonly used flags for ps is the -f (f for full) option, which provides more information as shown below :

    UID      PID  PPID C STIME    TTY   TIME CMD
    amit   6738 3662 0 10:23:03 pts/6 0:00 first_one
    amit   6739 3662 0 10:22:54 pts/6 0:00 second_one
    amit   3662 3657 0 08:10:53 pts/6 0:00 -ksh
    amit   6892 3662 4 10:51:50 pts/6 0:00 ps -f

   Here is the description of all the fields displayed by ps -f command :

   | Sr. no. | field | description |
   |---|---|---|
   | 1 | UID | user ID that this process belongs to (the person running it) |
   | 2 | PID | process ID |
   | 3 | PPID | parent process ID (the ID of the process that started it) |
   | 4 | C | CPU usage of the process |
   | 5 | STIME | start time of process |
   | 6 | TTY | terminal type associated with the process |
   | 7 | TIME | CPU time taken by the process |
   | 8 | CMD | command that started the process |

   There are other options which can be used along with ps command :

   | Sr. no. | Option | Description |
   |---|---|---|
   | 1 | -a | shows information about all users |
   | 2 | -x | shows information of processes running outside of terminal |
   | 3 | -u | shows additional information like -f |
   | 4 | -e | shows extended information |

   ## Stopping Processes

   Ending a process can be done in several different ways. Often, from a console-based command, sending a CTRL + C
   keystroke (the default interrupt character) will exit the command. This works when the process is running in the 
   foreground mode.

   If a process is running in the background, you should get its Job ID using the ps command. After that, you can use 
   the kill command to kill the process as follows :

    $ps -f
    UID      PID  PPID C STIME    TTY   TIME CMD
    amit   6738 3662 0 10:23:03 pts/6 0:00 first_one
    amit   6739 3662 0 10:22:54 pts/6 0:00 second_one
    amit   3662 3657 0 08:10:53 pts/6 0:00 -ksh
    amit   6892 3662 4 10:51:50 pts/6 0:00 ps -f
    $kill 6738
    Terminated

   Here, the kill command terminates the first_one process. If a process ignores a regular kill command, you can use
   kill -9 followed by the process ID as follows

    $kill -9 6738
    Terminated

   ## Parent and Child Processes

    Each unix process has two ID numbers assigned to it: The Process ID (pid) and the Parent process ID (ppid). Each user
    process in the system has a parent process.

    Most of the commands that you run have the shell as their parent. Check the ps -f example where this command listed
    both the process ID and the parent process ID.

   ## Zombie and Orphan Processes

    Normally, when a child process is killed, the parent process is updated via a SIGCHLD signal. Then the parent can do
    some other task or restart a new child as needed. However, sometimes the parent process is killed before its child is
    killed. In this case, the "parent of all processes," the init process, becomes the new PPID (parent process ID).
    In some cases, these processes are called orphan processes.

    When a process is killed, a ps listing may still show the process with a Z state. This is a zombie or defunct process. 
    The process is dead and not being used. These processes are different from the orphan processes. They have completed
    execution but still find an entry in the process table.

   ## Daemon Processes

    Daemons are system-related background processes that often run with the permissions of root and services requests from
    other processes.

    A daemon has no controlling terminal. It cannot open /dev/tty. If you do a "ps -ef" and look at the tty field, all daemons
    will have a ? for the tty.

    To be precise, a daemon is a process that runs in the background, usually waiting for something to happen that it is capable
    of working with. For example, a printer daemon waiting for print commands.

    If you have a program that calls for lengthy processing, then it’s worth to make it a daemon and run it in the background.

   ## Top command

   The top command is a very useful tool for quickly showing processes sorted by various criteria.

   It is an interactive diagnostic tool that updates frequently and shows information about physical and virtual memory, CPU usage,
   load averages, and your busy processes.

   Here is the simple syntax to run top command and to see the statistics of CPU utilization by different processes :

    $top

   ## Job ID vs Process ID

    Background and suspended processes are usually manipulated via job number (job ID). This number is different from the process
    ID and is used because it is shorter.

    In addition, a job can consist of multiple processes running in a series or at the same time, in parallel. Using the job ID is 
    easier than tracking individual processes.








