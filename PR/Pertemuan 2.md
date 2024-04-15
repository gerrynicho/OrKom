# Pekerjaan rumah: Buku Hamacher 2.1, 2.2 & 2.4
### 2.1 [E] Given a binary pattern in some memory location, is it possible to tell whether this pattern represents a machine instruction or a number?
```md
Tidak bisa, karena angka direpresentasikan oleh angka desimal, hexadesimal, oktal yang kemudian dijadikan menjadi biner. Sedangkan instruksi mesin dari asalnya sendiri sudah merupakan angka-angka biner. Jadi tidak bisa dibedakan angka biner di dalam lokasi memory jika mereka adalah instruksi mesin atau angka biasa.
```
### 2.2 [E] Consider a computer that has a byte-addressable memory organized in 32-bit words according to the big-endian scheme. A program reads ASCII characters entered at a keyboard and stores them in successive byte locations, starting at location 1000. Show the contents of the two memory words at locations 1000 and 1004 after the word “Computer” has been entered.
```md
ASCII, sebuah format karakter yang digunakan oleh komputer sudah mendefiniskan bahwa sebuah karakter terdiri dari 8 bit, sedangkan 1 byte terdiri dari 8 bit. Jadi, setiap karakter akan memakan 1 byte.

Di dalam sebuah lokasi memory, terdapat 32-bit word (32 bit --> 4 byte) sehingga di dalam lokasi memory 1000 akan terdapat 4 byte dan dari lokasi 1000 di-increment 4 byte lagi yang menjadi lokasi 1004 (sebuah lokasi yang memiliki 32-bit word yang baru)

Kata "Computer" terdiri dari 8 karakter, sehingga memakan 8 byte sehingga kita memerlukan 2 buah 32-bit word (2 lokasi memory) untuk menyimpan kata "Computer" sehingga kita pisahkan saja "Comp" dan "uter" menjadi sebuah word unik sendiri dengan "Comp" menempati lokasi 1000 dan "uter" menempati lokasi 1004.

Dalam bahasa mesin, ASCII diubah menjadi hexadesimal dan kemudian diubah menjadi biner. Berikut adalah hasilnya:
"C" = 43 (hexadecimal) = 01000011 (biner)
"o" = 6F (hexadecimal) = 01101111 (biner)
"m" = 6D (hexadecimal) = 01101101 (biner)
"p" = 70 (hexadecimal) = 01110000 (biner)

"u" = 75 (hexadecimal) = 01110101 (biner)
"t" = 74 (hexadecimal) = 01110100 (biner)
"e" = 65 (hexadecimal) = 01100101 (biner)
"r" = 72 (hexadecimal) = 01110010 (biner)

Big-endian scheme, yaitu urutan byte yang paling signifikan berada di lokasi memory yang paling rendah.
Ketika kita masukan kata "Comp" dan "uter" ke dalam lokasi memory, maka hasilnya akan menjadi:
Lokasi 1000: 01000011 01101111 01101101 01110000
              (43)      (6F)     (6D)     (70)
              'C'       'o'      'm'      'p'
Lokasi 1004: 01110101 01110100 01100101 01110010
              (75)      (74)     (65)     (72)
              'u'       't'      'e'      'r'
```
### 2.4 [E] Registers R4 and R5 contain the decimal numbers 2000 and 3000 before each of the following addressing modes is used to access a memory operand. What is the effective address (EA) in each case?
(a) 12(R4) <br/>
(b) (R4,R5) <br/>
(c) 28(R4,R5) <br/>
(d) (R4)+ <br/>
(e) −(R4) <br/>
```md
EA (Effective Address) adalah alamat efektif yang digunakan untuk mengakses sebuah operand di dalam memory.

(a) 12(R4)
    EA = R4 + 12 = 2000 + 12 = 2012
(b) (R4,R5)
    EA = R4 + R5 = 2000 + 3000 = 5000
(c) 28(R4,R5)
    EA = ( (R4 + R5) + 28) = ( (2000 + 3000) + 28) = 5028
(d) (R4)+
    EA = R4 = 2000
    lalu R4 = R4 + 4 = 2000 + 4 = 2000
    (EA mengambil literal value R4, bkn mengambil address R4)
    (kita tambah 4 karena kita menggunakan 32-bit word (4 byte))
(e) -(R4)
    EA = R4 - 4 = 2000 - 4 = 1996
```