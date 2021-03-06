# Basic Utilities-Printing, Email

## Printing files

Before you print a file on a Unix system, you may want to reformat it to adjust the margins,
highlight some words, and so on.

   The pr command:

   The pr command does minor formatting of files on the terminal screen or for a printer. Ex :

    $pr option(s) filename(s)

   The pr changes the format of the file only on the screen or on the printed copy; it doesn't 
   modify the original file. Following table lists some pr options :

   | Sr. no. | Option | Description |
   |---|---|---|
   | 1 | -k | produces k columns of output |
   | 2 | -d | double-spaces the output (not in all pr versions) |
   | 3 | -h "header" | takes the next argument as report header |
   | 4 | -t | eliminates the printing of header and the top/bottom margin |
   | 5 | -l PAGE_LENGTH | sets pagelength to PAGE_LENGTH lines, default is 56 lines |
   | 6 | -o MARGIN | Offsets each line with MARGIN spaces, default is 0 |
   | 7 | -w PAGE_WIDTH | sets pagewidth to PAGE_WIDTH charactes (for multiple column output only) |

   Before using pr, here are the contents of a sample file named alphabets

    $cat alphabets
    A
    B
    C
    D
    E
    F
    G
    H
    I
    J
    K
    L
    M
    N
    O
    P
    Q
    R
    S
    T
    U
    V
    W
    X
    Y
    Z

   Using pr command to make a three-column report with header Alphabets

    $pr -3 -h "Alphabets" alphabet
    A    	 J    	      S
    B	         L	      T
    C	         M	      U
    D	         N	      V
    E	         O	      W
    F	         P	      X
    G	         Q	      Y
    H	         R	      Z
    I

   lp and lpr commands :

   The command lp/lpr prints a file onto paper as opposed to the screen display.
   Once you are ready with formatting using the pr command, you can use any of these
   commands to print your file on the printer connected to your computer. Ex :

    $lp alphabets
    request id is laserp-525  (1 file)

   The lp command shows an ID that you can use to cancel the print job or check its status.

   * If you are using the lp command, you can use the -nNum option to print Num number of copies.
     Along with the command lpr, you can use -Num for the same

   * If there are multiple printers connected with the shared network, then you can choose a printer
     using -dprinter option along with lp command and for the same purpose you can use -Pprinter option
     along with lpr command. Here printer is the printer name.

   lpstat and lpq command :

   The lpstat command shows what's in the printer queue: request IDs, owners, file sizes, when the jobs 
   were sent for printing, and the status of the requests.

   Use lpstat -o if you want to see all output requests other than just your own.
   Requests are shown in the order they'll be printed :

    $lpstat -o
    laserp-573  john  128865  Nov 7  11:27  on laserp
    laserp-574  grace  82744  Nov 7  11:28
    laserp-575  john   23347  Nov 7  11:35

   The lpq gives slightly different information than lpstat -o 

    $lpq
    laserp is ready and printing
    Rank   Owner      Job  Files                  Total Size
    active john       573  report.ps              128865 bytes
    1st    grace      574  ch03.ps ch04.ps        82744 bytes
    2nd    john       575  standard input         23347 bytes

   cancel and lprm commands :

   * cancel : The cancel command terminates a printing request from the lp command.

   * lprm : The lprm command terminates all lpr requests.

   You can specify either the ID of the request (displayed by lp or lpq) or the name of the printer.

    $cancel laserp-575
    request "laserp-575" cancelled

   cancel whatever request is currently playing

    $cancel laserp
    request "laserp-573" cancelled

   The lprm command will cancel the active job if it belongs to you. Otherwise, you can give job numbers
   as arguments, or use a dash (-) to remove all of your jobs :

    $lprm 575
    dfA575diamond dequeued
    cfA575diamond dequeued

   The lprm command tells you the actual filenames removed from the printer queue.

   ## Sending Email

   You use the Unix mail command to send and receive mail. Here is the syntax to send an email :

    $mail [-s subject] [-c cc-address] [-b bcc-address] to-address

   Here are important options related to mail command

   | Sr. no. | Option | Description |
   |---|---|---|
   | 1 | -s | specifies subject on the command line |
   | 2 | -c | sends carbon copies to list of users. List should be commaseperated list of names |
   | 3 | -b | sends blind carbon copies to list. List should be a commaseparated list of names |

    example to send a test message to admin@yahoo.com : 

    $mail -s "test subject" admin@yahoo.com

   You are then expected to type in your message, followed by "control-D" at the beginning of a line.
   To stop, simply type dot (.) as follows :

    Hi,

    This is a test
    .
    Cc: 

   You can send a complete file using a redirect < operator as follows :

    $mail -s "Report 05/06/07" admin@yahoo.com < demo.txt

   To check incoming email at your Unix system, you simply type email as follows :

    $mail
    no email
















   
