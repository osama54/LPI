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

































































































