# Brute Force Menggunakan Burp Suite

![](Screenshot%20from%202021-12-17%2020-25-56.png)
1. Masuk ke halaman proxy > aktifkan intercept
2. Setelah masukk browsernya buka http://localhost:81/vulnerabilities/brute/
3. Masukkan kode random di username dan password
4. Setelah itu masuk lagi ke halaman brup suite![](Screenshot%20from%202021-12-17%2020-30-18.png)
5. Tekan ctrl+i atau klik kanan send to intruder
6. lalu masukk ke intruder![](Screenshot%20from%202021-12-17%2020-33-58.png)
7. add kata kunci yang ingin di bruteforce menggunakan add, tanda dolar untuk mentag data yang ingin di brute force![](Screenshot%20from%202021-12-17%2020-36-20.png)
8. Ubah attack type menjadi cluster bomb![](Screenshot%20from%202021-12-17%2020-36-59.png)
9. Setelah itu masuk ke payload, masukkan kata kunci untuk di brute force![](Screenshot%20from%202021-12-17%2020-38-55.png)
10. Jangan lupa masukkan payload ke duanya juga
11. Lalu masuk ke option![](Screenshot%20from%202021-12-17%2020-41-09.png)
12. masukkan 'welcome' ke greb match untuk menangkap kata kunci output dari 'welcome' yang akan keluar saat kata username dan password bernar.
13. setelah itu klik start attack![](Screenshot%20from%202021-12-17%2020-44-50.png)
14. username dan password yang benar akan muncul tanda "1" di baris "welcome"

## Referensi
https://medium.com/@faridadilazuarda29/dvwa-cara-melakukan-web-hacking-dengan-metode-brute-force-medium-level-75ca77d255