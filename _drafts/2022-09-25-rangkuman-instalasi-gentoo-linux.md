---
title: Cara Cepat Install Gentoo Linux
layout: post
tag: teknologi
image: '/media/gentoo/gentoo.jpg'
---
Gentoo Linux adalah distribusi yang memungkinkan anda membangun semua program dari kode sumber saat pemasangan. Tentu berbeda dari umumnya yang serba *binary*. Selain itu, pemasangan yang dianggap susah membuat orang jarang menggunakan distro ini.
### Format Drive

```bash
root # cfdisk /dev/sda
```

```bash
root # mkfs.ext4 /dev/sda1
```

### Mount Partition

```bash
root # mkdir -p /mnt/gentoo
root # mount /dev/sda1 /mnt/gentoo
```

### Stage 3
```bash
root # cd /mnt/gentoo
```

```bash
root # wget https://bouncer.gentoo.org/fetch/root/all/releases/amd64/autobuilds/20220924T034745Z/stage3-amd64-desktop-openrc-20220924T034745Z.tar.xz
```

```bash
root # tar -xf stage3*
```

### Chroot
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
```bash
root # emerge-webrsync
```

### User Accounts
```bash
root # passwd
```

```bash
root # useradd -g users -G wheel,portage,audio,video,usb,cdrom -m username
root # passwd username
```

### System
#### /etc/fstab
```
/dev/sda3		/		ext4		noatime		0 1
```
#### Hostname
```bash
dns_domain_lo="mynetwork.net"
```
#### Timezone
```bash
root # ln -sf /usr/share/zoneinfo/Europe/Helsinki /etc/localtime
```

#### Kernel
```bash
root # emerge gentoo-kernel-bin
```

#### Firmware
```bash
root # emerge linux-firmware
```

#### GRUB
```bash
root # emerge --ask sys-boot/grub
```
```bash
root # grub-install /dev/sda
root # grub-mkconfig -o /boot/grub/grub.cfg
```

### Network Tools
```bash
root # emerge net-misc/dhcpcd networkmanager
```

### Keluar
```bash
root # exit
root # cd /mnt
root # umount -R gentoo
root # reboot 
```
