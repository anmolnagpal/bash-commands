Unix Commands

Commonly used UNIX Commands!!

1.How to display the 10th line of a file?
```bash
head -10 filename | tail -1
```
2. How to remove the header from a file?
```bash
sed -i '1 d' filename
```
3. How to remove the footer from a file?
```bash
sed -i '$ d' filename
```
4. Write a command to find the length of a line in a file?

The below command can be used to get a line from a file.
```bash
sed –n '<n> p' filename
```
We will see how to find the length of 10th line in a file
```bash
sed -n '10 p' filename|wc -c
```
5. How to get the nth word of a line in Unix?
```bash
cut –f<n> -d' '
```
6. How to reverse a string in unix?
```bash
echo "java" | rev
```
7. How to get the last word from a line in Unix file?
```bash
echo "unix is good" | rev | cut -f1 -d' ' | rev
```
8. How to replace the n-th line in a file with a new line in Unix?
```bash
sed -i'' '10 d' filename       # d stands for delete

sed -i'' '10 i new inserted line' filename     # i stands for insert
```
9. How to check if the last command was successful in Unix?
```bash
echo $?
```
10. Write command to list all the links from a directory?
```bash
ls -lrt | grep "^l"
```
11. How will you find which operating system your system is running on in UNIX?
```bash
uname -a
```
12. Create a read-only file in your home directory?
```bash
touch file; chmod 400 file
```
13. How do you see command line history in UNIX?
```bash
The 'history' command can be used to get the list of commands that we are executed.
```
14. How to display the first 20 lines of a file?

By default, the head command displays the first 10 lines from a file. If we change the option of head, then we can display as many lines as we want.
```bash
head -20 filename
```
-   An alternative solution is using the sed command
```bash
sed '21,$ d' filename
```
-   The d option here deletes the lines from 21 to the end of the file

15. Write a command to print the last line of a file?

The tail command can be used to display the last lines from a file.
```bash
tail -1 filename
```
-   Alternative solutions are:
```bash
sed -n '$ p' filename

awk 'END{print $0}' filename
```
16. How do you rename the files in a directory with _new as suffix?
```bash
ls -lrt|grep '^-'| awk '{print "mv "$9" "$9".new"}' | sh
```
17. Write a command to convert a string from lower case to upper case?
```bash
echo "apple" | tr [a-z] [A-Z]
```
18. Write a command to convert a string to Initcap.
```bash
echo apple | awk '{print toupper(substr($1,1,1)) tolower(substr($1,2))}'
```
19. Write a command to redirect the output of date command to multiple files?

-   The tee command writes the output to multiple files and also displays the output on the terminal.
```bash
date | tee -a file1 file2 file3
```
20. How do you list the hidden files in current directory?
```bash
ls -a | grep '^\.'
```
21. List out some of the Hot Keys available in bash shell?
```bash
Ctrl+l - Clears the Screen.

Ctrl+r - Does a search in previously given commands in shell.

Ctrl+u - Clears the typing before the hotkey.

Ctrl+a - Places cursor at the beginning of the command at shell.

Ctrl+e - Places cursor at the end of the command at shell.

Ctrl+d - Kills the shell.

Ctrl+z - Places the currently running process into background.
```
22. How do you make an existing file empty?
```bash
cat /dev/null >  filename
```
23. How do you remove the first number on 10th line in file?
```bash
sed '10 s/[0-9][0-9]*//' < filename
```
24. What is the difference between join -v and join -a?
```bash
join -v : outputs only matched lines between two files.

join -a : In addition to the matched lines, this will output unmatched lines also.
```
25. How do you display from the 5th character to the end of the line from a file?
```bash
cut -c 5- filename
```
26. Display all the files in current directory sorted by size?
```bash
ls -l | grep '^-' | awk '{print $5,$9}' |sort -n|awk '{print $2}'
```
27. Write a command to search for the file 'map' in the current directory?
```bash
find -name map -type f
```
28. How to display the first 10 characters from each line of a file?
```bash
cut -c -10 filename
```
29. Write a command to remove the first number on all lines that start with "@"?
```bash
sed '\,^@, s/[0-9][0-9]*//' < filename
```
30. How to print the file names in a directory that has the word "term"?
-   The '-l' option make the grep command to print only the filename without printing the content of the file. As soon 
as the grep command finds the pattern in a file, it prints the pattern and stops searching other lines in the file.
```bash
grep -l term *
```

31. How to run awk command specified in a file?
```bash
awk -f filename
```
32. How do you display the calendar for the month march in the year 1985?

The cal command can be used to display the current month calendar. You can pass the month and year as arguments to display the required year, month combination calendar.
```bash
cal 03 1985
```
This will display the calendar for the March month and year 1985.

33. Write a command to find the total number of lines in a file?
```bash
wc -l filename
```
-   Other ways to pring the total number of lines are
```bash
awk 'BEGIN {sum=0} {sum=sum+1} END {print sum}' filename

awk 'END{print NR}' filename
```
34. How to duplicate empty lines in a file?
```bash
sed '/^$/ p' < filename
```
35. Explain iostat, vmstat and netstat?
```bash
Iostat: reports on terminal, disk and tape I/O activity.

Vmstat: reports on virtual memory statistics for processes, disk, tape and CPU activity.

Netstat: reports on the contents of network data structures.
```
36. How do you write the contents of 3 files into a single file?
```bash
cat file1 file2 file3 > file
```
37. How to display the fields in a text file in reverse order?
```bash
awk 'BEGIN {ORS=""} { for(i=NF;i>0;i--) print $i," "; print "\n"}' filename
```
38. Write a command to find the sum of bytes (size of file) of all files in a directory.
```bash
ls -l | grep '^-'| awk 'BEGIN {sum=0} {sum = sum + $5} END {print sum}'
```
39. Write a command to print the lines which end with the word "end"?
```bash
grep 'end$' filename
```
The '$' symbol specifies the grep command to search for the pattern at the end of the line.

40. Write a command to select only those lines containing "july" as a whole word?

grep -w july filename

The '-w' option makes the grep command to search for exact whole words. If the specified pattern is found in a string, then it is not considered as a whole word. For example: In the string "mikejulymak", the pattern "july" is found. However "july" is not a whole word in that string.

41. How to remove the first 10 lines from a file?

sed '1,10 d' < filename

42. Write a command to duplicate each line in a file?

sed 'p' < filename

43. How to extract the username from 'who am i' comamnd?

who am i | cut -f1 -d' '

44. Write a command to list the files in '/usr' directory that start with 'ch' and then display the number of lines in each file?

wc -l /usr/ch*

Another way is

find /usr -name 'ch*' -type f -exec wc -l {} \;

45. How to remove blank lines in a file ?

grep -v ‘^$’ filename > new_filename

46. How to display the processes that were run by your user name ?

ps -aef | grep <user_name>

47. Write a command to display all the files recursively with path under current directory?

find . -depth -print

48. Display zero byte size files in the current directory?

find -size 0 -type f

49. Write a command to display the third and fifth character from each line of a file?

cut -c 3,5 filename

50. Write a command to print the fields from 10th to the end of the line. The fields in the line are delimited by a comma?

cut -d',' -f10- filename

51. How to replace the word "Gun" with "Pen" in the first 100 lines of a file?

sed '1,00 s/Gun/Pen/' < filename

52. Write a Unix command to display the lines in a file that do not contain the word "RAM"?

grep -v RAM filename

The '-v' option tells the grep to print the lines that do not contain the specified pattern.

53. How to print the squares of numbers from 1 to 10 using awk command

awk 'BEGIN { for(i=1;i<=10;i++) {print "square of",i,"is",i*i;}}'

54. Write a command to display the files in the directory by file size?

ls -l | grep '^-' |sort -nr -k 5

55. How to find out the usage of the CPU by the processes?

The top utility can be used to display the CPU usage by the processes.

56. Write a command to remove the prefix of the string ending with '/'.

The basename utility deletes any prefix ending in /. The usage is mentioned below:

basename /usr/local/bin/file

This will display only file

57. How to display zero byte size files?

ls -l | grep '^-' | awk '/^-/ {if ($5 !=0 ) print $9 }'

58. How to replace the second occurrence of the word "bat" with "ball" in a file?

sed 's/bat/ball/2' < filename

59. How to remove all the occurrences of the word "jhon" except the first one in a line with in the entire file?

sed 's/jhon//2g' < filename

60. How to replace the word "lite" with "light" from 100th line to last line in a file?

sed '100,$ s/lite/light/' < filename

61. How to list the files that are accessed 5 days ago in the current directory?

find -atime 5 -type f

62. How to list the files that were modified 5 days ago in the current directory?

find -mtime 5 -type f

63. How to list the files whose status is changed 5 days ago in the current directory?

find -ctime 5 -type f

64. How to replace the character '/' with ',' in a file?

sed 's/\//,/' < filename

sed 's|/|,|' < filename

65. Write a command to find the number of files in a directory.

ls -l|grep '^-'|wc -l

66. Write a command to display your name 100 times.

The Yes utility can be used to repeatedly output a line with the specified string or 'y'.

yes <your_name> | head -100

67. Write a command to display the first 10 characters from each line of a file?

cut -c -10 filename

68. The fields in each line are delimited by comma. Write a command to display third field from each line of a file?

cut -d',' -f2 filename

69. Write a command to print the fields from 10 to 20 from each line of a file?

cut -d',' -f10-20 filename

70. Write a command to print the first 5 fields from each line?

cut -d',' -f-5 filename

71. By default the cut command displays the entire line if there is no delimiter in it. Which cut option is used to supress these kind of lines?

The -s option is used to supress the lines that do not contain the delimiter.

72. Write a command to replace the word "bad" with "good" in file?

sed s/bad/good/ < filename

73. Write a command to replace the word "bad" with "good" globally in a file?

sed s/bad/good/g < filename

74. Write a command to replace the word "apple" with "(apple)" in a file?

sed s/apple/(&)/ < filename

75. Write a command to switch the two consecutive words "apple" and "mango" in a file?

sed 's/\(apple\) \(mango\)/\2 \1/' < filename

76. Write a command to display the characters from 10 to 20 from each line of a file?

cut -c 10-20 filename

77. Write a command to print the lines that has the the pattern "july" in all the files in a particular directory?

grep july *

This will print all the lines in all files that contain the word “july” along with the file name. If any of the files contain words like "JULY" or "July", the above command would not print those lines.

78. Write a command to print the lines that has the word "july" in all the files in a directory and also suppress the filename in the output.

grep -h july *

79. Write a command to print the lines that has the word "july" while ignoring the case.

grep -i july *

The option i make the grep command to treat the pattern as case insensitive.

80. When you use a single file as input to the grep command to search for a pattern, it won't print the filename in the output. Now write a grep command to print the filename in the output without using the '-H' option.

grep pattern filename /dev/null

The /dev/null or null device is special file that discards the data written to it. So, the /dev/null is always an empty file.

Another way to print the filename is using the '-H' option. The grep command for this is

grep -H pattern filename

81. Write a command to print the file names in a directory that does not contain the word "july"?

grep -L july *

The '-L' option makes the grep command to print the filenames that do not contain the specified pattern.

82. Write a command to print the line numbers along with the line that has the word "july"?

grep -n july filename

The '-n' option is used to print the line numbers in a file. The line numbers start from 1

83. Write a command to print the lines that starts with the word "start"?

grep '^start' filename

The '^' symbol specifies the grep command to search for the pattern at the start of the line.

84. In the text file, some lines are delimited by colon and some are delimited by space. Write a command to print the third field of each line.

awk '{ if( $0 ~ /:/ ) { FS=":"; } else { FS =" "; } print $3 }' filename

85. Write a command to print the line number before each line?

awk '{print NR, $0}' filename

86. Write a command to print the second and third line of a file without using NR.

awk 'BEGIN {RS="";FS="\n"} {print $2,$3}' filename

87. How to create an alias for the complex command and remove the alias?

The alias utility is used to create the alias for a command. The below command creates alias for ps -aef command.

alias pg='ps -aef'

If you use pg, it will work the same way as ps -aef.

To remove the alias simply use the unalias command as

unalias pg

88. Write a command to display todays date in the format of 'yyyy-mm-dd'?

The date command can be used to display todays date with time

date '+%Y-%m-%d'

89.For LOOP

1. Rename all ".old" files in the current directory to ".bak":

for i in *.old   do  j=`echo $i|sed 's/old/bak/'`  mv $i $j  done

2. Change all instances of "yes" to "no" in all ".txt" files in the current directory. Back up the original files to ".bak".

for i in *.txt do  j=`echo $i|sed 's/txt/bak/'`  mv $i $j   sed 's/yes/no/' $j > $i  done

3. Loop thru a text file containing possible file names. If the file is readable, print the first line, otherwise print an error message:

for i in `cat file_list.txt` do  if test -r $i   

  then        

   echo "Here is the first line of file: $i"       

   sed 1q $i   

else

echo "file $i cannot be open for reading."      fi  done

How to print/display the first line of a file?

$> head -1 file.txt

$> sed '2,$ d' file.txt

How to print/display the last line of a file?

$> tail -1 file.txt

$> sed -n '$ p' test

How to display n-th line of a file?

$> sed –n '<n> p' file.txt

$> sed –n '4 p' test

$> head -<n> file.txt | tail -1

$> head -4 file.txt | tail -1

How to remove the first line / header from a file?

$> sed '1 d' file.txt

$> sed '1 d' file.txt > new_file.txt

$> mv new_file.txt file.txt

$> sed –i '1 d' file.txt

How to remove the last line/ trailer from a file in Unix script?

$> sed –i '$ d' file.txt

How to remove certain lines from a file in Unix?

$> sed –i '5,7 d' file.txt

How to remove the last n-th line from a file?

$> sed –i '96,100 d' file.txt   # alternative to command [head -95 file.txt]

$> tt=`wc -l file.txt | cut -f1 -d' '`;sed –i "`expr $tt - 4`,$tt d" test

How to check the length of any line in a file?

$> sed –n '<n> p' file.txt

$> sed –n '35 p' file.txt | wc –c

How to check if a file is present in a particular directory in Unix?

$> ls –l file.txt; echo $?

How to check all the running processes in Unix?

$> ps –ef

$> ps aux

$>ps -e -o stime,user,pid,args,%mem,%cpu

Combine multiple Rows to a Column – Oracle

SELECT SUBSTR (SYS_CONNECT_BY_PATH (NAME , ','), 2) FRUITS_LIST

FROM (SELECT NAME , ROW_NUMBER () OVER (ORDER BY NAME ) RN,

COUNT (*) OVER () CNT

FROM FRUITS)

WHERE RN = CNT

START WITH RN = 1

CONNECT BY RN = PRIOR RN + 1;

What is command to check space in Unix

df -k

What is command to kill last background Job

kill $!

What is difference between diff and cmp command

cmp -It compares two files byte by byte and displays first mismatch.

diff -It displays all changes required to make files identical.

What does $# stands for

It will return the number of parameters passed as command line argument.Unix Commands

Commonly used UNIX Commands!!

1.How to display the 10th line of a file?

head -10 filename | tail -1

2. How to remove the header from a file?

sed -i '1 d' filename

3. How to remove the footer from a file?

sed -i '$ d' filename

4. Write a command to find the length of a line in a file?

The below command can be used to get a line from a file.

sed –n '<n> p' filename

We will see how to find the length of 10th line in a file

sed -n '10 p' filename|wc -c

5. How to get the nth word of a line in Unix?

cut –f<n> -d' '

6. How to reverse a string in unix?

echo "java" | rev

7. How to get the last word from a line in Unix file?

echo "unix is good" | rev | cut -f1 -d' ' | rev

8. How to replace the n-th line in a file with a new line in Unix?

sed -i'' '10 d' filename       # d stands for delete

sed -i'' '10 i new inserted line' filename     # i stands for insert

9. How to check if the last command was successful in Unix?

echo $?

10. Write command to list all the links from a directory?

ls -lrt | grep "^l"

11. How will you find which operating system your system is running on in UNIX?

uname -a

12. Create a read-only file in your home directory?

touch file; chmod 400 file

13. How do you see command line history in UNIX?

The 'history' command can be used to get the list of commands that we are executed.

14. How to display the first 20 lines of a file?

By default, the head command displays the first 10 lines from a file. If we change the option of head, then we can display as many lines as we want.

head -20 filename

An alternative solution is using the sed command

sed '21,$ d' filename

The d option here deletes the lines from 21 to the end of the file

15. Write a command to print the last line of a file?

The tail command can be used to display the last lines from a file.

tail -1 filename

Alternative solutions are:

sed -n '$ p' filename

awk 'END{print $0}' filename

16. How do you rename the files in a directory with _new as suffix?

ls -lrt|grep '^-'| awk '{print "mv "$9" "$9".new"}' | sh

17. Write a command to convert a string from lower case to upper case?

echo "apple" | tr [a-z] [A-Z]

18. Write a command to convert a string to Initcap.

echo apple | awk '{print toupper(substr($1,1,1)) tolower(substr($1,2))}'

19. Write a command to redirect the output of date command to multiple files?

The tee command writes the output to multiple files and also displays the output on the terminal.

date | tee -a file1 file2 file3

20. How do you list the hidden files in current directory?

ls -a | grep '^\.'

21. List out some of the Hot Keys available in bash shell?

Ctrl+l - Clears the Screen.

Ctrl+r - Does a search in previously given commands in shell.

Ctrl+u - Clears the typing before the hotkey.

Ctrl+a - Places cursor at the beginning of the command at shell.

Ctrl+e - Places cursor at the end of the command at shell.

Ctrl+d - Kills the shell.

Ctrl+z - Places the currently running process into background.

22. How do you make an existing file empty?

cat /dev/null >  filename

23. How do you remove the first number on 10th line in file?

sed '10 s/[0-9][0-9]*//' < filename

24. What is the difference between join -v and join -a?

join -v : outputs only matched lines between two files.

join -a : In addition to the matched lines, this will output unmatched lines also.

25. How do you display from the 5th character to the end of the line from a file?

cut -c 5- filename

26. Display all the files in current directory sorted by size?

ls -l | grep '^-' | awk '{print $5,$9}' |sort -n|awk '{print $2}'

27. Write a command to search for the file 'map' in the current directory?

find -name map -type f

28. How to display the first 10 characters from each line of a file?

cut -c -10 filename

29. Write a command to remove the first number on all lines that start with "@"?

sed '\,^@, s/[0-9][0-9]*//' < filename

30. How to print the file names in a directory that has the word "term"?

grep -l term *

The '-l' option make the grep command to print only the filename without printing the content of the file. As soon as the grep command finds the pattern in a file, it prints the pattern and stops searching other lines in the file.

31. How to run awk command specified in a file?

awk -f filename

32. How do you display the calendar for the month march in the year 1985?

The cal command can be used to display the current month calendar. You can pass the month and year as arguments to display the required year, month combination calendar.

cal 03 1985

This will display the calendar for the March month and year 1985.

33. Write a command to find the total number of lines in a file?

wc -l filename

Other ways to pring the total number of lines are

awk 'BEGIN {sum=0} {sum=sum+1} END {print sum}' filename

awk 'END{print NR}' filename

34. How to duplicate empty lines in a file?

sed '/^$/ p' < filename

35. Explain iostat, vmstat and netstat?

Iostat: reports on terminal, disk and tape I/O activity.

Vmstat: reports on virtual memory statistics for processes, disk, tape and CPU activity.

Netstat: reports on the contents of network data structures.

36. How do you write the contents of 3 files into a single file?

cat file1 file2 file3 > file

37. How to display the fields in a text file in reverse order?

awk 'BEGIN {ORS=""} { for(i=NF;i>0;i--) print $i," "; print "\n"}' filename

38. Write a command to find the sum of bytes (size of file) of all files in a directory.

ls -l | grep '^-'| awk 'BEGIN {sum=0} {sum = sum + $5} END {print sum}'

39. Write a command to print the lines which end with the word "end"?

grep 'end$' filename

The '$' symbol specifies the grep command to search for the pattern at the end of the line.

40. Write a command to select only those lines containing "july" as a whole word?

grep -w july filename

The '-w' option makes the grep command to search for exact whole words. If the specified pattern is found in a string, then it is not considered as a whole word. For example: In the string "mikejulymak", the pattern "july" is found. However "july" is not a whole word in that string.

41. How to remove the first 10 lines from a file?

sed '1,10 d' < filename

42. Write a command to duplicate each line in a file?

sed 'p' < filename

43. How to extract the username from 'who am i' comamnd?

who am i | cut -f1 -d' '

44. Write a command to list the files in '/usr' directory that start with 'ch' and then display the number of lines in each file?

wc -l /usr/ch*

Another way is

find /usr -name 'ch*' -type f -exec wc -l {} \;

45. How to remove blank lines in a file ?

grep -v ‘^$’ filename > new_filename

46. How to display the processes that were run by your user name ?

ps -aef | grep <user_name>

47. Write a command to display all the files recursively with path under current directory?

find . -depth -print

48. Display zero byte size files in the current directory?

find -size 0 -type f

49. Write a command to display the third and fifth character from each line of a file?

cut -c 3,5 filename

50. Write a command to print the fields from 10th to the end of the line. The fields in the line are delimited by a comma?

cut -d',' -f10- filename

51. How to replace the word "Gun" with "Pen" in the first 100 lines of a file?

sed '1,00 s/Gun/Pen/' < filename

52. Write a Unix command to display the lines in a file that do not contain the word "RAM"?

grep -v RAM filename

The '-v' option tells the grep to print the lines that do not contain the specified pattern.

53. How to print the squares of numbers from 1 to 10 using awk command

awk 'BEGIN { for(i=1;i<=10;i++) {print "square of",i,"is",i*i;}}'

54. Write a command to display the files in the directory by file size?

ls -l | grep '^-' |sort -nr -k 5

55. How to find out the usage of the CPU by the processes?

The top utility can be used to display the CPU usage by the processes.

56. Write a command to remove the prefix of the string ending with '/'.

The basename utility deletes any prefix ending in /. The usage is mentioned below:

basename /usr/local/bin/file

This will display only file

57. How to display zero byte size files?

ls -l | grep '^-' | awk '/^-/ {if ($5 !=0 ) print $9 }'

58. How to replace the second occurrence of the word "bat" with "ball" in a file?

sed 's/bat/ball/2' < filename

59. How to remove all the occurrences of the word "jhon" except the first one in a line with in the entire file?

sed 's/jhon//2g' < filename

60. How to replace the word "lite" with "light" from 100th line to last line in a file?

sed '100,$ s/lite/light/' < filename

61. How to list the files that are accessed 5 days ago in the current directory?

find -atime 5 -type f

62. How to list the files that were modified 5 days ago in the current directory?

find -mtime 5 -type f

63. How to list the files whose status is changed 5 days ago in the current directory?

find -ctime 5 -type f

64. How to replace the character '/' with ',' in a file?

sed 's/\//,/' < filename

sed 's|/|,|' < filename

65. Write a command to find the number of files in a directory.

ls -l|grep '^-'|wc -l

66. Write a command to display your name 100 times.

The Yes utility can be used to repeatedly output a line with the specified string or 'y'.

yes <your_name> | head -100

67. Write a command to display the first 10 characters from each line of a file?

cut -c -10 filename

68. The fields in each line are delimited by comma. Write a command to display third field from each line of a file?

cut -d',' -f2 filename

69. Write a command to print the fields from 10 to 20 from each line of a file?

cut -d',' -f10-20 filename

70. Write a command to print the first 5 fields from each line?

cut -d',' -f-5 filename

71. By default the cut command displays the entire line if there is no delimiter in it. Which cut option is used to supress these kind of lines?

The -s option is used to supress the lines that do not contain the delimiter.

72. Write a command to replace the word "bad" with "good" in file?

sed s/bad/good/ < filename

73. Write a command to replace the word "bad" with "good" globally in a file?

sed s/bad/good/g < filename

74. Write a command to replace the word "apple" with "(apple)" in a file?

sed s/apple/(&)/ < filename

75. Write a command to switch the two consecutive words "apple" and "mango" in a file?

sed 's/\(apple\) \(mango\)/\2 \1/' < filename

76. Write a command to display the characters from 10 to 20 from each line of a file?

cut -c 10-20 filename

77. Write a command to print the lines that has the the pattern "july" in all the files in a particular directory?

grep july *

This will print all the lines in all files that contain the word “july” along with the file name. If any of the files contain words like "JULY" or "July", the above command would not print those lines.

78. Write a command to print the lines that has the word "july" in all the files in a directory and also suppress the filename in the output.

grep -h july *

79. Write a command to print the lines that has the word "july" while ignoring the case.

grep -i july *

The option i make the grep command to treat the pattern as case insensitive.

80. When you use a single file as input to the grep command to search for a pattern, it won't print the filename in the output. Now write a grep command to print the filename in the output without using the '-H' option.

grep pattern filename /dev/null

The /dev/null or null device is special file that discards the data written to it. So, the /dev/null is always an empty file.

Another way to print the filename is using the '-H' option. The grep command for this is

grep -H pattern filename

81. Write a command to print the file names in a directory that does not contain the word "july"?

grep -L july *

The '-L' option makes the grep command to print the filenames that do not contain the specified pattern.

82. Write a command to print the line numbers along with the line that has the word "july"?

grep -n july filename

The '-n' option is used to print the line numbers in a file. The line numbers start from 1

83. Write a command to print the lines that starts with the word "start"?

grep '^start' filename

The '^' symbol specifies the grep command to search for the pattern at the start of the line.

84. In the text file, some lines are delimited by colon and some are delimited by space. Write a command to print the third field of each line.

awk '{ if( $0 ~ /:/ ) { FS=":"; } else { FS =" "; } print $3 }' filename

85. Write a command to print the line number before each line?

awk '{print NR, $0}' filename

86. Write a command to print the second and third line of a file without using NR.

awk 'BEGIN {RS="";FS="\n"} {print $2,$3}' filename

87. How to create an alias for the complex command and remove the alias?

The alias utility is used to create the alias for a command. The below command creates alias for ps -aef command.

alias pg='ps -aef'

If you use pg, it will work the same way as ps -aef.

To remove the alias simply use the unalias command as

unalias pg

88. Write a command to display todays date in the format of 'yyyy-mm-dd'?

The date command can be used to display todays date with time

date '+%Y-%m-%d'

89.For LOOP

1. Rename all ".old" files in the current directory to ".bak":

for i in *.old   do  j=`echo $i|sed 's/old/bak/'`  mv $i $j  done

2. Change all instances of "yes" to "no" in all ".txt" files in the current directory. Back up the original files to ".bak".

for i in *.txt do  j=`echo $i|sed 's/txt/bak/'`  mv $i $j   sed 's/yes/no/' $j > $i  done

3. Loop thru a text file containing possible file names. If the file is readable, print the first line, otherwise print an error message:

for i in `cat file_list.txt` do  if test -r $i   

  then        

   echo "Here is the first line of file: $i"       

   sed 1q $i   

else

echo "file $i cannot be open for reading."      fi  done

How to print/display the first line of a file?

$> head -1 file.txt

$> sed '2,$ d' file.txt

How to print/display the last line of a file?

$> tail -1 file.txt

$> sed -n '$ p' test

How to display n-th line of a file?

$> sed –n '<n> p' file.txt

$> sed –n '4 p' test

$> head -<n> file.txt | tail -1

$> head -4 file.txt | tail -1

How to remove the first line / header from a file?

$> sed '1 d' file.txt

$> sed '1 d' file.txt > new_file.txt

$> mv new_file.txt file.txt

$> sed –i '1 d' file.txt

How to remove the last line/ trailer from a file in Unix script?

$> sed –i '$ d' file.txt

How to remove certain lines from a file in Unix?

$> sed –i '5,7 d' file.txt

How to remove the last n-th line from a file?

$> sed –i '96,100 d' file.txt   # alternative to command [head -95 file.txt]

$> tt=`wc -l file.txt | cut -f1 -d' '`;sed –i "`expr $tt - 4`,$tt d" test

How to check the length of any line in a file?

$> sed –n '<n> p' file.txt

$> sed –n '35 p' file.txt | wc –c

How to check if a file is present in a particular directory in Unix?

$> ls –l file.txt; echo $?

How to check all the running processes in Unix?

$> ps –ef

$> ps aux

$>ps -e -o stime,user,pid,args,%mem,%cpu

Combine multiple Rows to a Column – Oracle

SELECT SUBSTR (SYS_CONNECT_BY_PATH (NAME , ','), 2) FRUITS_LIST

FROM (SELECT NAME , ROW_NUMBER () OVER (ORDER BY NAME ) RN,

COUNT (*) OVER () CNT

FROM FRUITS)

WHERE RN = CNT

START WITH RN = 1

CONNECT BY RN = PRIOR RN + 1;

What is command to check space in Unix

df -k

What is command to kill last background Job

kill $!

What is difference between diff and cmp command

cmp -It compares two files byte by byte and displays first mismatch.

diff -It displays all changes required to make files identical.

What does $# stands for

It will return the number of parameters passed as command line argument.
