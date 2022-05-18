Nonce + key reuse attack in AES CTR merupakan serangan yang bisa dilakukan jika kita menggunakan Nonce + key berulang kali pada enkripsi AES pada mode CTR. Ini bisa mengakibatkan data yang tadinya kita enkripsi tadi menjadi ter de-enkripsi.

POC:

Jika "encrypted_string1" dan "encrypted_string2" menggunakan Key + nonce yang sama dan kita tau plain text dari "encryped_string1", kita dapat men-XOR "encrypted_string1" dengan "encrypted_string2" lalu hasilnya kita XOR dengan plain text dari "encrypted_string1", Maka kita akan mendapatkan plain text dari "encrypted_string2". Fungsi pythonnya kurang lebih seperti ini:

blob = encryped_string1 ^ encryped_string2

decrypted_string2 = blob ^ plainText_string1

Untuk lebih jelasnya bisa lihat CTF milik john hammond:

https://www.youtube.com/watch?v=Gtfr1dBGzHg

Contoh program Nonce + key reuse attack in AES CTR: