# Shell Decision Making

   Unix Shell supports conditional statements which are used to perform different actions based on
   different conditions. We will now understand two decision-making statements here :

   * The **if...else** statement

   * The **case...esac** statement

   ## The if...else statements

   If else statements are useful decision-making statements which can be used to select an option 
   from a given set of options.

   Unix Shell supports following forms of if…else statement :

   * if...fi statement

   * if...else...fi statement

   * if...elif...else...fi statement

   Most of the if statements check relations using relational operators.

   Example :

    #! /bin/bash

    a=10
    b=23
    if [[ $a -gt $b ]]
    then
    echo "Greater"
    else
    echo "Lesser"
    fi

   Output :

    Lesser

   ## The case...esac Statement  (similar to switch..case)

   You can use multiple if...elif statements to perform a multiway branch. However, this is not always the
   best solution, especially when all of the branches depend on the value of a single variable.

   Unix Shell supports case...esac statement which handles exactly this situation, and it does so more
   efficiently than repeated if...elif statements.

   The basic syntax of the case...esac statement is to give an expression to evaluate and to execute several
   different statements based on the value of the expression.

    case word in
       pattern1)
          Statement(s) to be executed if pattern1 matches
          ;;
       pattern2)
          Statement(s) to be executed if pattern2 matches
          ;;
       pattern3)
          Statement(s) to be executed if pattern3 matches
          ;;
       *)
         Default condition to be executed
         ;;
    esac

   Here the string word is compared against every pattern until a match is found. The statement(s) following 
   the matching pattern executes. If no matches are found, the case statement exits without performing any action.

   There is no maximum number of patterns, but the minimum is one.

   When statement(s) part executes, the command ;; indicates that the program flow should jump to the end of the
   entire case statement. This is similar to break in the C programming language.

   Example :

    #!/bin/sh
    
    FRUIT="kiwi"

    case "$FRUIT" in
       "apple") echo "Apple pie is quite tasty." 
       ;;
       "banana") echo "I like banana nut bread." 
       ;;
       "kiwi") echo "New Zealand is famous for kiwi." 
       ;;
    esac

   Output :

    New Zealand is famous for kiwi.







   




