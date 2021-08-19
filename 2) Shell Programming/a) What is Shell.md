# What is Shell?

   A Shell provides you with an interface to the Unix system. It gathers input from you and executes
   programs based on that input. When a program finishes executing, it displays that program's output.

   Shell is an environment in which we can run our commands, programs, and shell scripts. Different Shells
   require different set of commands.

   ## Shell Prompt

   The prompt, $, which is called the command prompt, is issued by the shell. While the prompt is displayed,
   you can type a command.

   Shell reads your input after you press Enter. It determines the command you want to executed by looking
   at the first word of your input. A word is an unbroken set of characters. Spaces and tabs separate words.

   ## Shell Types

   In Unix, there are two major types of shells :

   * Bourne shell − If you are using a Bourne-type shell, the $ character is the default prompt.

   * C shell − If you are using a C-type shell, the % character is the default prompt.

   The Bourne Shell has the following subcategories :

   * Bourne shell (sh)

   * Korn shell (ksh)

   * Bourne Again shell (bash)

   * POSIX shell (sh)

   The different C-type shells follow :

   * C shell (csh)

   * TENEX/TOPS C shell (tcsh)

  ## Shell Scripts

   The basic concept of a shell script is a list of commands, which are listed in the order of execution.

   There are conditional tests, such as value A is greater than value B, loops allowing us to go through 
   massive amounts of data, files to read and store data, and variables to read and store data, and the
   script may include functions.

   ## Example Script

   Assume we create a test.sh script. Note all the scripts would have the .sh extension. Before you add 
   anything else to your script, you need to alert the system that a shell script is being started. 
   This is done using the shebang construct. For example :

    #!/bin/sh

   This tells the system that the commands that follow are to be executed by the Bourne shell. It's called a
   shebang because the # symbol is called a hash, and the ! symbol is called a bang. Example :

    #!/bin/bash
    pwd
    ls

   Shell Comments 
   You can put your comments in your script as follows :

    #!/bin/bash

    # comment 1
    # comment 2
    # Script follows here:
    pwd
    ls

   Save the above content and make the script executable :

    $chmod +x test.sh

   The shell script is now ready to be executed :

    $./test.sh






























