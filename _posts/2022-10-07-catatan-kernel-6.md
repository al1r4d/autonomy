---
title: Catatan Kernel Linux 6.0
layout: post
tag: linux
image: '/media/linux/kernel.png'
---
Tanggal 2 Oktober 2022 Kernel Linux 6.0 telah dirilis. Kernel ini membawa perbaikan untuk *Retbleed vulnerability*, peningkatan kerja virtualisasi, dukungan terbaru untuk GPU, dan lain - lain.
## Motivasi
Setiap kernel baru muncul, saya akan memasangnya dan *tweaking* agar menghasilkan performa yang terbaik. Saya suka dengan oprek - oprek dan meningkatkan kinerja.
## Yang Saya Lakukan
Saya melakukan penambalan Kernel Linux.
### Scheduler Linux
Kali ini saya berpindah ke [TT CPU Scheduler](https://github.com/hamadmarri/TT-CPU-Scheduler) setelah sebelumnya menggunakan [BMQ CPU Scheduler](https://www.phoronix.com/news/Linux-BitMap-Queue-BMQ). Mengapa pindah? Saya tertarik mencoba setelah diberitahu kalau TT bagus untuk *Latency* dan tetap responsif ketika *workload* berat. Setelah saya memasang TT dan melakukan kompilasi kernel, saya merasa temperatur lebih dingin daripada BMQ. Waktu kompilasi pun beda 1 - 5 menit dibanding BMQ. 

Jika anda pengguna Real-time kernel, TT bisa digunakan secara bersamaan. Tertarik mencoba?
### Clear Linux
Clear Linux adalah distro buatan Intel yang berfokus pada optimisasi bagi pengguna CPU Intel. Saya menggunakan patch **Clear Linux** karena terdorong kelebihannya.
### Google MG LRU
Multi-Gen LRU atau MGLRU membantu dan menambah performa jika anda memiliki RAM rendah.
### LRNG
LRNG adalah *fast random generator* jika dibandingkan *upstream*.
### Clang Full LTO
Saya membaca artikel Phoronix dan tertulis bahwa perfoma kernel yang dibangun menggunakan Clang Full LTO lebih baik daripada GCC.
### Maple Tree
Untuk efisiensi penggunaan *processor cache*.
### -CK Patchset
Agar latency tidak tinggi.
### High HZ
Entah mengapa semakin tinggi HZ, maka makin responsif desktop saya. Maka dari itu saya memilih 1666 HZ.
### -O3
-O3 adalah level optimasi tertinggi, tetapi harus diwaspadai karena beberapa orang tidak menyarankan ini. Alasannya karena takut aplikasinya tidak berjalan.
### -march="cpukamu"
Saya menggunakan Intel seri Haswell. Jadi saya menetapkan `-march=haswell`.
### BBR v2
Untuk ningkatin kecepatan jaringan di Linux.
