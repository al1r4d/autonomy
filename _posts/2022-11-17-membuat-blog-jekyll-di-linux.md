---
title: Membuat Blog Jekyll di Linux
tag: linux
layout: post
image: '/media/jekyll/jekyll.jpg'
---
Blog bukan harus tentang Wordpress, Medium, atau Wordpress. Ada Jekyll yang bisa digunakan, contohnya blog ini. Mari kita kupas lebih dalam tentangnya.

## Apa Itu Jekyll
Singkatnya Jekyll adalah static website generator yang dapat mengubah file markdown menjadi html. Dibangun menggunakan Ruby dan bersifat _free open source software_ dengan lisensi MIT.

Yang saya sukai dari Jekyll adalah kesederhanaan. Tidak ada database yang bikin penuh. Anda tidak butuh spesifikasi tinggi untuk memasang.

Di bawah ini adalah gambaran letak folder yang digunakan Jekyll. Lebih jelasnya bisa baca tutorial step by step di website [Jekyll](https://jekyllrb.com/docs/step-by-step/01-setup/).
```
├── _includes
├── _layouts
├── _pages
├── _post
├── _site
``` 
    
## Memasang Jekyll di Linux
Posisi saya ada di Devuan GNU/Linux. Untuk memasang Jekyll, saya menggunakan cara di bawah.

Mengapa tidak langsung dari repositori? Entahlah, kadang saya dapat error kalau install Jekyll dari repositori distro. Sehingga saya mengunduh langsung lewat `gem`.
```
$ sudo apt -y install ruby ruby-dev
$ gem install bundler
$ gem install jekyll
```

## Membuat Blog Jekyll
Kalau sudah pasang Jekyll, saatnya menyalakannya. Anda dapat menggunakan perintah di bawah.
```
$ jekyll serve
```

Jika anda belum punya blog, anda bisa _clone_ tema bebas. Misalnya dari Github.
```
$ git clone https://github.com/pages-themes/minimal
$ cd minimal
$ jekyll serve
```
## Github Pages & Jekyll
![](/media/jekyll/github-pages.png)
Saya ada informasi menarik. Anda bisa mengonlinekan blog Jekyll secara gratis di Github. Yang anda butuhkan hanyalah akun Github saja.
1. Push folder blog Jekyll anda.
2. Atur `branch` di menu Pages.
3. Jangan lupa pointing domain anda ke Github Pages. [Tutorial ada disini](https://init.web.id/custom-apex-domain-untuk-github-pages/)