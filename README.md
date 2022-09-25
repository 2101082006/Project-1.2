# Membuat Layanan Mikroservice Sederhana
## Download Maven Projek Menggunakan Spring Web
### Step 1 :
Buat Projek Maven menggunakan Spring Initialir. Untuk linknya : [Klik Disini!](https://start.spring.io/).
### Step 2 :
Pilihlah versi Spring Boot yang cocok. Disarankan untuk memilih versi  _2.6.12._
### Step 3 :
Beri nama _file/group_. Dalam kasus ini, saya membuat nama filenya dengan nama sendiri _com.ibra_.
### Step 4 :
Untuk bagian _Artifact_ nya diubah menjadi _latihan-service_.
### Step 5 :
Pilihlah Java Version sesuai dengan yang digunakan pada perangkat 
(disini saya menggunakan jdk versi 17).
### Step 6 :
Klik pada bagian _Dependencies_, lalu cari keyword *Spring Web*, lalu Enter. ![Screenshot (562)](https://user-images.githubusercontent.com/113502572/192135252-143e48b3-9fd3-4076-b06a-d78e8c5c4345.png)
### Step 7 :
Klik _Generate the project_ pada bagian bawah layar. File berupa zip akan terdownload secara otomatis.
### Step 8 :
Ekstrak file yang sudah didownload tadi di dalam hardisk.
### Step 9 :
Buka *Apache Netbeans* lalu _Open Project_ yang telah diekstrak tadi.
### Step 10 :
Klik kanan di project *latihan-service*, lalu pilih _Build with Dependencies_. Tunggu proses Build sukses hingga ada tulisan **BUILD SUCCESS**.

# Projek Spring Boot Baru
## Step 1 : Memulai Projek Spring Boot
Dalam spring initializr terdapat beberapa inputan yang harus diisi

* Project: build tool yang akan digunakan untuk mengembangkan project, bisa dipilih jenis project menggunakan maven atau gradle
* Language: bahasa pemrograman yang akan digunakan, bisa dipilih bahasa pemrograman Java, Kotlin atau Groovy
* Spring Boot: versi spring boot yang akan digunakan
* Project Metadata: merupakan fasilitas untuk penamaan paket project yang akan dikembangkan
* Group: digunakan untuk identifikasi unik yang universal untuk sebuah proyek. Meskipun ini sering kali hanya nama proyek misalnya accounting, akan sangat membantu jika menggunakan nama paket yang sepenuhnya memenuhi syarat untuk membedakannya dari proyek lain dengan nama serupa 8 misalnya com.bittama.accounting.
* Artifact: adalah nama paket jar atau war tanpa versi. Nama dapat dipilih apa pun yang dinginkan dengan huruf kecil dan tidak ada simbol yang aneh. Dari contoh gambar di atas maka nama yang dihasilkan adalah accounting-<versi>.jar
* Package Name: adalah struktur nama paket dalam project
* Packaging: output dari project yang dikembangkan bisa berupa jar atau war
* Java: versi java yang digunakan
## Step 2 : Menambahkan Kode
Kita dapat memulai menulis kode dengan menggunakan editor apa saja. Kali ini kita menggunakan NetBeans IDE. Sebenarnya dalam NetBeans IDE sudah terdapat plugins untuk memulai Spring Boot, silakan dicoba sendiri.

Oke, langsung saja kita buka NetBeans IDE kemudian open project, pilih dari file yang telah diekstrak tadi. Berikut adalah tampilan dari hasil generate jika di buka dengan NetBeans IDE.
![Screenshot (561)](https://user-images.githubusercontent.com/113502572/192135243-ac396072-cc02-4ed1-998c-76b0b3607b9c.png)
Buat file Java Class dengan nama HelloController.java dan tulis kode seperti di bawah ini
 

	 package com.ibra.latihan2.service;

   	 import org.springframework.boot.SpringApplication;
  	 import org.springframework.boot.autoconfigure.SpringBootApplication;
  	 import org.springframework.web.bind.annotation.GetMapping;
 	 import org.springframework.web.bind.annotation.RequestParam;
	 import org.springframework.web.bind.annotation.RestController;

  	 @SpringBootApplication
  	 @RestController
  	 public class LatihanServiceApplication {

	 public static void main(String[] args) {
		SpringApplication.run(LatihanServiceApplication.class, args);
	 }
        
         @GetMapping("/hello")
         public String hello(@RequestParam(value = "name", defaultValue = "Latihan2") String name) {
         return String.format("Hello %s!", name);
           }
         }
## Step 3 : Run!
Jalankan dengan mengklik menu Run pilih Run Project atau tekan tombol F6 pada keyboard. Buka browser lalu masukkan url http://localhost:8080 maka akan tampil seperti gambar di bawah ini.
![gambar](https://andikhermawan.files.wordpress.com/2021/07/04-1.png)
