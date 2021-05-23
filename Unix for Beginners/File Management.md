# File Management

   ### In Unix, there are 3 types of files :-

   - **Ordinary-Files**: An ordinary file is a file on the system that contains data, text, or program
		    	 instructions.

   - **Directories**:    Directories store both special and ordinary files. For users familiar with
		    	 Windows or Mac OS, Unix directories are equivalent to folders.

   - **Special-Files**:  Some special files provide access to hardware such as hard drives, CD-ROM drives,
		    	 modems, and Ethernet adapters. Other special files are similar to aliases or
		    	 shortcuts and enable you to access a single file using different names.

   ### Listing Files

    $ ls
    $ ls -l

   In the ls -l listing example, every file line begins with a **d**, **-**, or **l**. These characters indicate
   the type of the file that's listed. 

   | Prefix | Description |
   |---|---|
   | - | Regular file, such as an ASCII text file, binary executable, or hard link. |
   | b | Block special file. Block input/output device file such as a physical hard drive. |
   | c | Character special file. Raw input/output device file such as a physical hard drive. |
   | d | Directory file that contains a listing of other files and directories. |
   | l | Symbolic link file. Links on any regular file. |
   | p | Named pipe. A mechanism for interprocess communications. |
   | s | Socket used for interprocess communication. |

   ### Metacharacter

   Metacharacters have a special meaning in Unix. For example, * and ? are metacharacters. We use * to match 0
   or more characters, a question mark (?) matches with a single character.

   ##### example

    $ ls am*.md

    am01-1.md   am010.md  am02.md    am03-2.md 
    am04-1.md   am040.md  am05.md    am06-2.md

  This lists all the files starting with am and end with .md

   ### Hidden Files

   An invisible file is one, the first character of which is the dot or the period character (.). Unix programs
  (including the shell) use most of these files to store configuration information.

   To list the invisible files, specify the -a option to ls −

    $ ls -a

    .         .profile       docs     lib     test_results
    ..        .rhosts        hosts    pub     users
    .emacs    bin            hw1      res.01  work

   - **Single dot(.)** − This represents the current directory.

   - **Double dot(..)** − This represents the parent directory.

   ### Creating Files

    $ touch filename

   ### Editing Files

   #### You can use any of the below editor

    $ gedit filename		OR
    $ nano filename		OR
    $ vi filename

   ### Display Content of Files

   #### You can use the cat command to see the content of a file.

    $ cat filename

   #### You can display the line numbers by using the -b option along with the cat
  
    $ cat -b filename

   ### Counting in Files

   #### You can use the wc command to get a count of the total number of lines, words, and characters contained in a file.

    $ wc filename

   #### You can give multiple files as argument

    $ wc filename1 filename2 filename3

   ### More Common Operations on Files

   - $ cp sourceFile targetFile			//copy file
   - $ mv sourceFile targetFile			//rename file
   - $ rm filename			    			//delete file
   - $ rm filename1 filename2			   //delete multiple files

   ### Standard Unix Streams

   #### Under normal circumstances, every Unix program has three streams (files) opened for it when it starts up.

   - **stdin**: This is referred to as the standard input and the associated file descriptor is 0. This is also 
        	represented as STDIN. The Unix program will read the default input from STDIN.

   - **stdout**: This is referred to as the standard output and the associated file descriptor is 1. This is also
        	represented as STDOUT. The Unix program will write the default output at STDOUT.

   - **stderr**: This is referred to as the standard error and the associated file descriptor is 2. This is also
       		 represented as STDERR. The Unix program will write all the error messages at STDERR.








