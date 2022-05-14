# Intro - What is snort and who should use it ?

  
Snort is a [NIDS](http://en.wikipedia.org/wiki/Network_intrusion_detection_system) tool. NIDS tools monitor network traffic for suspicious activity. While there are other tools (system (firewall) logs, wireshark, tcpdump, etc) the "problem" with these tools is the sheer volume of network packets makes it difficult to impossible to detect suspicious network activity. Snort monitors your network traffic and generates "alerts" based on the snort rule set. One then reviews a smaller number of alerts, although by it's nature snort often generates a large volume of "false positives".  
  
Note: IMO, in general, snort is used to monitor network traffic on large LAN and/or to public servers such as LAMP. If you are wanting to use snort it is assumed you understand at least the basics of networking protocols (udp/tcp/icmp). If you need a review [This site](http://security.maruhn.com/) has some outstanding tutorials (see the [networking concepts](http://security.maruhn.com/networking-concepts/) and [Tutorial](http://security.maruhn.com/iptables-tutorial/) links).  
  
Note: Installing, configuring, and monitoring snort will take some time and effort, especially with the initial installation. Learning to use snort, understanding alerts, and customizing the snort rules is beyond this tutorial and comes with practice, Google, and reading the [snort documentation](http://www.snort.org/docs).  
  
[Snort users manual (PDF)](http://www.snort.org/assets/125/snort_manual-2_8_5_1.pdf)  
  
Note: By design, snort generates "False positives" and to use snort one will need to become familiar with snort rules. Responding to snort alerts is as much an art as a science and although I can give you a few general tips, nothing replaces hands on experience with snort.  
  
Note: Using snort or reading the (iptables) logs may induce an acute paranoid state in susceptible individuals. Take a deep breath, Don't panic, and read / google search the alerts.  
  
In this set of posts I will show you how to install and configure snort using postgresql and [BASE](http://base.secureideas.net/screens.php). BASE is a web based a graphical tool to monitor snort alerts. Postgresql is a database used to log snort alerts. You could use mysql as an alternate if you prefer.  
  
**While apt-get will install the necessary packages from the Ubuntu repositories, there is a moderate amount of post-install configuration that is required.**  
  
My advice is to install a minimal Ubuntu system using the server CD (select install a minimal system) or the [minimal CD](https://help.ubuntu.com/community/Installation/MinimalCD).  
  
There is an overview of how to use the minimal CD [here](http://www.psychocats.net/ubuntu/minimal) .  
  
This will result in a small command line only system. You may then install openssh-server and ssh into your snort machine (makes it easier to copy and paste the commands).

## Source
https://ubuntuforums.org/showthread.php?t=1477696