[上一頁](https://jian-hong-wu.github.io/blog/)

$ ls -a

$ cd

$ pwd

$ uname

$ clear

$ cat

$ sudo

$ cp

$ su

$ mv

$ mkdir

$ touch

$ rm

$ rmdir

$ ifconfig

$ reboot

$ poweroff

$ man

$ sync

$ find

$ grep

$ du

$ df

$ gedit

$ ps

$ top

$ file

$ date

//取今天時間  
$ date -d “now” %Y-%m-%d 

//取昨天時間  
$ date -d “yesterday” %Y-%m-%d  
$ date -d “1 days ago” %Y-%m-%d  
//-d, –date=STRING         display time described by STRING, not `now’  
STRING可以為‘now’ 、 ‘yesterday’、 ‘n days ago’  
‘n days ago’  表示n天前的那一天

//取前天時間  
$ date -d “2 days ago” %Y-%m-%d 

//取下週一時間  
date -d 'next Mon' +%Y-%m-%d

//取上週一時間  
date -d 'last Mon' +%Y-%m-%d

