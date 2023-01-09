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















































































