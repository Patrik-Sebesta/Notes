Linux comands
---
- RO mounted disk
````
fdisk -l
ntfsfix /dev/sda2
umount /dev/sda2
sudo mount -o uid=1000,gid=1000,rw /dev/sdXX
````
- found sizes 
````
 du -a | sort -n -r | head -n 10
````
- extend 
````
df -h
lvextend -rL +5G /var
````
- autostart 
````
[patrik.sebesta@localhost autostart]$ pwd 
/home/patrik.sebesta/.config/autostart
[patrik.sebesta@localhost autostart]$ ln -s  /usr/share/applications/terminator.desktop ./terminator.desktop 

[patrik.sebesta@localhost autostart]$ ll
total 0
lrwxrwxrwx. 1 patrik.sebesta patrik.sebesta 37 Oct  8 09:47 slack.desktop -> /usr/share/applications/slack.desktop
lrwxrwxrwx. 1 patrik.sebesta patrik.sebesta 42 Oct  8 09:51 terminator.desktop -> /usr/share/applications/terminator.desktop
````


- what is running on port 
````
netstat -tulpen | grep 12345
````

- check new added lines in logs 
````
for i in {40..55}; do echo -n "14:${i} - "; grep -E "Nov\ 30\ 13:${i}" /var/log/tm/afs.log | wc -l; done
````
