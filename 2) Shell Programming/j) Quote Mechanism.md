# Shell Quoting Mechanisms

   Unix Shell provides various metacharacters which have special meaning while using them in any
   Shell Script and causes termination of a word unless quoted.

   For example, ? matches with a single character while listing files in a directory and an * matches
   more than one character. Here is a list of shell special characters (also called metacharacters) :

    * ? [ ] ' " \ $ ; & ( ) | ^ < > new-line space tab

   A character may be quoted by preceding it with a \.

   Example

    #!/bin/sh

    echo Hello; Word
    echo I earned $500

   Output :

    Hello
    ./test.sh: line 2: Word: command not found

    shell returned 127

   Let us now try using a quoted character :

    #!/bin/sh

    echo 'Hello; Word'
    echo "I earned $500"

   Output :

    Hello; Word
    I earned $500

   The following table lists the four forms of quoting :

   | Sr. no. | Quoting | Description |
   |---|---|---|
   | 1 | Single quote | All special characters between these quotes lose their special meaning |
   | 2 | Double quote | Most special characters between these quotes lose their special meaning with these exceptions : 
   * $
   * `
   * \$
   * \'
   * \"
   * \\ |
   | 3 | Backslash | Any character immediately following the backslash loses its special meaning |
   | 4 | Back quote | Anything in between back quotes would be treated as a commond and would be executed |

   ## Single Quotes

   Consider an echo command that contains many special shell characters :

    echo <-$1500.**>; (update?) [y|n]

   Putting a backslash in front of each special character is tedious and makes the line difficult to read :

    echo \<-\$1500.\*\*\>\; \(update\?\) \[y\|n\]

   Put a single quote (') at the beginning and at the end of the string :

    echo '<-$1500.**>; (update?) [y|n]'

   If a single quote appears within a string to be output, you should not put the whole string within single quotes instead you
   should precede that using a backslash (\) as follows :

    echo 'It\'s Shell Programming

   ## Double Quotes

   Try to execute the following shell script. This shell script makes use of single quote :

    VAR=ZARA
echo '$VAR owes <-$1500.**>; [ as of (`date +%m/%d`) ]'

   Output :

    $VAR owes <-$1500.**>; [ as of (`date +%m/%d`) ]

   This is not what had to be displayed. It is obvious that single quotes prevent variable substitution. If you want to substitute 
   variable values and to make inverted commas work as expected, then you would need to put your commands in double quotes
   as follows :

    VAR=ZARA
    echo "$VAR owes <-\$1500.**>; [ as of (`date +%m/%d`) ]"

   Output :

    ZARA owes <-$1500.**>; [ as of (07/02) ]

   Double quotes take away the special meaning of all characters except the following :

   * $ for parameter substitution

   * Backquote for command substitution

   * \$ to enable literal dollar signs

   * \` to enable literal backquotes

   * \" to enable embedded double quotes

   * \\ to enable embedded backslashes

   * All other \ characters are literal (not special)

   Characters within single quotes are quoted just as if a backslash is in front of each character. This helps the echo command
   display properly.

   If a single quote appears within a string to be output, you should not put the whole string within single quotes instead you
   should precede that using a backslash (\) as follows : 

    echo 'It\'s Shell Programming'

   ## Backquotes

   Putting any Shell command in between backquotes executes the command.

   Syntax :

    var=`command`

   Example :

    DATE=`date`

    echo "Current Date: $DATE"

   Output :

    Current Date: Thu Sep  2 05:28:45 MST 2021









