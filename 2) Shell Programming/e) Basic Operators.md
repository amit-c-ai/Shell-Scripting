# Shell Basic Operators

   There are various operators supported by each shell. We will discuss in detail about Bourne shell
   (default shell).

   We will now discuss the following operators :

   * Arithmetic Operators

   * Relational Operators

   * Boolean Operators

   * String Operators

   * File Test Operators

   Bourne shell didn't originally have any mechanism to perform simple arithmetic operations but it
   uses external programs, either **awk** or **expr**.

   Example :

    #!/bin/sh

    val=`expr 2 + 2`
    echo "Total value : $val"

   Output :

    Total value : 4

   The following points need to be considered while adding :

   * There must be spaces between operators and expressions. For example, 2+2 is not correct; it should
       be written as 2 + 2.

   * The complete expression should be enclosed between ‘ ‘, called the backtick.

   ## Arithmetic Operators

   The following arithmetic operators are supported by Bourne Shell.

   Assume variable a holds 10 and variable b holds 20 then :

   | Operator | Description | Example |
   |---|---|---|
   | +(Addition) | Adds values on either side of operator | `expr $a + $b` will give 30 |
   | -(Subtraction) | Subtract 2nd value from 1st | `expr $a - $b` will give -10 |
   | *(Multiplication) | Multiply values on either side of operator | `expr $a \* $b` will give 200 |
   | /(Division) | Divide 1st value by 2nd value | `expr $a / $b` will give 0 |
   | %(Modulus) | Returns remainder | `expr $b % $a` will give 0 |
   | =(Assignment) | Assigns right operand in left operand | a = $b will assign value of b to a |
   | ==(Equality) | Compares two numbers, if both are same then returns true. | [ $a == $b ] will return false |
   | !=(Not Equality) | Compares two numbers, if both are not same then returns true. | [ $a != $b ] will return true |

   It is very important to understand that all the conditional expressions should be inside square braces with
   spaces around them, for example [ $a == $b ] is correct whereas, [$a==$b] is incorrect.

   All the arithmetical calculations are done using long integers.

   ## Relational Operators

   Bourne Shell supports the following relational operators that are specific to numeric values. These
   operators do not work for string values unless their value is numeric.

   For example, following operators will work to check a relation between 10 and 20 as well as in
   between "10" and "20" but not in between "ten" and "twenty".

   Assume variable a holds 10 and variable b holds 20 then :

   | Operator | Description | Example |
   |---|---|---|
   | eq | Check if values are equal | [ $a -eq $b ] is not true. |
   | ne | Check if values are not equal | [ $a -ne $b ] is true. |
   | gt | Checks if the value of left operand is greater than the value of right operand  | [ $a -gt $b ] is not true. |
   | lt | Checks if the value of left operand is less than the value of right operand | [ $a -lt $b ] is true. |
   | ge | Checks if the value of left operand is greater than equal to the value of right operand | [ $a -ge $b ] is not true. |
   | le | Checks if the value of left operand is less than equal to the value of right operand | [ $a -le $b ] is true. |

   It is very important to understand that all the conditional expressions should be placed inside square braces
   with spaces around them. For example, [ $a <= $b ] is correct whereas, [$a <= $b] is incorrect.

   ## Boolean Operators

   The following Boolean operators are supported by the Bourne Shell.

   Assume variable a holds 10 and variable b holds 20 then :

   | Operator | Description | Example |
   |---|---|---|
   | ! | This is logical negation. This inverts a true condition into false and vice versa. | [ [ ! false ] is true. |
   | -o | This is logical OR. If one of the operands is true, then the condition becomes true. | [ $a -lt 20 -o $b -gt 100 ] is true. |
   | -a | This is logical AND. If both the operands are true, then the condition becomes true otherwise false. | [ $a -lt $b -a $b -gt 100 ] is false. |

   ## String Operators

   The following string operators are supported by Bourne Shell.

   Assume variable a holds "abc" and variable b holds "efg" then :

   | Operator | Description | Example |
   |---|---|---|
   | = | Checks if the value of two operands are equal or not; if yes, then the condition becomes true. | [ $a = $b ] is not true. |
   | != | Checks if the value of two operands are equal or not; if no, then the condition becomes true. | [ $a != $b ] is true. |
   | -z | Checks if the given string operand size is zero; if it is zero length, then it returns true. | [ -z $b ] is not true. |
   | -n | Checks if the given string operand size is non-zero; if it is nonzero length, then it returns true. | [ -n $b ] is true. |
   | str | Checks if str is not the empty string; if it is empty, then it returns false. | [ $a ] is not false. |

   ## File Test Operators

   We have a few operators that can be used to test various properties associated with a Unix file.

   Assume a variable file holds an existing file name "test" the size of which is 100 bytes and has read,
   write and execute permission on :


   | Operator | Description | Example |
   |---|---|---|
   | -b file | Checks if file is a block special file; if yes, then the condition becomes true. | [ -b $file ] is false. |
   | -c file | Checks if file is a character special file; if yes, then the condition becomes true. | [ -c $file ] is false. |
   | -d file | Checks if file is a directory; if yes, then the condition becomes true. | [ -d $file ] is not true. |
   | -f file | Checks if file is an ordinary file as opposed to a directory or special file; if yes, then the condition becomes true. | [ -f $file ] is true. |
   | -g file | Checks if file has its set group ID (SGID) bit set; if yes, then the condition becomes true. | [ -g $file ] is false. |
   | -k file | Checks if file has its sticky bit set; if yes, then the condition becomes true. | [ -k $file ] is false. |
   | -p file | Checks if file is a named pipe; if yes, then the condition becomes true. | [ -p $file ] is false. |
   | -t file | Checks if file descriptor is open and associated with a terminal; if yes, then the condition becomes true. | [ -t $file ] is false. |
   | -u file | Checks if file has its Set User ID (SUID) bit set; if yes, then the condition becomes true. | [ -u $file ] is false. |
   | -r file | Checks if file is readable; if yes, then the condition becomes true. | [ -r $file ] is true. |
   | -w file | Checks if file is writable; if yes, then the condition becomes true. | [ -w $file ] is true. |
-x file	Checks if file is executable; if yes, then the condition becomes true.	[ -x $file ] is true.
-s file	Checks if file has size greater than 0; if yes, then condition becomes true.	[ -s $file ] is true.
-e file	Checks if file exists; is true even if file is a directory but exists.	[ -e $file ] is true.















