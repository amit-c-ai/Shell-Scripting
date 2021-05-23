# File Management

   ### In Unix, there are 3 types of files :-

    Ordinary-Files: An ordinary file is a file on the system that contains data, text, or program
		    	instructions.

    Directories:    Directories store both special and ordinary files. For users familiar with
		    	Windows or Mac OS, Unix directories are equivalent to folders.

    Special-Files:  Some special files provide access to hardware such as hard drives, CD-ROM drives,
		    	modems, and Ethernet adapters. Other special files are similar to aliases or
		    	shortcuts and enable you to access a single file using different names.

   Listing Files

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
