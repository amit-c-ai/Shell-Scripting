# Shell Substitution

   The shell performs substitution when it encounters an expression that contains one or more
   special characters.

   Example :

   Here, the printing value of the variable is substituted by its value. Same time, "\n" is
   substituted by a new line :

   #!/bin/sh

   a=10
   echo -e "Value of a is $a \n"

   Output :

    Value of a is 10 

   Output without -e :

    Value of a is 10 \n

   The following escape sequences which can be used in echo command :

   | Sr. no. | Escape | Description |
   |---|---|---|
   | 1 | \\ | backslash |
   | 2 | \a | alert() |
   | 3 | \b | backspace |
   | 4 | \c | supress trainling newline |
   | 5 | \f | form feed |
   | 6 | \n | newline |
   | 7 | \r | carriage return |
   | 8 | \t | horizontal tab space |
   | 9 | \v | vertical tab space |

   ## Command Substitution 

   Command substitution is the mechanism by which the shell performs a given set of commands
   and then substitutes their output in the place of the commands.

   Syntax :

    `command`

   When performing the command substitution make sure that you use the backquote, not the single
   quote character.

   Example :

   Command substitution is generally used to assign the output of a command to a variable. Each
   of the following examples demonstrates the command substitution :

    #!/bin/sh

    DATE=`date`
    echo "Date is $DATE"

    USERS=`who | wc -l`
    echo "Logged in user are $USERS"

    UP=`date ; uptime`
    echo "Uptime is $UP"

   Output :

    Date is Mon Aug 30 13:46:20 IST 2021
    Logged in user are 1
    Uptime is Mon Aug 30 13:46:20 IST 2021
    13:46:20 up  3:40,  1 user,  load average: 0.50, 0.43, 0.62

   ## Variable Substitution

   Variable substitution enables the shell programmer to manipulate the value of a variable based
   on its state.

   Here is the following table for all the possible substitutions :

   | Sr. no. | Form | Description |
   |---|---|---|
   | 1 | ${var} | Substitute the value of var. |
   | 2 | ${var}:-word | If var is null or unset, word is substituted for var. The value of var does not change. |
   | 3 | ${var}:=word | If var is null or unset, var is set to the value of word. |
   | 4 | ${var}:?message | If var is null or unset, message is printed to standard error. This checks that variables are set correctly. |
   | 5 | ${var}:+word | If var is set, word is substituted for var. The value of var does not change. |

   Example :

    #!/bin/sh

    echo ${var:-"Variable is not set"}
    echo "1 - Value of var is ${var}"

    echo ${var:="Variable is not set"}
    echo "2 - Value of var is ${var}"

    unset var
    echo ${var:+"This is default value"}
    echo "3 - Value of var is $var"

    var="Prefix"
    echo ${var:+"This is default value"}
    echo "4 - Value of var is $var"

    echo ${var:?"Print this message"}
    echo "5 - Value of var is ${var}"

   Output :

    Variable is not set
    1 - Value of var is
    Variable is not set
    2 - Value of var is Variable is not set

    3 - Value of var is
    This is default value
    4 - Value of var is Prefix
    Prefix
    5 - Value of var is Prefix

















