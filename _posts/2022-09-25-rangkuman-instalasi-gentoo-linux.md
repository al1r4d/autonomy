---
title: Cara Cepat Install Gentoo Linux
layout: post
tag: linux
image: '/media/gentoo/gentoo.jpg'
---
Gentoo Linux adalah distribusi yang memungkinkan anda membangun semua program dari kode sumber saat pemasangan. Tentu berbeda dari umumnya yang serba *binary*. Selain itu, pemasangan yang dianggap susah membuat orang jarang menggunakan distro ini.

Saya akan menulis rangkuman instalasi Gentoo Linux metode MBR. Jika anda GPT/UEFI, maka bagian partisi dan grub harus diubah.

### Download ISO Gentoo
Download [ISO Gentoo Live](https://www.gentoo.org/downloads/) dahulu.

### Format Drive
Kita akan format dan mengatur partisi `/dev/sdX`, misalnya `/dev/sda`. Silahkan atur partisi sesuai keinginan. Disini saya hanya membuat satu partisi, yaitu root (/).
```bash
root # cfdisk /dev/sda
```
Atur filesystem yang digunakan, misalnya `ext4`. Saya sarankan `btrfs` saja.
```bash
root # mkfs.ext4 /dev/sda1
```

### Mount Partition
Kita *mount* partisi yang sudah dibuat.
```bash
root # mkdir -p /mnt/gentoo
root # mount /dev/sda1 /mnt/gentoo
```

### Stage 3
Ganti direktori ke folder *mount*.
```bash
root # cd /mnt/gentoo
```
Unduh berkas stage3 di [Gentoo Downloads](https://bouncer.gentoo.org/fetch/root/all/releases/amd64/autobuilds/20220924T034745Z/stage3-amd64-desktop-openrc-20220924T034745Z.tar.xz)
```bash
root # wget https://bouncer.gentoo.org/fetch/root/all/releases/amd64/autobuilds/20220924T034745Z/stage3-amd64-desktop-openrc-20220924T034745Z.tar.xz
```
Ekstrak file stage3.
```bash
root # tar -xf stage3*
```

### Chroot
Disini kita akan *chroot*.
```bash
root # cd /mnt/gentoo
root # mount --types proc /proc /mnt/gentoo/proc
root # mount --rbind /sys /mnt/gentoo/sys
root # mount --make-rslave /mnt/gentoo/sys
root # mount --rbind /dev /mnt/gentoo/dev
root # mount --make-rslave /mnt/gentoo/dev
root # mount --bind /run /mnt/gentoo/run
root # mount --make-slave /mnt/gentoo/run
root # cp /etc/resolv.conf etc && chroot . /bin/bash
root # source /etc/profile
```

### Update Repo Portage
Perbarui berkas - berkas dari repositori.
```bash
root # emerge-webrsync
```

### User Accounts
Ubah kata sandi akun *root*.
```bash
root # passwd
```
Kita akan membuat akun baru.
```bash
root # useradd -g users -G wheel,portage,audio,video,usb,cdrom -m username
root # passwd username
```

### System
#### Fstab
Atur file `/etc/fstab` fstab sesuai partisi.
```
/dev/sda1		/		ext4		noatime		0 1
```
#### Hostname
Atur hostname di file `/etc/conf.d/hostname`.
```bash
hostname="gentoo"
```
#### Timezone
Atur jam dan tanggal dengan perintah ini.
```bash
root # ln -sf /usr/share/zoneinfo/Asia/Jakarta /etc/localtime
```
#### Kernel
Unduh kernel yang sudah dikompilasi agar proses pemasangan lebih cepat.
```bash
root # emerge gentoo-kernel-bin
```

#### Firmware
Unduh firmware agar perangkat yang membutuhkan firmware di komputer anda bekerja
```bash
root # emerge linux-firmware
```

#### GRUB
Pasang program GRUB.
```bash
root # emerge --ask sys-boot/grub
```
Pasang GRUB sesuai hardisk kalian, misalnya di `/dev/sda`.
```bash
root # grub-install /dev/sda
```
Jangan lupa *generate* config agar bisa boot ke Gentoo Linux.
```bash
root # grub-mkconfig -o /boot/grub/grub.cfg
```

### Network Tools
Pasang alat - alat koneksi internet agar bisa internetan. Program `dhcpcd` sebagai **DHCP Client** dan `networkmanager` sebagai konfigurasi jaringan.
```bash
root # emerge net-misc/dhcpcd networkmanager
```

### Keluar
Keluar dari *chroot* dan *restart*.
```bash
root # exit
root # cd /mnt
root # umount -R gentoo
root # reboot 
```
