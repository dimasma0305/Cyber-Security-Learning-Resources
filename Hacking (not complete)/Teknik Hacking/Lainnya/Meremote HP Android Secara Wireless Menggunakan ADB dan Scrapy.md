# Meremote HP Android Secara Wireless Menggunakan ADB dan Scrapy
## Wireless
The application communicates with the device over ''adb'', so it should be easy to make it work wirelessly: Connect to a device over Wi-Fi.

It was not counting on an adb bug preventing <code>adb reverse</code> to work over a connection established by <code>adb connect</code>.

Therefore, we implemented a workaround to fallback using <code>adb forward</code> (and reversing the client/server roles) when <code>adb reverse</code> fails.

## How to run scrcpy wirelessly? 
Here are the steps:

1. Connect the device to the same Wi-Fi as your computer

2. Get your device IP address (in Settings → About phone → Status)

3. Enable adb over TCP/IP on your device: <code>adb tcpip 5555</code>

4. Connect to your device: <code>adb connect DEVICE_IP:5555</code> (replace <code>DEVICE_IP</code>)

5. Unplug your device

6. Run scrcpy as usual

To switch back to USB mode: <code>adb usb</code>.

As expected, the performances are not the same as over USB.

The default scrcpy bit-rate is 8Mbps, which is probably too much for a Wi-Fi connection. Depending on the use case, decreasing the bit-rate and the resolution may be a good compromise:
 scrcpy --bit-rate 2M --max-size 800
For people in a hurry:
 scrcpy -b2M -m800
Note that while it now works over TCP/IP, this is not an optimal solution for streaming a video wirelessly, since the raw stream is still sent over TCP, where a packet loss is very bad for latency, due to head-of-line blocking. But it’s better than nothing!

Under good conditions, it may work pretty well:

On the video, ''scrcpy'' is started over USB on the laptop with ''Debian'' (on the right), and over Wi-Fi on the Mac (on the left).

You can now build, install and run the new version!

Enjoy!

## Example  
> adb tcpip 5555
>adb connect 192.168.43.1:5555
>scrcpy

## Interesting Link 
[Aircrack-ng](Aircrack-ng.md)
https://stackoverflow.com/questions/14654718/how-to-use-adb-shell-when-multiple-devices-are-connected-fails-with-error-mor
https://askubuntu.com/questions/1251205/remotely-control-android-smartphone-from-ubuntu-16-04

## Source
https://www.genymotion.com/blog/open-source-project-scrcpy-now-works-wirelessly/
