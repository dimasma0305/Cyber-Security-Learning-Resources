# Menambahkan Hex Ke Foto
## Membuat foto menjadi hex
```
xxd -plain test.png > test.hex
```
## Mengubah hex di foto
```
mousepad test.hex
```
### Konfersi hex
https://www.rapidtables.com/convert/number/ascii-to-hex.html
## Mengubah hex jadi foto
```
xxd -ps -r test.hex > test2.png
```
## Melihat perbedaan file
```
diff -a test.png test2.png
```
## Melihat binary file
```
cat test2.png
```
## Alternatif (singkat)
Untuk meng-append sebuah byte ke png bisa menggunakan
```
echo "dimas maulana ganteng sekali" >> test.png
```