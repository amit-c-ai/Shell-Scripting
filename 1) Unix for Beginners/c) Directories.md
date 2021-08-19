# Directories

### Home Directory

   The directory in which you find yourself when you first login is called your home directory.

   Commands

    $cd ~			//home directory
    $cd ~username		//any other user's home directory
    $pwd			//present working directory
    $ls -dirname		//listing directories

    $mkdir dirname		//make directory
    $mkdir dir1 dir2 dir2	//make multiple directories

   Sometimes when you want to create a directory, its parent directory or directories might not exist.
   In this case, mkdir issues an error message as follows −

    $mkdir /tmp/amit/test
    mkdir: Failed to make directory "/tmp/amit/test"; 
    No such file or directory

   In such cases, you can specify the -p option to the mkdir command. It creates all the necessary 
   directories for you. For example −

    $mkdir -p /tmp/amit/test

   Commands

    $rmdir dirname		//removing directory
    $rmdir dir1 dir2 dir3	//removing multiple directory
    $cd dirname			//change to any directory by specifying a valid absolute or relative path

    $mv olddir newdir		//mv(move) command can ve used to change directory name

   Directories .(dot) and ..(dot dot)

    The filename . (dot) represents the current working directory; and the filename .. (dot dot) represents 
    the directory one level above the current working directory
    


   


