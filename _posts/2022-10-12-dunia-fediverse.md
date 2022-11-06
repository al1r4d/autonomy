---
title: Dunia Fediverse
layout: post
tag: teknologi
image: '/media/fediverse/fediverse.jpg'
---
Media sosial bukan hanya tentang Facebook, Instagram, Twitter, Line, Whatsapp, dan mainstream lainnya. Di luar sana, telah hidup media sosial underground yang belum orang umum tahu.

Semenjak pemberitaan Elon Musk ingin membeli Twitter, nama **Mastodon** kerap kali disebut sebagai alternatif, bagi mereka yang membenci Elon.

Apa itu **Mastodon**? Ada apa dengan **Activity Pub** yang dijargonkan sebagai media sosial masa depan?
## Protokol ActivityPub
![](/media/fediverse/activitypub.png)

ActivityPub adalah protokol jejaring sosial terbuka dan terdesentralisasi berbasis protokol ActivityPump Pump.io. Protokol ini enyediakan API klien/server untuk membuat, memperbarui, dan menghapus konten, serta API server-ke-server untuk mengirimkan pemberitahuan dan konten.


## Mastodon, Pleroma, dan sebagainya
Ada banyak proyek yang mengimplementasikan protokol ActivityPub, media sosial Fediverse pun salah satunya.

### Mastodon
![](/media/fediverse/mastodon.png)

Mastodon adalah media sosial sosial open-source gratis berbasis ActivityPub di mana pengguna dapat mengikuti teman dan menemukan yang baru. Di Mastodon, pengguna dapat mempublikasikan apa pun yang mereka inginkan: tautan, gambar, teks, video. 

Semua server Mastodon dapat dioperasikan sebagai jaringan gabungan. Pengguna di satu server dapat berkomunikasi dengan lancar dengan pengguna dari server lain, termasuk non-Mastodon yang mengimplementasikan ActivityPub.

Saya menggunakan Mastodon di instansi [mstdn.starnix.network](https://mstdn.starnix.network/@al1r4d). Temui saya di sana!

### Pleroma
![](/media/fediverse/pleroma.png)

Pleroma adalah media sosial microblogging yang dapat tersambung server lain yang mendukung ActivityPub. Artinya, Anda dapat meng-host server untuk diri sendiri atau teman Anda, etapi tetap bertukar pesan dengan orang-orang di server yang lebih besar. Pleroma tersambung dengan semua server yang mengimplementasikan ActivityPub, seperti Friendica, GNU Social, Hubzilla, Mastodon, Misskey, Peertube, dan Pixelfed.

Pleroma ditulis dengan Elixir dan menggunakan PostgresSQL untuk penyimpanan data. Ini cukup efisien untuk dijalankan pada perangkat berdaya rendah seperti Raspberry Pi.

## Haruskah Anda Mencobanya?
Dunia Fediverse sangat mengagumkan. Anda bisa melihat bagaimana tersambung dengan pengguna lain, meskipun beda server. Saya sudah mencobanya, anda kapan?
