# Using Shell Arrays

   Shell supports a different type of variable called an array variable. This can hold multiple
   values at the same time. Instead of creating a new name for each variable that is required, 
   you can use a single array variable that stores all the other variables.

   ## Defining array values

   Suppose you are trying to represent the names of various students as a set of variables. Each
   of the individual variables is a scalar variable as follows :

    NAME01="Amit"
    NAME02="Viren"
    NAME03="Mahnaz"
    NAME04="Ayan"
    NAME05="Daisy"

   We can use a single array to store all the above mentioned names. Following is the simplest method
   of creating an array variable. This helps assign a value to one of its indices.

    array_name[index]=value

   Example :

    NAME[0]="Amit"
    NAME[1]="Viren"
    NAME[2]="Mahnaz"
    NAME[3]="Ayan"
    NAME[4]="Daisy"

   If you are using the ksh shell, here is the syntax of array initialization :

    set -A array_name value1 value2 ... valuen

   If you are using the bash shell, here is the syntax of array initialization :

    array_name=(value1 ... valuen)

   ## Accessing array values

   After you have set any array variable, you access it as follows :

    ${array_name[index]}

   Example :

    #!/bin/sh

    NAME[0]="Zara"
    NAME[1]="Qadir"
    NAME[2]="Mahnaz"
    NAME[3]="Ayan"
    NAME[4]="Daisy"
    echo "First Index: ${NAME[0]}"
    echo "Second Index: ${NAME[1]}"

   Output :

    $./test.sh
    First Index: Zara
    Second Index: Qadir

   You can access all the items in an array in one of the following ways :

    ${array_name[*]}
    ${array_name[@]}













