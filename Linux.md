Linux comands
---
- RO mounted disk
````
fdisk -l
sudo mount -o remount,uid=1000,gid=1000,rw /dev/sdXX
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