---
title: Mengenal XMPP
tag : teknologi
layout: post
---
Setiap kali saya mengatakan bahwa XMPP adalah solusi _Instant Messaging_ terbaik yang tersedia, seseorang berpendapat bahwa itu "terlalu sulit" atau "membingungkan" untuk digunakan oleh pengguna yang kurang mahir.

Saya mencoba mencari panduan pengenalan untuk menggunakan XMPP yang dapat saya kirimkan kepada orang-orang yang bertanya kepada saya, tetapi saya hanya menemukan panduan tentang pengaturan server XMPP atau beberapa panduan yang dijelaskan dengan buruk, jadi saya memutuskan untuk menulis panduan sendiri sehingga rata-rata orang dapat menggunakan protokol XMPP tanpa komplikasi.

## Tapi, apa itu XMPP?

XMPP adalah standar untuk pesan instan. Sebenarnya, layanan IM propietary seperti Whatsapp berbasis pada protokol XMPP. Protokol ini dirancang untuk digunakan secara terdistribusi, di mana terdapat berbagai penyedia dan Anda dapat menggunakan salah satu yang paling Anda sukai. Hampir seperti email, Anda dapat mengobrol dengan orang yang menggunakan penyedia yang berbeda: Joe dapat mengirim email dari joe@gmail.com ke ed@outlook.com bahkan jika penyedia Joe (gmail) tidak sama dengan milik Ed (Outlook). XMPP bekerja dengan cara yang sama.

Sifat jaringan XMPP yang terdistribusi ini memiliki banyak keuntungan. Misalnya, tidak ada satu titik kegagalan, jadi kebalikan dari apa yang terjadi dengan Whatsapp, jika server mati, sebagian besar jaringan akan tetap berjalan dan itu hanya akan mempengaruhi sebagian kecil. para pengguna. 

Ini juga memberi anda kebebasan untuk memilih penyedia yang anda inginkan dan yang anda percayai, anda tidak dipaksa untuk mempercayai perusahaan yang teduh (misalnya Facebook) untuk menyimpan percakapan kami. Anda memiliki kemungkinan menjadi penyedia Anda sendiri!

## Jadi, bagaimana saya mulai menggunakan XMPP?

Nah, semudah membuat akun di penyedia preferensi Anda.

### Membuat akun XMPP

Sama seperti email, dengan XMPP, kita dapat memilih di antara beberapa penyedia XMPP untuk membuat akun kita. Rekomendasi pribadi saya adalah Nixnet dan Disroot. 

Membuat akun semudah pergi ke penyedia pilihan Anda dan mengisi formulir web. Di XMPP ada fitur bagus dan Anda dapat mendaftar dari klien Anda! Tetapi Anda mungkin lebih terbiasa dengan formulir web, jadi gunakan itu jika Anda mau. Pilih nama pengguna Anda dan kata sandi yang kuat. Mungkin Anda diminta untuk menyelesaikan captcha. Itu saja, sekarang akun XMPP Anda seharusnya sudah siap. Mudah, bukan?

Untuk masuk ke klien Anda dan membagikan pengguna XMPP Anda sehingga orang lain dapat menghubungi Anda, itu seperti email: user@domain.com. Misalnya, namasaya@contoh.org atau namaanda@xmpp.domain.com.

### Masuk ke klien XMPP Anda

Sekarang Anda perlu mengunduh klien XMPP. Saya rasa sebagian besar dari Anda ingin menggunakan XMPP di ponsel Anda, tetapi Anda juga dapat menggunakannya di desktop. Jadi unduh klien tergantung pada OS Anda:

- Untuk Android, Conversation adalah bagus. Anda dapat mengunduhnya dari F-Droid (_free software_, disarankan) atau dari Play Store (3,49 euro, tidak disarankan!).
- Untuk iOS, Siskin IM adalah opsi yang populer. Anda dapat menemukannya di Apple Store.
- Untuk desktop, rekomendasi saya adalah Gajim untuk GNU/Linux dan BSD. Untuk Windows dan macOS, meskipun Anda seharusnya tidak menggunakannya, rekomendasi saya adalah Gajim untuk Windows dan Beagle IM untuk macOS.

Setelah Anda memiliki klien, yang harus Anda lakukan adalah masuk dengan akun yang Anda buat sebelumnya. Ingat bahwa formatnya seperti email, user@domain.org.

### Enkripsi

Enkripsi sangat penting. XMPP mendukung beberapa metode enkripsi. Tapi kami akan fokus pada yang paling mudah: OMEMO.

Mengaktifkan OMEMO sangat sederhana tetapi tergantung pada klien yang Anda gunakan. Norma umum yang baik adalah mencari ikon kunci dan mengkliknya, itu akan memberi Anda opsi untuk mengaktifkan OMEMO. Pada beberapa klien lain mungkin perlu menginstal plugin, misalnya di Gajim. Saya akan menjelaskan caranya.

#### OMEMO di Gajim

Di bilah utama di bagian atas jendela, buka Gajim > Plugin. Daftar plugin yang tersedia akan muncul. Cari plugin bernama “OMEMO”, pilih dan klik tombol unduh di bawah. Ini akan meminta Anda untuk me-restart Gajim, restart. Setelah itu, ikon kunci akan muncul di setiap obrolan. Klik dan ingat untuk memilih OMEMO. Itu dia. Semuanya harus bekerja sekarang.

## Kesimpulan

Saya harap Anda menemukan panduan ini bermanfaat. Jika Anda memiliki pertanyaan, Anda selalu dapat menulis email kepada saya dan saya akan melakukan yang terbaik untuk membantu Anda.

Saya ingin beberapa saran untuk menyempurnakan panduan ini. Niat saya adalah membuatnya sejelas mungkin bagi pengguna baru, jadi umpan balik apa pun dihargai.

