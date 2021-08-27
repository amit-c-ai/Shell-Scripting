# Shell Loop Control

   two statements that are used to control shell loops :

   * break statement

   * continue statement

   The infinite loop

   A loop may continue forever if the required condition is not met. A loop that executes forever without
   terminating executes for an infinite number of times. For this reason, such loops are called infinite
   loops.

   Example :

    #!/bin/sh

    a=10

    while [ $a -lt 10 ]
    do
       echo $a
       a=`expr $a + 1`
    done

   This loop continues forever because a is always greater than or equal to 10 and it is never less than 10.

   ## Break Statement

   The break statement is used to terminate the execution of the entire loop, after completing the execution
   of all of the lines of code up to the break statement. Control reaches to end of the loop.

   Syntax :

    break

   The break command can also be used to exit from a nested loop using this format :

    break n

   Here n specifies the nth enclosing loop to the exit from.

   Example :

    #!/bin/sh

    a=0

    while [ $a -lt 10 ]
    do
       echo $a
       if [ $a -eq 5 ]
       then
          break
       fi
       a=`expr $a + 1`
    done

   Output :

    0
    1
    2
    3
    4
    5

   Here is a simple example of nested for loop. This script breaks out of both loops if var1 equals 2
   and var2 equals 0 :

    #!/bin/sh

    for var1 in 1 2 3
    do
    for var2 in 0 5
       do
          if [ $var1 -eq 2 -a $var2 -eq 0 ]
          then
             break 2
          else
             echo "$var1 $var2"
          fi
       done
    done

   Output :

    1 0
    1 5

   ## Continue Statement

   The continue statement is similar to the break command, except that it causes the current iteration of
   the loop to exit, rather than the entire loop.

   This statement is useful when an error has occurred but you want to try to execute the next iteration of
   the loop.

   Syntax :

    continue

   Like with the break statement, an integer argument can be given to the continue command to skip commands
   from nested loops.

    continue n

   Here n specifies the nth enclosing loop to continue from.

   Example :

    #!/bin/sh

    NUMS="1 2 3 4 5 6 7"

    for NUM in $NUMS
    do
       Q=`expr $NUM % 2`
       if [ $Q -eq 0 ]
       then
          echo "Number is an even number!!"
          continue
       fi
       echo "Found odd number"
    done

   Output :

    Found odd number
    Number is an even number!!
    Found odd number
    Number is an even number!!
    Found odd number
    Number is an even number!!
    Found odd number
  













