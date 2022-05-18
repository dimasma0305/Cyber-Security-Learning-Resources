# How to check if port is in use on Linux or Unix
## How to check if port is in use in

To check the listening ports and applications on Linux:

1.  Open a terminal application i.e. shell prompt.
2.  Run any one of the following command on Linux to see open ports:  
    ```a
	sudo lsof -i -P -n | grep LISTEN  
    sudo netstat -tulpn | grep LISTEN  
    sudo ss -tulpn | grep LISTEN  
    sudo lsof -i:22 ## see a specific port such as 22 ##  
    sudo nmap -sTU -O IP-address-Here
	```
3.  For the latest version of Linux use the ss command. For example, ss -tulw

Let us see commands and its output in details.
## Option #1: lsof command

The syntax is: 
```a
sudo lsof -i -P -n  
sudo lsof -i -P -n | grep LISTEN  
doas lsof -i -P -n | grep LISTEN ### [OpenBSD] ### 
```
Sample outputs:  

[![](data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjUyIiB3aWR0aD0iNTk5IiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZlcnNpb249IjEuMSIvPg==)![Fig.01: Check the listening ports and applications with lsof command](https://www.cyberciti.biz/media/new/faq/2016/11/lsof-outputs.png)](http://www.cyberciti.biz/faq/unix-linux-check-if-port-is-in-use-command/lsof-outputs/)

Fig.01: Check the listening ports and applications with lsof command

Consider the last line from above outputs:

sshd    85379     root    3u  IPv4 0xffff80000039e000      0t0  TCP 10.86.128.138:22 (LISTEN)

-   **sshd** is the name of the application.
-   **10.86.128.138** is the IP address to which sshd application bind to (LISTEN)
-   **22** is the TCP port that is being used (LISTEN)
-   **85379** is the process ID of the sshd process

## Option #2: netstat command

You can check the listening ports and applications with netstat as follows.

### Linux netstat syntax

Run netstat command along with [grep command](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/ "See Linux/Unix grep command examples for more info") to filter out port in LISTEN state:  
```a
netstat -tulpn | grep LISTEN
```
The netstat command deprecated for some time on Linux. Therefore, you need to use the ss command as follows: 
```a
sudo ss -tulw  
sudo ss -tulwn  
sudo ss -tulwn | grep LISTEN
```
![Linux check if port is in use using ss command](https://www.cyberciti.biz/media/new/faq/2016/11/Linux-check-if-port-is-in-use-using-ss-command.png)  
Where, ss command options are as follows:
-   **-t** : Show only TCP sockets on Linux
-   **-u** : Display only UDP sockets on Linux
-   **-l** : Show listening sockets. For example, TCP port 22 is opened by SSHD server.
-   **-p** : List process name that opened sockets
-   **-n** : Don’t resolve service names i.e. don’t use DNS

### FreeBSD/MacOS X netstat syntax
```a
netstat -anp tcp | grep LISTEN  
netstat -anp udp | grep LISTEN
```
### OpenBSD netstat syntax
```a
netstat -na -f inet | grep LISTEN  
netstat -nat | grep LISTEN
```
## Option #3: nmap command

The syntax is:  
```a
$ sudo nmap -sT -O localhost  
$ sudo nmap -sU -O 192.168.2.13 ##[ list open UDP ports ]##  
$ sudo nmap -sT -O 192.168.2.13 ##[ list open TCP ports ]##
```
Sample outputs:  

![Fig.02: Determines which ports are listening for TCP connections using nmap](https://www.cyberciti.biz/media/new/faq/2016/11/nmap-outputs.png)](https://www.cyberciti.biz/media/new/faq/2016/11/nmap-outputs.png)

Fig.02: Determines which ports are listening for TCP connections using nmap

You can combine TCP/UDP scan in a single command: 
```a
sudo nmap -sTU -O 192.168.2.13
```
## A note about Windows users

You can check port usage from Windows operating system using following command:
```a
netstat -bano | more  
netstat -bano | grep LISTENING  
netstat -bano | findstr /R /C:"[LISTEING]"  
```

## Conclusion

This page explained command to determining if a port is in use on Linux or Unix-like server. For more information see the [nmap command](https://www.cyberciti.biz/networking/nmap-command-examples-tutorials/ "See Linux/Unix nmap command examples for more info") and lsof command page [online here](https://github.com/lsof-org/lsof) or by typing the [man command](https://bash.cyberciti.biz/guide/Man_command "See Linux/Unix man command examples for more info") as follows: 
```a
man lsof  
man ss  
man netstat  
man nmap
```

## Source
https://www.cyberciti.biz/faq/unix-linux-check-if-port-is-in-use-command/