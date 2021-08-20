# Using Shell Variables

   A variable is nothing more than a pointer to the actual data. The shell enables you to create,
   assign, and delete variables.

   ## Variable names

   The name of a variable can contain only letters (a to z or A to Z), numbers ( 0 to 9) or the 
   underscore character ( _).

   By convention, Unix shell variables will have their names in UPPERCASE.

   Valid variables :

    _ALI
    TOKEN_A
    VAR_1
    VAR_2

   Invalid variables :

    2_VAR
    -VARIABLE
    VAR1-VAR2
    VAR_A!

   ## Defining Variables

   Variables are defined as follows :

    variable_name=variable_value    (variable name, = and variable value should not have space between them)

   example :
   
    NAME="Amit Choudhary"

   The above example defines the variable NAME and assigns the value "Zara Ali" to it. Variables of this
   type are called scalar variables. A scalar variable can hold only one value at a time.

   Shell enables you to store any value you want in a variable. For example :

    VAR1="Zara Ali"
    VAR2=69
    VAR3=120.5

   ## Accessing Values

   To access the value stored in a variable, prefix its name with the dollar sign ($). For example :

    #!/bin/sh

    NAME="Amit Choudhary"
    echo $NAME

   ## Read-only Variables

   Shell provides a way to mark variables as read-only by using the read-only command. After a variable
   is marked read-only, its value cannot be changed. For example :

    #!/bin/sh

    NAME="Amit"
    readonly NAME
    NAME="Viren"

   output :

     line 5: NAME: is read only

   ## Unsetting Variables (deleting variables)

   Unsetting or deleting a variable directs the shell to remove the variable from the list of variables that
   it tracks. Once you unset a variable, you cannot access the stored value in the variable.

   Syntax :

    unset variable_name

   Example :

    #!/bin/sh

    NAME="Amit"
    unset NAME
    echo NAME

   The above example does not print anything. You cannot use the unset command to unset variables that are
   marked readonly.

   ## Variable Types

   When a shell is running, three main types of variables are present :

   * Local Variables − A local variable is a variable that is present within the current instance of the shell.
       It is not available to programs that are started by the shell. They are set at the command prompt.

   * Environment Variables − An environment variable is available to any child process of the shell. Some 
       programs need environment variables in order to function correctly. Usually, a shell script defines
       only those environment variables that are needed by the programs that it runs.

   * Shell Variables − A shell variable is a special variable that is set by the shell and is required by the
       shell in order to function correctly. Some of these variables are environment variables whereas others are
       local variables.


















