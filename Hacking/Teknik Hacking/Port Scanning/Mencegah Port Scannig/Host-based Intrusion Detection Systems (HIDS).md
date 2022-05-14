# Host-based Intrusion Detection Systems (HIDS)

  
Intrusion detection can be divided into three broad categories: NIDS, HIDS, and vulnerability scans. In this post I will review several options for HIDS and OpenVAS (vulnerability scanner). If you are wanting information on NIDS, see the [NIDS sticky](http://ubuntuforums.org/showthread.php?t=1477696)  
  
Most Windows users are familiar with [HIDS](http://en.wikipedia.org/wiki/Host-based_intrusion_detection_system). Examples include virus and spyware scanners. HIDS monitor system files and detect unauthorized changes and known threats / [malware](http://en.wikipedia.org/wiki/Malware).  
  
Many Linux users may feel these tools are of limited utility because:  
  
1. These tools are notorious for quirks, hiccups, and the sky is falling. As with the boy who cried wolf, excessive warnings and false positives tend to get ignored.  
  
2. These tools detect only known vulnerabilities and thus do not protect against "[zero day exploits](http://en.wikipedia.org/wiki/Zero_day_attack)". Known vulnerabilities are generally patched rapidly in Linux. Thus many people are of the opinion keeping their systems up to date is sufficient and these tools are superfluous.  
  
3. The majority of these tools are command line tools with limited, if any, graphical interface (web interfaces are more common). Some people tend to shy away from tools lacking a graphical interface.  
  
4. Although every OS has potential security holes, many users find Ubuntu is "secure enough" such that additional measures are not warranted . For an overview of this mentality, see [this discussion](http://www.theregister.co.uk/2004/10/22/security_report_windows_vs_linux/) .  
  
  
This post is for those who are interested in "learning the ropes" and will review HIDS tools. IMO it is best to try these tools out **before you suspect your system is compromised**.

## Source
https://ubuntuforums.org/showthread.php?t=1477662
