# The 4-way handshake WPA or WPA2 encryption protocol

After a couple of days that i am trying to understand the principles in the 4- way handshake between the client and the AP (Access Point), i think i got it pretty well.

After the explanation i will demonstrate the vulnerability in the WPA/WPA2 encryption protocol by Linux command.

**What is the handshake?  
**The handshake is a term that include the first four messages of the encryption connection process between the client that wants the WI-FI and the AP that provide it.

To understand the 4 stages we need firstly to get over few keys that will be essential:

PMK (Pairwise Master Key)  
PTK (Pairwise Transit Key)  
GTK(Group Temporal Key)  
GMK(Group Master Key)  
ANONCE  
SNONCE  
MIC

First of all we need to understand what every key is stand for to continue.  
**PMK- Pairwise Master Key:  
**Ok so for this key we need to understand a few things. PSK (Pre-Shared Key)and passphrase. they are the same but different. The passphrase is the password that we are giving to our network- to our AP. The PSK is the passphrase but he (the PSK) took it and translate it to 256 bits of string. In WPA/WPA2/personal the PMK is the PSK.  
Both the machines have the PMK in assumed the the client knows the password for the WI-FI.

**GMK- Group Master Key:  
**The GMK is used in this action to create the GTK, the GTK is generated on every AP and shared with the devices that are connected with him.

**PTK — Pairwise Transit Key:**  
The PTK is encryption for uni-cast traffic. In this example between the client and the AP.To get this encryption the client and the AP needs several parameters.  
PTK = PMK + ANONCE + SNONCE + MAC(AA) + MAC(SA)  
ANONCE- is a random number that the AP has made.  
SNONCE- is a random number that the client has made.  
MAC(AA)- the mac address of the AP (authenticator).  
MAC(SA)- the mac address of the client (supplicant).  
The PTK is depend on a higher-level key also — PMK.

**GTK- Group Temporal Key:  
**The GTK is the encryption for broadcast and multicast for the traffic between one AP to his clients. For every different AP there is a different GTK to secure the traffic in the “air” that belongs to the same network.All the clients that connect to the same AP have the same GTK.

MIC- Message Integrity Code, its like a stump from the sender who sent the message.

(STA -client)

![](https://miro.medium.com/max/1400/1*tQBzQybcy0-vcOnuklPZYw.png)

**Message 1:** AP sends to the client his ANONCE. Now the client has everything he needs to create the PTK because he got the ANONCE, it was the only thing that was missing for him.

**Message 2:** The client sends to the AP his SNONCE with a MIC, the MIC is mainly for the AP to recognize that this message is realy from this client, its like a signature (a high level algorithm signature).  
Now, after the AP got the message he has everything he needs to create the PTK and that is what he does.

**Message 3:** The AP sends to the client the GTK because he is going to be his new client.  
The client get the GTK and install it.

**Message 4:** The client sends to the AP that everything is OK and installed.

**Why it is important to understand the stages in the messages?  
**If we want to crack the WI-FI and we don’t have the passphrase (PSK), we need to capture the handshake between the client and the AP that we want to connect to. We can force the client to reconnect by simply attack him with deauthentication messages, and than capture the handshake. Now i know one way to crack the password by getting the PMK (PSK) that generate the PTK with all the parameters. After you make a long list of potential password, you use the command — aircrack-ng. What it does is that the command takes the handshake that you capture (specifically the first two messages) and separate the MIC from the other parameters that all together is equal to the PTK  
(PTK = PMK + ANONCE + SNONCE + MAC(AA) + MAC(SA)). Then the command runs the list with your potential passwords (your PSK (pre-shared key)) and put it together with the other parameters, and than it check if the MIC that the command gets from the combination is equal to the original MIC. This process takes lot of time.
# Sumber
[https://medium.com/@alonr110/the-4-way-handshake-wpa-wpa2-encryption-protocol-65779a315a64](https://medium.com/@alonr110/the-4-way-handshake-wpa-wpa2-encryption-protocol-65779a315a64)