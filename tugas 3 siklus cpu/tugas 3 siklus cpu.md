### NAMA : Sapta Adzani Purnama
### NRP : 3123521014
### Prodi : D3 Teknik Informatika-LA
### KELAS : A

### 3.Jalankan VM Debian anda, lalu lakukan clone https://github.com/ferryastika/flops-iops. Compile dan eksekusi sesuai petunjuk. Sesuiakan jumlah thread dengan jumlah CPU yang ada di VM Debianmu. Catat hasilnya dan jelaskan arti dari hasil ekskusi. Lakukan sebanyak 5 kali. Bandingkan hasilnya anatar temanmu. Buat Plot perbandinnga hasil untuk masing-masing PC di tiap kelompokmu. Analisa hasil percobaan tadi dan beri kesimpulan tentang IOPS dan FLOPS.
![alt text](<Screenshot (285).png>)
## keterangan :

**$ git clone** https://github.com/ferryastika/flops-iops: Ini akan mengkloning repositori flops-iops dari GitHub ke direktori lokal.

**$ cd flops-iops**: Ini akan mengubah direktori kerja ke dalam direktori flops-iops yang baru saja diberikan perintah clone.

**$ make**: Ini adalah perintah untuk mengkompilasi program. make akan membaca file Makefile di direktori tersebut dan menjalankan instruksi yang didefinisikan di dalamnya untuk menghasilkan program yang dapat dieksekusi.

**$ make clean**: Ini adalah perintah yang digunakan setelah kompilasi untuk membersihkan file-file sementara atau hasil kompilasi yang tidak diperlukan.

**$sudo make install**: Perintah ini akan menjalankan target install yang didefinisikan dalam file Makefile. Target ini digunakan untuk menginstal program atau paket yang telah dikompilasi ke dalam sistem.

**$sudo make uninstall**: Perintah ini digunakan untuk menghapus program atau paket yang telah diinstal menggunakan perintah make install.

# flops
![alt text](<Screenshot (287).png>)
## keterangan :
## percobaan 1 : 
#### Tr 1: 4215508154 
#### Tr 2: 4191144646 
#### FLOPS 8406652800
#### Maximum CPU Throughput: 8.406653 Gigaflops 
#### Maximum Single Core Throughput: 4.215508Gigaflops.

## percobaan 2 :
#### Tr 1: 4199386802 
#### Tr 2: 4216837742 
#### FLOPS 8416224544
#### Maximum CPU Throughput:  8.416224 Gigaflops 
#### Maximum Single Core Throughput: 4.216837Gigaflops.

## percobaan 3 :
#### Tr 1: 4227743858  
#### Tr 2: 4264721708  
#### FLOPS 8492465566
#### Maximum CPU Throughput:   8.492466 Gigaflops 
#### Maximum Single Core Throughput: 4.264722Gigaflops.

## percobaan 4 :
#### Tr 1: 4166240416  
#### Tr 2: 4191283252  
#### FLOPS 8357523668
#### Maximum CPU Throughput:   8.357524 Gigaflops 
#### Maximum Single Core Throughput: 4.191283Gigaflops.

## percobaan 5  :
#### Tr 1: 3812510260  
#### Tr 2: 3829059130 
#### FLOPS 7641569390
#### Maximum CPU Throughput:   8.415424 Gigaflops 
#### Maximum Single Core Throughput: 4.1912345Gigaflops.

# iops
![alt text](<Screenshot (288).png>)
## keterangan :
## percobaan 1 : 
#### Tr 1: 4446005148
#### Tr 2: 4463009252 
#### IOPS 8909014400
#### Maximum CPU Throughput: 8.909014  Gigaiops 
#### Maximum Single Core Throughput: 4.463009Gigaiops.

## percobaan 2 : 
#### Tr 1: 4304510574 
#### Tr 2: 4341530804 
#### IOPS  8646041378
#### Maximum CPU Throughput: 8.646042 Gigaiops 
#### Maximum Single Core Throughput:  4.341531Gigaiops.

## percobaan 3 : 
#### Tr 1: 4374475560 
#### Tr 2:4356605188 
#### IOPS  8731080748
#### Maximum CPU Throughput: 8.731081  Gigaiops 
#### Maximum Single Core Throughput:  4.374476Gigaiops.

## percobaan 4 : 
#### Tr 1: 4326912044 
#### Tr 2:4314971700  
#### IOPS  8641883744
#### Maximum CPU Throughput: 8.641884  Gigaiops 
#### Maximum Single Core Throughput: 4.32692Gigaiops.

## percobaan 5 : 
#### Tr 1: 4215383796 
#### Tr 2:4296992830   
#### IOPS  8512376626
#### Maximum CPU Throughput:  8.512377 Gigaiops 
#### Maximum Single Core Throughput: 4.296993Gigaiops.

# kesimpulan flops dan iops
### Floating Point Operations Per Second (FLOPS) dan Integer Operations Per Second (IOPS) adalah metrik yang digunakan untuk mengukur kinerja sistem komputasi. FLOPS mengukur jumlah operasi floating-point yang dapat dilakukan oleh sistem dalam satu detik, sementara IOPS mengukur jumlah operasi integer yang dapat dilakukan dalam satu detik. Kedua metrik ini penting dalam mengevaluasi kinerja sistem untuk berbagai jenis aplikasi. FLOPS sering digunakan dalam komputasi ilmiah, simulasi numerik, dan pemrosesan gambar, sementara IOPS lebih relevan untuk aplikasi yang memerlukan operasi integer, seperti database dan pemrosesan data. Secara umum, semakin tinggi nilai FLOPS atau IOPS, semakin cepat dan efisien sistem dalam melakukan operasi yang sesuai, yang dapat mengindikasikan kinerja yang lebih baik dalam menangani berbagai tugas komputasi.

### 4.Apabila Debian VM mu masih belum terdapat packeage gcc, make dan git, lakukan instalasi dan catat setiap langkahnya!
![alt text](<Screenshot (289).png>)
## keterangan :

Perintah **$ su** digunakan untuk mengganti pengguna menjadi superuser atau root.

**apt install gcc** adalah perintah yang digunakan untuk menginstal compiler GNU Compiler Collection (GCC) melalui sistem manajemen paket Advanced Package Tool (APT). GCC adalah koleksi compiler yang diperlukan untuk mengkompilasi program-program dalam bahasa C, C++, dan beberapa bahasa lainnya di lingkungan Linux.

**apt install make** menginstal perangkat lunak Make, yang merupakan utilitas yang digunakan untuk mengotomatisasi proses kompilasi program. Make digunakan untuk mengelola dependensi dan mengkompilasi program dari sumber kode.

**apt install git** menginstal sistem kontrol versi Git. Git digunakan untuk mengelola dan mengontrol versi dari kode sumber perangkat lunak. Ini memungkinkan kolaborasi antar pengembang, pelacakan perubahan kode, dan manajemen proyek yang efisien.



