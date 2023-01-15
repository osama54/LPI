# Part 6
## Regular Expression 
Command|Detail
---|---|
grep -d skip -i --color=none ipv[46] /etc/\*|-d skip: Skip seraching in directory, -i: case insensentive,  ipv[46]: allow me to search for ipv4 or ipv6 
grep -d skip -i --color=none ipv[46] /etc/\* 2> /dev/null|Exclude all the errors
grep -d skip -i --color=none rfc [1-3]  /etc/\* 2> /dev/null| search for the range 
grep -d skip -i --color=none \\#\\ bootp  /etc/services|I have use \ before # becuase the hash is bash script command and use \ before the space for the same reason.
grep -d skip -i --color=none r.ot  /etc/services| search for any character r or ot
grep -d skip -i --color=none ro\*t  /etc/passwd| o*: Charactr present zero or more times 
grep -d skip -i  ro.\*t  /etc/passwd| .\*: Search for anything between the ro and t, rx rosfstrf  

---

Command|Detail
---|---|
grep -E --color=name ro+t /etc/passwd| We use extended regular like + we must include -E, + meaning to search for one o or multiple o like oooo
grep -E --color=name ro?t /etc/passwd| ?: zero or one 
grep -E --color=name root\|shutdown /etc/passwdgrep -E --color=name root\|shutdown /etc/passwd| \| pipe search root or shutdown 
grep -E --color=name "root|shutdown" /etc/passwd| Shell quoting ", display same result above 
grep -E --color=name "(^root|^shutdown)".\*bash$" /etc/passwd|
grep -E --color=name "root|shutdown" /etc/passwd|
grep -F -f search.txt --color=name /etc/passwd| search for the words in search.txt in /etc/passwd

#### Fgrep Egrep: old fashion command that deprecated, and now we need to use grep -F and grep -E.

---

                   echo " hello " > food.txt
                   echo "" >> food.txt
                   echo " hi " >> food.txt
##### above command will add empty line between hello and hi 

Command|Detail
---|---|
sed 's/cake$/cookies/' food.txt| replace all lines ends with cake with other word cookies.
sed '/^/d' food.txt| remove all blank lines. 

---

### Every command that is not built into the Bash shell is a program ( sometimes called a binary) that resides smewhere in the Linux virtual directory structure. 

          type grep 
       out: grep is aliased to `grep --color=auto'
above meaning that grep have defualt option that is color=auto        
                     
          unalias grep
remove the defualt option from grep 

Command|Detail
---|---|
whereis grep| locate grep files 
whereis type| cannot find information becuase type is built in bash shell
man -k which \| grep ^whreis \| tee -a studyme.txt| -k: find a kewword in man of command, -a: append result
locate word.txt|locate the file location
sudo updatedb|update the mlocate.db database
find / -name newword.txt 2> /dev/null | Find is flexible, / start searching at the start point and locate for all sub directories, if we put just / that meaning start from root and search all directories. 
find /home -name newword.txt 2> /dev/null| search in home directory
find /home -regex .\*word.txt|Match zero or on. 
find /etc -maxdepth 1 -name passwd| -maxdepth 1 search only in the directory and not the sub directories. 

#### File globbing| is when a file name is expanded in multiple file names that contain original file name
#### mlocate.db is the database the locate use to search, it is typically only updated on a daily basis ( i could't find file that just created ) so we need to use command sudo updatedb to update the database 
#### The whereis command will display files associated with a program, such as its man pages and its binary file, as well as any source file and info files
#### The locate command uses a database with file names to perform searches, making it fast than find. If the database is out-of-date, you’ll need to use the updatedb command and super user privileges to get it updated

### find search options
Command|Detail
---|---|
-cmin minutes|Searches for files with status that changed minutes ago
-empty|locates text files or directories that are empty
-group group-name|Searches for files that belong to the group-name group
-mmin minutes|Locates files with data that changed minutes ago
-name file-name|Searches for file namde file-name
-perm file-permissions|Locates file with the permissions of file-permissions
-regex regular-expression|Searches for files with a name matching the regular-expression pattern
-size file-size|Locates files with a size of file-size
-user username|Searches for files owned by username

##### regex(7) is another reference to the basic regular expression (BRE) term. It is derived from the fact that the man pages in the Linux Programmer

---
---
---

# Part 7 

Command|Detail
---|---|
ls -d /etc/|To see a directory's information, but not its contents
ls -d /etc/\*|will show me all the files and subdirectories, however, becuase use -d, it won't show any subdirectory contents
ls -d /etc/net\*|Find files or subdirectories whose name starts with net
ls -d /etc/\*net\*|find any files contain net 
ls -d /etc/network?|The question mark ? willdcard will match any characters in one charachter position 
ls -d /etc/liba\[os]\*|look for any files or subdirectory name that starts with liba and then has either o or u charachter, and then anythin after that
ls -d /etc/lib?\[a-z]\*| look for range or charachter 
file /etc/updatedb.conf| Determine a file's type 

#### File globbing| is when a file name is expanded in multiple file names that contain original file name. This occurs when you use wildcards. 

---

Command|Detail
---|---|
stat hello.txt|we can see the last access date, modification date, and change date 
touch hello.txt|if we need to update all the timestamps ^ we use touch for that 
touch -m hello.txt|only modification time changes
rm hello.txt|remove file without any information 
rm -i hello.txt|will ask me before delete the file
rm -vi hello.txt|will ask me before delete the file and tell me the file is removed
rm -i \*.txt|Delete all files with .txt  
rm -i $(ls \*.txt)|same result us upper ^

---

Command|Detail
---|---|
cp hello.txt newhello.text|copy the file to the new name 
cp hello.txt Documents/newhello.txt| copy file to new directory
mv hello.txt Documents/| move file to new directory
mv newhello.txt Document/hello2.txt|move and change the file name 
mv -i hello2.txt Documents/|if find tha file with same name in destination, will ask me before do that 

---

Command|Detail
---|---|
ls -F|list the subdirectory in current directory 
mkdir Exam|create Exam directory
ls -dl Exam|give me a deal of information 
mkdir -p Study/Cert|cannot create parent directory without -p 
ls -FR|lock for all subdirectory
rmdir Directory/
ls -R Test|see diirectory tree all files
rm -iR|Use either -r or -R on rm to remove files in directory tree| 

#### Child directory is another name for a Subdirectory
#### Mkdir remove only empty directory, rm -R temove files in any directory tree

































































