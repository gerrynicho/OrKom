# Pekerjaan rumah: Buku Hamacher 3.3
### 3.3 What is the difference between a subroutine and an interrupt-service routine?
```md
Perbedaan subroutine dan interrupt-service routine terletak di bagian awal da bagian akhir routine. Subroutine mulai bekerja ketika sebuah program memanggil subroutine secara eksplisit. Sedangkan interrupt-service routine hanya mulai bekerja ketika menerima sebuah signal interrupt dari program. Lalu ketika subroutine sudah selesai, ia kembali (return) ke instruction yang memanggil subroutine tersebut, sedangkan interrupt-service routine kembali ke instruction yang menyebabkan signal interrupt (instruction terakhir sebelum muncul signal interrupt) dan bukan ke instruction yang memanggil interrupt-service routine untuk meengurus (handle) signal interrupt.
```

### RANGKUMAN DIRECT MEMORY ACCESS DARI INTERNET
```md
### Pengertian DMA
Direct Memory Access adalah sebuah teknik yang digunakan untuk memindahkan data dari memory ke perangkat I/O tanpa melibatkan CPU. DMA memungkinkan CPU untuk melakukan pekerjaan lain sementara DMA mengurus transfer data dari memory ke perangkat I/O.

### Prinsip DMA
```