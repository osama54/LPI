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












































































































