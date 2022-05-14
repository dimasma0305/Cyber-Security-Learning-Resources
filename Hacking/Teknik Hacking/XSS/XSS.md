XSS merupakan kependekan yang digunakan untuk istilah cross site scripting. XSS merupakan salah satu jenis serangan injeksi code. XSS dilakukan oleh penyerang dengan cara memasukkan kode HTML atau client script code lainnya ke suatu situs. Serangan ini akan seolah-olah datang dari situs tersebut

Singkatnya JS injection.

![[Pasted image 20220225175233.png]]
https://www.youtube.com/watch?v=KHwVjzWei1c
![[Pasted image 20220225175531.png]]

catatan: sandbox bisa mencegah xss, tapi jika kamu bisa keluar dari box tersebut, mungkin bisa menjalankan XSS.
work in safari:

```
<base href="javascript:/a/-alert(1)///////"
<a href=../lol/safari.html>test</a>
<a href>haha</a>
```
reference: https://www.youtube.com/watch?v=eQFbG6CwwdI