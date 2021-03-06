# Environment

   A variable is a character string to which we assign a value. The value assigned
   could be a number, text, filename, device, or any other type of data.

   ### PS1 and PS2 variable

   The characters that the shell displays as your command prompt are stored in the
   variable PS1. You can change this variable to be anything you want. As soon as you change
   it, it'll be used by the shell from that point on. 

   For example, if you issued the command :

    $PS1='=>'
    =>
    =>
    =>

    Your prompt will become =>.

   To set the value of PS1 so that it shows the working directory, issue the command :

    =>PS1="[\u@\h \w]\$"
    [root@ip-72-167-112-17 /home/amit/Environment]$
    [root@ip-72-167-112-17 /home/amit/Environment]$
   
    The result of this command is that the prompt displays the user's username,
    the machine's name (hostname), and the working directory.

   There are quite a few escape sequences that can be used as value arguments for PS1 :

   | Sr. no. | Escape Sequence & Description |
   |---|---|
   | 1 | \t (Current time:expressed as HH:MM:SS) |
   | 2 | \d (Current date:expressed as weekday:month:year) |
   | 3 | \n (New line) |
   | 4 | \s (Current shell environment) |
   | 5 | \W (Current working directory) |
   | 6 | \w (Full path of current working directory) |
   | 7 | \u (Current user's username) |
   | 8 | \h (Hostname of current machine) |
   | 9 | \# (Command number of the current command. Increases when a new command is entered) |
   | 10 | \$ (If logged in as root end promt as # otherwise $) |

   ### Secondry prompt (PS2)

   When you issue a command that is incomplete, the shell will display a secondary prompt and
   wait for you to complete the command and hit Enter again.

   The default secondary prompt is > (the greater than sign), but can be changed by re-defining
   the PS2 shell variable :

   Following example uses secondry prompt

    $ echo "this is a
    > test"
    this is a
    test
    
   Following example re-defines the PS2 variable

    $ PS2="secondary prompt->"
    $ echo "this is a
    secondary prompt->test"
    this is a
    test

   Environment Variables

   Following is the partial list of important environment :

   | Sr. no. | Variable & Description |
   |---|---|
   | 1 | DISPLAY (Contains the identifier for the display that X11 programs should use by default.) |
   | 2 | HOME (Indicates the home directory of the current user:default argumet to cd) |
   | 3 | IFS (Indicates the Internal Field Separator that is used by parser for word splitting after expansion.) |
   | 4 | LANG (LANG expands to the default system locale; LC_ALL can be used to override this.) |
   | 5 | LD_LIBRARY_PATH [link](https://stackoverflow.com/questions/7148036/what-is-ld-library-path-and-how-to-use-it#:~:text=LD_LIBRARY_PATH%20is%20the%20predefined%20environmental,linking%20dynamic%20libraries%2Fshared%20libraries.&text=The%20best%20way%20to%20use,immediately%20before%20executing%20the%20program.) |
   | 6 | PATH (Indicates the search path for commands. It is a colon-separated list of directories.) |
   | 7 | PWD (Indicates the current working directory as set by the cd command.) |
   | 8 | RANDOM (Generates a random integer between 0 and 32,767 each time it is referenced.) |
   | 9 | SHLVL (Increments by one each time an instance of bash is started.) |
   | 10 | TERM (Refers to the display type.) |
   | 11 | TZ (Refers to Time zone. It can take values like GMT, AST, etc.) |
   | 12 | UID (Expands to the numeric user ID of the current user, initialized at the shell startup.) |

   Example :

    $ echo $HOME
    /root
    ]$ echo $DISPLAY

    $ echo $TERM
    xterm
    $ echo $PATH
    /usr/local/bin:/bin:/usr/bin:/home/amit/bin:/usr/local/bin







   



   


