# Special Variables

   We know that we can't use certain nonalphanumeric characters in variable names. This
   is because those characters are used in the names of special Unix variables. These 
   variables are reserved for specific functions.

   For example, the $ character represents the process ID number of the current shell :

    $echo $$

   output :

    4740

   The following table shows a number of special variables that you can use in your shell scripts :

   | Sr. no.  | Variable | Description |
   |---|---|---|
   | 1 | $0 | The filename of the current script |
   | 2 | $n | These variables correspond to the arguments with which a script was invoked. Here n is +ve no. corresponding to position of argument |
   | 3 | $# | The number of arguments supplied to a script |
   | 4 | $* | All the arguments are double quoted. If a script receives two arguments, $* is equivalent to $1 $2 |
   | 5 | $@ | All the arguments are individually double quoted. If a script receives two arguments, $@ is equivalent to $1 $2 |
   | 6 | $? | The exit status of the last command executed |
   | 7 | $$ | The process number of the current shell. For shell scripts, this is the process ID under which they are executing |
   | 8 | $! | The process number of the last background command |

   ## Command-Line Arguments

   The command-line arguments $1, $2, $3, ...$9 are positional parameters, with $0 pointing to the actual
   command, program, shell script, or function and $1, $2, $3, ...$9 as the arguments to the command.

   Example :

    #!/bin/sh

    echo "File Name: $0"
    echo "First Parameter : $1"
    echo "Second Parameter : $2"
    echo "Quoted Values: $@"
    echo "Quoted Values: $*"
    echo "Total Number of Parameters : $#"

   Output :

    $./test.sh Amit Choudhary
    File Name : ./test.sh
    First Parameter : Amit
    Second Parameter : Choudhary
    Quoted Values: Amit Choudhary
    Quoted Values: Amit Choudhary
    Total Number of Parameters : 2

   ## Special parameters $* and $@

   Both the parameters specify the command-line arguments.

   * "$*" special parameter takes the entire list as one argument with spaces between 

   * "$@" special parameter takes the entire list and separates it into separate arguments.

   We can write the shell script as shown below to process an unknown number of commandline arguments with either the $*
   or $@ special parameters :

    #!/bin/sh

    for TOKEN in $*
    do
       echo $TOKEN
    done

   Output :

    $./test.sh Wake up to reality
    Wake
    up
    to
    reality
    
   Here do...done is a kind of loop which we'll learn later.

   ## Exit Status

   The $? variable represents the exit status of the previous command.

   Exit status is a numerical value returned by every command upon its completion. As a rule, most commands return an
   exit status of 0 if they were successful, and 1 if they were unsuccessful.

   Example :

    #!/bin/sh

    for TOKEN in $*
    do
       echo $TOKEN
    done
    echo $?

   Output :

    $./test.sh Wake up to reality
    Wake
    up
    to
    reality
    0















