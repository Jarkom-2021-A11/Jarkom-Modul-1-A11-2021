# Jarkom-Modul-1-A11-2021

## Soal 1
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"

1. filter menggunakan `http.host == "ichimarumaru.tech"`
2. kemudian pilih salah satu paket, klik kanan, pilih `Follow > TCP Stream` dan akan terlihat bahwa server yang digunakan adalah `nginx/1.18.0 (ubuntu)` dengan port tujuannya adalah port 80.

![Jawaban Nomor 1](images/nomor1gambar1.jpg)

## Soal 2
Temukan paket dari web-web yang menggunakan basic authentication method!

1. filter menggunakan `http.authbasic`
2. kemudian pilih salah satu paket, lalu expand pada bagian `Hypertext Transfer Protocol`, dan dapat dilihat bahwa hostnya adalah `basic.ichimarumaru.tech`.

![Jawaban Nomor 2](images/nomor2gambar1.jpg)

## Soal 3
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

1. Pertama lakukan filter menggunakan `ip.dst == 167.172.77.139 && http.authorization` (ip dapat dilihat dari soal sebelumnya) sehingga tampil seluruh paket yang berasal dari basic.ichimarumaru.tech dan memiliki authorization.
2. Klik kanan pada salah satu paket kemudian expand pada bagian authorization.
3. Sehingga dapat dilihat bahwa usernamenya adalah `kuncimenujulautan` dan passwordnya adalah `tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN`

![Jawaban Nomor 3 Gambar 1](images/nomor3gambar1.jpg)
![Jawaban Nomor 3 Gambar 2](images/nomor3gambar2.jpg)

## Soal 4
Temukan paket mysql yang mengandung perintah query select

1. Lakukan filter dengan menggunakan `mysql.query && (mysql.query contains "select" ||  mysql.query contains "SELECT")`

![Jawaban Nomor 4](images/nomor4gambar1.jpg)

## Soal 5
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

1. Lakukan filter dengan menggunakan `mysql.query && mysql.query contains "INSERT"`
2. Terlihat bahwa usernamenya adalah `akakanomi` dan passwordnya adalah `pemisah4lautan`

![Jawaban Nomor 5 Gambar 1](images/nomor5gambar1.jpg)
![Jawaban Nomor 5 Gambar 2](images/nomor5gambar2.jpg)

## Soal 6
Cari username dan password ketika melakukan login ke FTP Server!

untuk mencari username filter display diisi
```ftp.request.command contains "USER"```
![Jawaban Nomor 6 Gambar 1](images/nomor6gambar1.png)
untuk mencari password filter display diisi
```ftp.request.command contains "PASS"```
![Jawaban Nomor 6 Gambar 2](images/nomor6gambar2.png)

didapat username dan password sebagai berikut:
```
username : secretuser
password : aku.pengen.pw.aja
```

## Soal 7
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

filter display diisi ```ftp-data contains "Real.pdf"```
![Jawaban Nomor 7 Gambar 1](images/nomor7gambar1.jpeg)
klik kanan pada ftp-data -> klik kanan -> follow -> TCP Stream
![Jawaban Nomor 7 Gambar 2](images/nomor7gambar2.png)
akan muncul huruf-huruf.
ubah show data as menjadi raw.
![Jawaban Nomor 7 Gambar 2](images/nomor7gambar2.jpeg)
lalu save as dengan ekstensi .pdf maka akan muncul seperti berikut.
![Jawaban Nomor 7 Gambar 3](images/nomor7gambar3.jpeg)


## Soal 8
Cari paket yang menunjukan pengambilan file dari FTP tersebut!

Solusi : Mencari pake yang menunjukan pengambilan sama halnya dengan men-*download* sehingga filter yang sesuai ialah ```ftp contains "RETR"```

![Jawaban Nomor 8](images/nomor8gambar1.jpg)

## Soal 9
Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!

Solusi : 
untuk mendapatkan zip →  ftp-data.command contains "secret.zip"
![Jawaban Nomor 9](images/nomor9gambar1.jpg)
lalu klik kanan → Follow → TCP Stream → Ubah data menjadi raw lalu save as “secret.zip”
![Jawaban Nomor 9](images/nomor9gambar2.jpg)
ketika dibuka akan meminta password seperti ini 
![Jawaban Nomor 9](images/nomor9gambar3.jpg)

## Soal 10
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

Untuk mendapatkan history.txt → ftp-data.command contains "history.txt"
![Jawaban Nomor 10](images/nomor10gambar1.jpg)
Jika dilihat pada bagian Line-based text terlihat bahwa password dibuat dari baris paling akhir dari isi bukanapaapa.txt
untuk mencari bukanapaapa.txt → ftp-data.command contains "bukanapaapa.txt"
![Jawaban Nomor 10](images/nomor10gambar2.jpg)
Jika dilihat pada bagian Line-based text terlihat bahwa string paling akhir adalah “d1b1langbukanapaapajugagapercaya” sehingga itu adalah password dari secret.zip
![Jawaban Nomor 10](images/nomor10gambar2.jpg)

## Soal 11
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 

Solusi: ```src port 80```

![Jawaban Nomor 11](images/nomor11gambar1.PNG)

## Soal 12
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

Solusi: ```port 21```

![Jawaban Nomor 12](images/nomor12gambar1.PNG)

## Soal 13
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

Solusi: ```dst port 443```

![Jawaban Nomor 13](images/nomor13gambar1.PNG)

## Soal 14
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

Solusi: ```dst host kemenag.go.id```

![Jawaban Nomor 14](images/nomor14gambar1.PNG)

## Soal 15
Filter sehingga wireshark hanya mhanya mengambil paket yang berasal dari ip kalian!

Solusi:
Dengan menggunakan command prompt dan command ```ipconfig```. Dari situ, Ditemukan bahwa ip yang digunakan adalah ```192.168.0.101```. 
Kemudian untuk mengambil paket yang berasal dari ip, menggunakan capture filter: ```ip src 192.168.0.101``` 

![Jawaban Nomor 15](images/nomor15gambar1.PNG)
