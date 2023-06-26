---
title: Membuat virtual pc dengan Xen
layout: post
---

## Xen

Dengan xen kita dapat menjadikan pc kita terinstall didalamnya beberapa mesin virtualisasi. openSUSE adalah salah satu distro yang sudah mendukung penggunaan xen dengan mudah, kita hanya tinggal install xen tersebut menggunakan paket manager opensuse ..zypper.

Berikut ini urutan langkah yang saya sudah dilakukan, menggunakan openSUSE Leap 15.4.
1. Kita update terlebih dahulu os kita menggunakan  <br>
$sudo zypper update <br>
2. Kemudian kita install xen tersebut <br>
$sudo zypper in -t pattern xen <br>


