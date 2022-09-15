---
title: Menyusun Kernel Linux Dengan Clang LTO
layout: post
tag: teknologi
image: '/media/clang/clang.jpg'
---
## Apa Itu Clang dan LTO?
Clang adalah program _compiler_ bahasa C yang mengutamakan kecepatan penyusunan dan penggunaan memori yang rendah. LLVM Developer Group adalah developer di balik program ini.

LTO atau _Link Time Optimization_ adalah cara untuk mengoptimasi suatu program. Lebih lanjut bisa dibaca di artikel [LLVM Link Time Optimization: Design and Implementation](https://llvm.org/docs/LinkTimeOptimization.html).
## Memasang Clang
Pastikan program Clang telah terinstall. Jika belum, unduhlah terlebih dahulu. Cara di bawah bisa anda lakukan jika berada di distribusi Debian dan turunannya.
```bash
root # apt install clang
```
## Mengaktifkan LTO pada Kernel Linux
Menggunakan _Link Time Optimization_ sewaktu membangun kernel Linux sangatlah mudah. Nyalakan skrip LTO dengan perintah di bawah.
```bash
root # cd /usr/src/linux
root /usr/src/linux # scripts/config -e LTO_CLANG
```
Setelah itu, jalankan `menuconfig`. Kemudian buka menu `General Architecture` dan aktifkan `Strong Stack Protector`. Pilihlah LTO mana yang anda suka.
```bash
root /usr/src/linux # make CC=clang LLVM=1 menuconfig
```

![](/media/clang/lto.png)

Jika dirasa cukup, kompilasi dilakukan dengan cara
```bash
root /usr/src/linux # make CC=clang LLVM=1 -j4 -l8
root /usr/src/linux # make CC=clang LLVM=1 modules_install
root /usr/src/linux # make CC=clang LLVM=1 install
```

Selesai.
