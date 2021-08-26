# Shell Loops

   A loop is a powerful programming tool that enables you to execute a set of commands repeatedly.
   In this chapter, we will examine the following types of loops available to shell programmers

   * The while loop

   * The for loop

   * The until loop

   * The select loop

   ## While Loop

   The while loop enables you to execute a set of commands repeatedly until some condition occurs.
   It is usually used when you need to manipulate the value of a variable repeatedly.

   Syntax :

    while command
    do
       Statement(s) to be executed if command is true
    done

   Example :

    #!/bin/sh

    a=0

    while [ $a -lt 10 ]
    do
       echo $a
       a=`expr $a + 1`
    done

   Output :

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9

   ## For Loop

   The for loop operates on lists of items. It repeats a set of commands for every item in a list.

   Syntax :

    for var in word1 word2 ... wordN
    do
       Statement(s) to be executed for every word.
    done

   Example :

    #!/bin/sh

    for var in 0 1 2 3 4 5 6 7 8 9
    do
       echo $var
    done

   Output :

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9

   Following code will also give the same output :

    #!/bin/sh

    for var in {0..10}
    do
       echo $var
    done

   ## Until Loop

   The while loop is perfect for a situation where you need to execute a set of commands while some
   condition is true. Sometimes you need to execute a set of commands until a condition is true.

   Syntax :

    until command
    do
       Statement(s) to be executed until command is true
    done

   Example :

    #!/bin/sh

    a=0

    until [ ! $a -lt 10 ]
    do
       echo $a
       a=`expr $a + 1`
    done

   Output :

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9

   ## Nesting Loops

   All the loops support nesting concept which means you can put one loop inside another similar one or
   different loops. This nesting can go up to unlimited number of times based on your requirement.

   Here is an example of nesting while loop. The other loops can be nested based on the programming 
   requirement in a similar way.

   Syntax :

    while command1 ; # this is loop1, the outer loop
    do
       Statement(s) to be executed if command1 is true

       while command2 ; # this is loop2, the inner loop
       do
          Statement(s) to be executed if command2 is true
       done
   
       Statement(s) to be executed if command1 is true
    done

   Example :

    #!/bin/sh

    a=0
    while [ "$a" -lt 10 ]    # this is loop1
    do
       b="$a"
       while [ "$b" -ge 0 ]  # this is loop2
       do
          echo -n "$b "
          b=`expr $b - 1`
       done
       echo
       a=`expr $a + 1`
    done

   Output :

    0
    1 0
    2 1 0
    3 2 1 0
    4 3 2 1 0
    5 4 3 2 1 0
    6 5 4 3 2 1 0
    7 6 5 4 3 2 1 0
    8 7 6 5 4 3 2 1 0
    9 8 7 6 5 4 3 2 1 0











