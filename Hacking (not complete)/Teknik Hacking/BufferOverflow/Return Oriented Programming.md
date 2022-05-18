![](https://dimaswiki.files.wordpress.com/2022/05/fb_img_1651411464669.jpg?w=720)
# Return Oriented Programming

ROP (Return Oriented Programing) adalah jenis Stack Smashing Attack yang memanfaatkan Vulnerability di sebuah program (e.g., Buffer overflow) untuk mengubah jalannya suatu program, dengan memanipulasi call stack didalamnya. Biasanya ini digunakan oleh attacker untuk mendapatkan shellcode execution.

Contoh Scenario:

Seorang hacker masuk ke sebuah sistem lewat kerentanan di web application sebuah perusahaan.

Hacker ini mendapatkan akses berupa user www-data, dimana www-data ini merupakan akses yang memiliki privilage sangat minim.

Hacker tersebut ingin mendapatkan akses user tertinggi yaitu user root, oleh karena itu sang hacker menganalisa semua yang bisa dia akses di sistem tersebut.

Sang hacker menemukan bahwa ada beberapa program ELF (Executable and Linkable Format) yang bisa di eksekusi semua user di mesin tersebut dan salah satunya memiliki setuid user root.

Sang hacker menganalisa file ELF tersebut di mesin-nya, dan menemukan bahwa program tersebut memiliki vulnerability Buffer Overflow.

Sang hacker membuat skenario yang sama dengan yang ada di sistem korban di dalam mesinnya, hal ini dia lakukan untuk melakukan debugging dan test untuk program payload yang dia buat untuk mengehack program itu.

Setelah beberapa trial dan error, payload itupun selesai. Sang hacker menjalankan program payload itu di sistem korbannya dan dia berhasil mendapatkan akses root.

Dan tidak lupa sebagai hacker yang profesional dia menyisipkan backdoor dan juga program untuk menghapus jejaknya di mesin si koban.

contoh program payload ROP:  
https://github.com/dimasma0305/CTF_Solution_Writeup/blob/main/PicoCTF-Penyelesaian/picoCTF%202022.md#ropfu

  
picoCTF ropfu:  
https://play.picoctf.org/practice/challenge/292?category=6&originalEvent=70&page=1

  
Referensi:  
https://en.wikipedia.org/wiki/Return-oriented_programming  
https://github.com/evyatar9/Writeups/tree/master/CTFs/2022-picoCTF2022/Binary_Exploitation/300-ropfu