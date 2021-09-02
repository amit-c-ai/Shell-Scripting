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
   | 2 | Double quote | Most special characters between these quotes lose their special meaning with these exceptions : |
   | 3 | Backslash |  |
   | 4 | Back quote |  |







