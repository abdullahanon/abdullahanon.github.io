---
title: Memperluas Kapasitas Hardisk LVM
layout: post
---

Sistem operasi linux slackware mendukung penggunaan lvm dalam tipe format harddisk nya, yang memudahkan kita mengatur kapasitas harddisk tersebut sesuai keinginan kita.

Berikut ini langkah yang saya lakukan untuk memperluas kapasitas harddisk pada laptop yang saya gunakan.
1. Kita cek layout harddisk menggunakan cfdisk dilanjutkan membuat partisi dengannya dan type partisi kita atur menjadi LVM
2. Dilanjutkan pembuatan partisi dengan perintah pvcreate /dev/sda4.
3. Bisa kita cek partisi yang baru saja kita buat dengan pvs.
4. Dilanjutkan dengan memperluas volume group partisi yang sudah ada menggunakan vgextend vg1 /dev/sda4, dimana vg1 adalah nama volume group yang kita miliki.
5. Bisa kita cek hasil pengembangan volume tersebut dengan menggunakan vgs.
6. Setelah volume group bisa kita perluas saatnya kita memperluas pula logic volume tersebut dengan perintah lvextend -l 100%FREE /dev/vg1/home.
7. Ditutup dengan perintah resize2fs /dev/vg1/home.
8. Selesai :)


