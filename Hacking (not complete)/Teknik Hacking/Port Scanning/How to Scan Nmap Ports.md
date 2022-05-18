# How to Scan Nmap Ports

To **scan Nmap ports** on a  remote system, enter the following in the terminal:

```a
sudo nmap 192.168.0.1
```

Replace the IP address with the IP address of the system you’re testing. This is the basic format for **Nmap**, and it will return information about the ports on that system.

In addition to scanning by IP address, you can also use the following commands to specify a target:

To scan a host:

```a
nmap www.hostname.com
```

To scan a range of IP addresses (.1 – .10):

```a
nmap 192.168.0.1-10
```

To run **Nmap** on a subnet:

```a
nmap 192.168.0.1/13
```

To scan targets from a text file:

```a
nmap –iL textlist.txt
```

**Note:** The developers at nmap.org provide a test server that you can experiment on, located at [scanme.nmap.org](http://scanme.nmap.org/). You can use this to test your Nmap utility.

## Scan a Single Port, All Ports, or Series

[Nmap commands](https://phoenixnap.com/kb/nmap-command-linux-examples) can be used to scan a single port or a series of ports:

Scan port 80 on the target system:

```a
nmap –p 80 192.168.0.1
```

Scan ports 1 through 200 on the target system:

```a
nmap –p 1-200 192.168.0.1
```

Scan (Fast) the most common ports:

```a
nmap –F 192.168.0.1
```

To scan all ports (1 – 65535):

```a
nmap –p– 192.168.0.1 
```

## Other Types of Nmap Port Scans

Different types of scans can be performed:

To scan using TCP connect (it takes longer, but is more likely to connect):

```a
nmap –sT 192.168.0.1
```

To perform the default SYN scan (it tests by performing only half of the TCP handshake):

```a
nmap –sS 192.168.0.1
```

To instruct Nmap to scan UDP ports instead of TCP ports (the **–p switch** specifies ports 80, 130, and 255 in this example):

```a
nmap –sU –p 80,130,255 192.168.0.1
```

Run a fast scan on the target system, but bypass host discovery. (Host discovery uses **ping**, but many server firewalls do not respond to **ping** requests. This option forces the test without waiting for a reply that may not be coming):

```a
nmap –Pn –F 192.168.0.1 
```

The **nmap** utility can be used to detect the operating system of a particular target:

```a
nmap –A 192.168.0.1
```

It can also be used to probe for the services that might be using different ports:

```a
nmap –sV 192.168.0.1
```

**Note:** The **–sV** option can be tuned to be more or less aggressive in its scan. Use the **––version-intensity 2** option to specify the level of testing. Replace the number 2 with a number from 0 (light testing) to 9 (run all probes). The more intense the testing, the longer the scan will take.

## Common Ports

Here is a brief list of standard ports and their designations:

-   21 – FTP
-   22 – SSH
-   25 – SMTP (sending email)
-   53 – DNS (domain name service)
-   80 – HTTP (web server)
-   110 – POP3 (email inbox)
-   123 – NTP (Network Time Protocol)
-   143 – IMAP (email inbox)
-   443 – HTTPS (secure web server)
-   465 – SMTPS (send secure email)
-   631 – CUPS (print server)
-   993 – IMAPS (secure email inbox)
-   995 – POP3 (secure email inbox)

A [Linux firewall](https://phoenixnap.com/kb/iptables-tutorial-linux-firewall) can be configured to block all traffic on a particular port.

For example, a firewall can be set to block Port 80, but users won’t be able to load any website in that case. You can use firewall rules to allow some ports, but block others. Use a firewall in conjunction with other [network security tools and software](https://phoenixnap.com/blog/best-network-security-tools) to scan traffic on a particular port, and to watch for suspicious traffic.

![example of running a scan on apache](https://phoenixnap.com/kb/wp-content/uploads/2021/04/nmap-open-ports-1.png)

## Nmap Scanning Best Practices

You should only use **Nmap port scanning** on servers that you own, or that you have permission to scan. Often, port-scanning is seen as an aggressive method, or a prelude to [a cyber attack](https://phoenixnap.com/blog/cyber-security-attack-types). It is also considered a bad practice to tie up a server’s resources by using Nmap to run repeated scans on the same target.

It is possible that during your scan, you may find unusual activity. For example, you may see a service running on an unusual port number. This means there is something strange going on, and should be investigated.

The **OS and Service scanning options** are helpful for scanning a particular port or service to get more information. If a service is running on a non-default port, it might be by design – or it might suggest there is a security breach.

Ports often have a default usage. Most ports under 1000 are dedicated and assigned to a specific service.

Conclusion

This guide provided an overview of **Nmap scanning and how you can use it for testing ports in Linux**. You should now understand how ports work, and why it is important to know how they are used.

Nmap adds a versatile tool to any system administrator’s arsenal for debugging and locating security flaws.

## Source
https://phoenixnap.com/kb/nmap-scan-open-ports