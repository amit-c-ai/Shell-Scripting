# Pipes and Filters

   We can connect two commands together so that the output from one program becomes the 
   input of the next program. Two or more commands connected in this way form a **pipe**.

   To make a pipe, put a vertical bar (|) on the command line between two commands.

   When a program takes its input from another program, it performs some operation on that 
   input, and writes the result to the standard output. It is referred to as a **filter**.

   ## The grep command

   grep command searches file/files for lines having certain pattern given by us. Ex :

    $grep pattern filename(s)

   Example

    $ls -l | grep "Aug"
    -rw-rw-rw-   1 john  doc     11008 <mark>Aug</mark>  6 14:10 ch02
    -rw-rw-rw-   1 john  doc      8515 <mark>Aug</mark>  6 15:30 ch07
    -rw-rw-r--   1 john  doc      2488 <mark>Aug</mark> 15 10:51 intro
    -rw-rw-r--   1 carol doc      1605 <mark>Aug</mark> 23 07:35 macros

   There are various options which you can use along with the grep command :

   | Sr. no. | Option | Description |
   |---|---|---|
   | 1 | -v | prints all lines that do not match pattern |
   | 2 | -n | prints the matched line and its line number |
   | 3 | -l | prints only the names of files with matching lines |
   | 4 | -c | prints only the count of matching lines |
   | 5 | -i | matches either upper or lowercase(ignore case) |

   Let's now use [regular expression](https://www.geeksforgeeks.org/write-regular-expressions/) that tells grep to find lines with "**carol**", followed by zero
   or other characters abbreviated as ".*",then followed by "Aug"

   we are using the -i option to have case insensitive search

    $ls -l | grep -i "carol.*aug"
    -rw-rw-r--   1 carol doc      1605 Aug 23 07:35 macros

   ## The Sort Command

   The sort command arranges lines of text alphabetically or numerically. The following
   example sorts the lines in the food file :

    $sort food
    Afghani Cuisine
    Bangkok Wok
    Big Apple Deli
    Isle of Java
    
    Mandalay
    Sushi and Sashimi
    Sweet Tooth
    Tio Pepe's Peppers

   The sort command arranges lines of text alphabetically by default.
   There are many options that control the sorting :

   | Sr. no. | Option | Description |
   |---|---|---|
   | 1 | -n | Sorts numerically (example: 10 will sort after 2), ignores blanks and tabs |
   | 2 | -r | Reverses the order of sort |
   | 3 | -f | Sorts upper and lowercase together |
   | 4 | +x | Ignores first x fields when sorting |

   More than two commands may be linked up into a pipe. Taking a previous pipe example
   using grep, we can further sort the files modified in August by the order of size.

   The following pipe consists of the commands ls, grep, and sort :

    $ls -l | grep "Aug" | sort +4n
    -rw-rw-r--  1 carol doc      1605 Aug 23 07:35 macros
    -rw-rw-r--  1 john  doc      2488 Aug 15 10:51 intro
    -rw-rw-rw-  1 john  doc      8515 Aug  6 15:30 ch07
    -rw-rw-rw-  1 john  doc     11008 Aug  6 14:10 ch02

   The sort option +4n skips four fields (fields are separated by blanks) then sorts the lines in numeric order.

   ## The pg and more commands

   A long output can normally be zipped by you on the screen, but if you run text through more or use the pg command
   as a filter; the display stops once the screen is full of text.

   Let's assume that you have a long directory listing. To make it easier to read the sorted listing, pipe the output
   through more as follows :

    $ls -l | grep "Aug" | sort +4n | more
    -rw-rw-r--  1 carol doc      1605 Aug 23 07:35 macros
    -rw-rw-r--  1 john  doc      2488 Aug 15 10:51 intro
    -rw-rw-rw-  1 john  doc      8515 Aug  6 15:30 ch07
    -rw-rw-r--  1 john  doc     14827 Aug  9 12:40 ch03
       	    .
	    .
	    .
    -rw-rw-rw-  1 john  doc     16867 Aug  6 15:56 ch05
    --More--(74%)

   The screen will fill up, once the screen is full of text consisting of lines sorted by the order of the file size.
   At the bottom of the screen is the more prompt, where you can type a command to move through the sorted text.

   Once you're done with this screen, you can use any of the commands listed in the discussion of the more program











