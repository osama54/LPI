Commands|Detail
---|---|
tty|View which ssh session
whoami|View Current user login in
pwd|View current directory
ls|View files in current directory
ls -d|To see a directory's information, but not its contents  
ls directory-name|View the current files in the specified direcotry 
cd ..|Going to take me level up directory 
cd ../..|Going to take me two levels up
cd -| take me back to last directory i was just it 
cd|back to home

#### Linux uses virtual directory structure, we will not see the device names in the directory like windows c: d: . 
###### Windows: C:\Users\Osama\Document\
###### Linux: /home/osama/documents
###### Linux: /usr/bin

### File System hirearchy standard ( FHS ) :
FHS|Detail 
---|---|
/boot|Boot loader files
/etc|Configuration files (System & apps)
/home|User files
/media|Removable media
/mnt|Removable media (Older location)
/opt|Thir-party apps
/tmp|Temoporart files
/usr|linuxprogram data
/var|Variable data (example: log files)


### Sub directory part of the FHS:
FHC sub|Detail
---|---|
/usr/bin|Linux user program binaries
/usr/sbin|Linux admin program binaries
/usr/local|Local installation program data


Absolute|Relative
---|---|
Always start with /|must be in directory the contain the file
ls /var/log/|ls var
ls/home/osama/documents|ls document
cd /var/log|

---
---
---

Commands|Detail
---|---|
uname|Show the name of the kernal that currently running
uname -r|Release option, but version info
uname -v|Version option, but build info
uname -a|show me all kernal information
bash --version|show me the version of the bash
type pwd|type show me if the pwd command build in the bash shell or not
which| find where is the command is located 
man| find the manual for the command 
info| find more detail about the command
history| find previous commands used
!!|recall the command entered
cat .bash_history|
history -w|force this history list to written in .bash_history
history -c| clear history list

#### when display my history using the history command, notice that it doesn't exactly contain the same command when display cat .bash_history command, this is becuase the history displays what is called the history list and the history list exists in memory until you log out.
##### but there is special command to force this history list to written in .bash_history 
### !9: use ! and the number of command and it will be executed directy without typing the full command
### help: provides information on commands built into the bash shell
### man and info: provides help for external commands

#### built-in command: are part of the bash shell 
#### external command: are not: Programs that reside within the virtual directory structure /bin

##### ex: type uname: " uname is hashed " that mean the uname used recently and is cashed in the memory
##### use which to find the 

---
---
---

# Part 3 
Commands|Detail
---|---|
ls -a|Show all hiden files in the directory
ls -f|Few file indicator, /=directory,  * executable file, @=symbolic linc
ls -l|Provide the detail files
ls -alF|Well see all files information, all hidden files, classification indicatiors
cat /proc/version|Contain kernal information like uname -r
cat /etc/passwd|show passwd 
head /etc/passwd|show only the head of the passwd file ( first 10 line )
head -2 /etc/passwd|show only first two line 
tail /etc/passwd|show the last 10 lines of the passwd file
tail -2 /etc/passwd|show the last 2 lines os passwd file 
tail -f /var/log/secure|show the last message of the log file and then display any new messages come in (Press Ctrl+c to stop process)

---
Commands|Detail
---|---|
cat /var/log/boot.log or /var/log/kern.log|Display boot log
more /var/log/boot.log|Show only one page, and use space and enter to view more
less /var/log/boot.log|same as more but we can use page down and page up to change between pages and also can search in file by press /typesomething and press enter 
wc|show the number of .lines, word, and bytes in the text file 
wc -l|show only the lines in the text file
wc -w|For number of words 
wc -c|for number of bytes 
unic word.txt|show only the unique lines not dublicate lines 
uniq -c|the the number of time that line occurs (dublicated)
uniq -d|ony prints the duplicate lines one time
uniq -D|ony prints the duplicate lines all time 
touch work.txt|craete text file 
echo "hello" > word.txt|insert hello to word file 
echo "world" >> word.txt
nl /etc/passwd|it just give each line number (Did not number the blank lines) see only the number associated with number lines 

#### for uniq command the lines must be next each other to know it is duplicate. 
                  hello
                  world
                  world
                  world
                  hello
in above example the uniq -D will show only the world is duplicated 

--- 
### A hash is A fixed-length string of letters and numbers also called 
###### *Hash value *Fingerprint *Signature *Message digest 

Commands|Detail
---|---|
ls /var/log|folder contain the log files 
cp /var/log/syslog.2.gz .|dot . meaning copy the file to my current location 
md5sum /var/log/syslog.2.gz|give me hash value using MD5
sha256sum /var/log/syslog.2.gz|give me hash value using sha 256 
sha512sum /var/log/syslog.2.gz|give me hash value using sha 512

---
---
---

# Part 4 

Commands|Detail
---|---
sot world.txt|
sort file.txt|sort a text file alphabetically 
sort -n numbers.txt|sort file numerically (just sort no change for the original file)
paste alpha.txt numbers.txt| combine files in sibe-by-side format
split -l 2 alpha.txt| split the file to multiple files each one contain only two lines from the original file ( the new file name is xaa, xab, xac)
split -l 2 alpha.txt NewFile|Change the file name exported to Newfileaa, Newfileab, Newfileac
cut| cut out sections of a specified file ( does not change the original file )
cut -d : f7|seperate fields in record, -f which field of each record to view 
cut -c1-10 /etc/passwd|pull out charachters one to 10 of each record
#### paste put alpha.txt in first column and numbers.txt in the second column

---

Commands|Detail
---|---
tr : $ < /etc/passwd| : it is the character that i want to change, $ the new value ( tr doesn't change the actual file) 
od /etc/passwd|display files in octal code as well as other formats (useful for display binary code)
od -A x -t x1z -v /bin/cat|Get binary program displayed in hexadecimal
sed 's/chocolate/strawberry/' food.txt|replace only first line contain chocolate with strawberry in the food.txt file
sed 's/chocolate/strawberry/g' food.txt|Change all chocoloate words, g:global

### sed: is Fast becuase it reads a file a line at a time and makes the desired changes to each line

---

Commands|Detail
---|---
grep root /etc/passwd|search word root in /etc/passwd (show root in red )
grep --color=never root /etc/passwd|Show root without color
grep -i ROOT /etc/passwd|For case insensitive search
grep -i ^ROOT /etc/passwd|search word at the begining in the line
grep -i ROOT$ /etc/passwd|search word at the end in the line

---
---
---

# Part 5 

Commands|Detail
---|---
tr n N < /etc/passwd|Change all lower case n to upper case N 
sort alpha.txt > newAlpha.txt|Sort alpha file and save result to newAlpha.txt (Sort doens't change the original file) 
grep --color==never bash$ /etc/passwd > keepSearch.txt|Save grep output to keepSearch
sort alpha.txt >> newAlpha.txt|use double >> to add the file to end of newAlpha.txt, if use onle one > the previous txt will removed. 
grep nologin$ /etc/passwd \| wc -l|word count word for nologin
cut -d: -f1,7 /etc/passwd \| sort \| tee data.txt \| less|cut and sort, and put the result in data.tx and view it in less. 
tee|Directing STDOUT to two different location

### Redirection: is the ability to change the method to SEND or RECEIVE text from the default method. 
#### STDIN: Standard Input
#### STDOUT: Standard Output
#### STDERR: Standard Error
##### \>Creates a new file or overwrites file contents with STDOUT
##### \>>Appends STDOUT to a file (but will create the file, if it does not exist) 



























































