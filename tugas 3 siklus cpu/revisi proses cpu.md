### NAMA : Sapta Adzani Purnama
### NRP : 3123521014
### Prodi : D3 Teknik Informatika-LA
### KELAS : A

## Siklus CPU
![alt text](<Screenshot (398).png>)
#### KETERANGAN : pada proses cpu berawal dari fetch(pengambilan alamat) kemudian decode (membaca nilai pada alamat yang diambil) selanjutnya execute (mengeksekusi perintah dari nilai yang diambil) proses itu berjalan dengan looping jadi setelah dieksekusi maka akan kembali mengambil alamat selanjutnya.

## PROSES 1
![alt text](<Screenshot (397).png>)
#### KETERANGAN : fetch alamat 0 kemudian membaca nilai dari alamat 0 yaitu load 6 kemudian dieksekusi pada alamat 6 memiliki value 1 dan dimasukkan kedalam accumulator.

## PROSES 2
![alt text](<Screenshot (399).png>)
#### KETERANGAN : setelah looping kembali lagi fetch menambil alamat dalam memori yaitu 1 kemudian alamat 1 dilakukan pengkodean membaca perintah ADD 7 selanjutnya dilakukan eksekusi perintah pada alamat 7 nilai 1 ditambahkan ke accumulator sehingga yang awalnya 1 ditambah value dari address 7 menjadi 2.

## PROSES 3
![alt text](<Screenshot (400).png>)
#### KETERANGAN : kembali lagi looping ke proses fetch mengambil address 2 kemudian decode membaca value address 2 yang memiliki value store 6 yang kemudian dieksekusi menjadi perintah menyisipkan nilai accumulator ke addres 6 sehingga addres 6 yang awalnya memiliki value 1 berubah menjadi 2.

## PROSES 4
![alt text](<Screenshot (401).png>)
#### KETERANGAN : looping lagi ke proses fetch mengambil nilai 3 kemudian dilakukan decode membaca perintah pada addres 3 yaitu jump 1 kemudian dieksekusi value jump yang berarti melompat ke addres 1 sehingga addres 0 tidak lagi diambil nilainya.proses ini menjadi yang terakhir dimana proses kemudian kembali lagi ke value add 7 seperti pada proses 2 dan seterusnya.

## kesimpulan
### pada proses cpu yang berjalan berawal dari fetch-decode-execute terjadi proses looping diawal cpu berjalan terjadi proses load mengisi accumulator dengan value dari load tergantuk addres yang di sebutkan load kemudian terjadi proses add dimana pada value yang di add akan ditambahkan ke accumulator setelah itu store itu menyisipkan nilai accumulator ke value tertentu sesuai dengan perintah pada store yang terakhir jump yaitu melakukan skip proses load dan langsung menjalankan add seperti sebelumnya proses nya akan selalu terjadi looping.

