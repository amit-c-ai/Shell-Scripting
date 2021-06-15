# Network Communitcation Utilities

   There are several Unix utilities that help users compute in a networked, distributed environment.
   This file lists a few of them.

   ## The Ping Utility

   The ping command sends an echo request to a host available on the network. Using this command, you
   can check if your remote host is responding well or not.

   The ping command is useful for the following :

   * Tracking and isolating hardware and software problems

   * Determining the status of the network and various foreign hosts

   * Testing, measuring and managing networks

   Syntax

    $ping hostname or ip address

   The above command starts printing a response after every second. To come out of the command, you can
   terminate it by pressing CNTRL + C keys.

   Example

    $ping google.com
    PING google.com(bom12s18-in-x0e.1e100.net (2404:6800:4009:82b::200e)) 56 data bytes
    64 bytes from bom12s18-in-x0e.1e100.net (2404:6800:4009:82b::200e): icmp_seq=1 ttl=117 time=77.8 ms
    64 bytes from bom12s18-in-x0e.1e100.net (2404:6800:4009:82b::200e): icmp_seq=2 ttl=117 time=74.2 ms
    64 bytes from bom12s18-in-x0e.1e100.net (2404:6800:4009:82b::200e): icmp_seq=3 ttl=117 time=71.7 ms
    64 bytes from bom12s18-in-x0e.1e100.net (2404:6800:4009:82b::200e): icmp_seq=4 ttl=117 time=73.1 ms
    64 bytes from bom12s18-in-x0e.1e100.net (2404:6800:4009:82b::200e): icmp_seq=5 ttl=117 time=87.9 ms
    64 bytes from bom12s18-in-x0e.1e100.net (2404:6800:4009:82b::200e): icmp_seq=6 ttl=117 time=87.7 ms
    ^C
    --- google.com ping statistics ---
    10 packets transmitted, 10 received, 0% packet loss, time 9014ms
    rtt min/avg/max/mdev = 71.784/81.049/88.512/6.101 ms

   If host does not exist, you'll get following output

    $ping giiiiigle.com
    ping: giiiigle.com: Name or service not known

   ## The ftp Utility

   Here, ftp stands for **F**ile **T**ransfer **P**rotocol. This utility helps you upload and download your file from
   one computer to another computer.

   The ftp utility has its own set of Unix-like commands. These commands help you perform tasks such as 

   * Connect and login to a remote host.

   * Navigate directories.

   * List directory contents.

   * Put and get files.

   * Transfer files as ascii, ebcdic or binary.

   Syntax

    $ftp hostname or ip address

   The above command would prompt you for the login ID and the password. Once you are authenticated, you can access
   the home directory of the login account and you would be able to perform various commands.

   The following table lists out a few important commands :

   | Sr. no. | Command | Description |
   |---|---|---|
   | 1 | put filename | uploads filename from the local machine to the remote machine |
   | 2 | get filename | downloads filename from remote the machine to the local machine |
   | 3 | mput file list | uploads more than one file from the local machine to the remote machine |
   | 4 | mget file list | downloads more than one file from remote the machine to the local machine |
   | 5 | prompt off | turns the prompt off. By default, you will receive a prompt to upload or download files |
   | 6 | prompt on | turns the prompt on |
   | 7 | dir | lists all the files available in the current directory of the remote machine |
   | 8 | cd dirname | changes directory to dirname on the remote machine |
   | 9 | lcd dirname | changes directory to dirname on the local machine |
   | 10 | quit | logout from the current login |

   Example

    $ftp amit.com
    Connected to amit.com.
    220 amit.com FTP server (Ver 4.9 Thu Sep 2 20:35:07 CDT 2009)
    Name (amit.com:amit): amit
    331 Password required for amit.
    Password:
    230 User amit logged in.
    ftp> dir
    200 PORT command successful.
    150 Opening data connection for /bin/ls.
    total 1464
    drwxr-sr-x   3 amit   group       1024 Mar 11 20:04 Mail
    drwxr-sr-x   2 amit   group       1536 Mar  3 18:07 Misc
    drwxr-sr-x   5 amit   group        512 Dec  7 10:59 OldStuff
    drwxr-sr-x   2 amit   group       1024 Mar 11 15:24 bin
    drwxr-sr-x   5 amit   group       3072 Mar 13 16:10 mpl
    -rw-r--r--   1 amit   group     209671 Mar 15 10:57 myfile.out
    drwxr-sr-x   3 amit   group        512 Jan  5 13:32 public
    drwxr-sr-x   3 amit   group        512 Feb 10 10:17 pvm3
    226 Transfer complete.
    ftp> cd mpl
    250 CWD command successful.
    ftp> dir
    200 PORT command successful.
    150 Opening data connection for /bin/ls.
    total 7320
    -rw-r--r--   1 amit   group       1630 Aug  8 1994  dboard.f
    -rw-r-----   1 amit   group       4340 Jul 17 1994  vttest.c
    -rwxr-xr-x   1 amit   group     525574 Feb 15 11:52 wave_shift
    -rw-r--r--   1 amit   group       1648 Aug  5 1994  wide.list
    -rwxr-xr-x   1 amit   group       4019 Feb 14 16:26 fix.c
    226 Transfer complete.
    ftp> get wave_shift
    200 PORT command successful.
    150 Opening data connection for wave_shift (525574 bytes).
    226 Transfer complete.
    528454 bytes received in 1.296 seconds (398.1 Kbytes/s)
    ftp> quit
    221 Goodbye.

   ## The Telnet Utility

   There are times when we are required to connect to a remote Unix machine and work on that machine remotely. Telnet 
   is a utility that allows a computer user at one site to make a connection, login and then conduct work on a computer
   at another site.

   Once you login using Telnet, you can perform all the activities on your remotely connected machine. The following is 
   an example of Telnet session :

    C:>telnet amit.com
    Trying...
    Connected to amit.com.
    Escape character is '^]'.
    
    login: amit
    amit's Password: 
    *****************************************************
    *                                                   *
    *                                                   *
    *    WELCOME TO AMIT.COM                            *
    *                                                   *
    *                                                   *
    *****************************************************

    Last unsuccessful login: Fri Mar  3 12:01:09 IST 2009
    Last login: Wed Mar  8 18:33:27 IST 2009 on pts/10

       {  do your work }

    $ logout
    Connection closed.

   ## The Finger Utility

   The finger command displays information about users on a given host. The host can be either local or remote.

   Finger may be disabled on other systems for security reasons.

   Following are the simple syntax to use the finger command.
 
   Check all the logged-in users on the local machine :

    $finger
    Login     Name       Tty      Idle  Login Time   Office     Office Phone
    amit      Amit      *:0             Jun 16 01:49 (:0)

   Get information about a specific user available on the local machine :

    $finger amit
    Login: amit           			Name: Amit
    Directory: /home/amit               	Shell: /bin/bash
    On since Wed Jun 16 01:49 (IST) on :0 from :0 (messages off)
    New mail received Wed Jun 16 01:46 2021 (IST)
         Unread since Thu Jun 10 15:57 2021 (IST)
    No Plan.

   Check all the logged-in users on the remote machine :

    $finger @avtar.com
    Login     Name       Tty      Idle  Login Time   Office
    amit               pts/0          Jun 25 08:03 (62.61.164.115)

   Get the information about a specific user available on the remote machine :

    $finger amit@avtar.com
    Login: amit                           Name: (null)
    Directory: /home/amit                 Shell: /bin/bash
    On since Thu Jun 25 08:03 (MST) on pts/0 from 62.61.164.115
    No mail.
    No Plan.















































