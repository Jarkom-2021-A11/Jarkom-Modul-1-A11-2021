# Jarkom-Modul-1-A11-2021

## Soal 1
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"

1. filter menggunakan `http.host == "ichimarumaru.tech"`
2. kemudian pilih salah satu paket, klik kanan, pilih `Follow > TCP Stream` dan akan terlihat bahwa server yang digunakan adalah `nginx/1.18.0 (ubuntu)`

![Jawaban Nomor 1](images/nomor1gambar1.jpg)

## Soal 2
Temukan paket dari web-web yang menggunakan basic authentication method!

## Soal 3
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

## Soal 4
Temukan paket mysql yang mengandung perintah query select

## Soal 5
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!



## Soal 11
11.	Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 

Solusi: ```src port 80```

## Soal 12
11.	12.	Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

Solusi: ```port 21```

## Soal 13
11.	Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

Solusi: ```dst port 443```

## Soal 14
11.	Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

Solusi: ```dst host kemenag.go.id```


### Soal 15
11.	Filter sehingga wireshark hanya mhanya mengambil paket yang berasal dari ip kalian!

Solusi:
Dengan menggunakan command prompt dan command ```ipconfig```. Dari situ, Ditemukan bahwa ip yang digunakan adalah ```192.168.0.101```. 
Kemudian untuk mengambil paket yang berasal dari ip, menggunakan capture filter: ```ip src 192.168.0.101``` 

![Jawaban Nomor 15](images/nomor15gambar1.jpg)