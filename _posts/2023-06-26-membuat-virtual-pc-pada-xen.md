---
title: Membuat virtual pc dengan Xen
layout: post
---

## Xen

Dengan xen kita dapat menjadikan pc kita .. terinstall didalamnya beberapa mesin virtualisasi. openSUSE adalah salah satu distro yang sudah mendukung penggunaan xen dengan mudah, terlebih dahulu kita install xen tersebut menggunakan paket manager yang dimiliki opensuse yaitu zypper.

Berikut ini urutan langkah yang saya lakukan untuk menginstall paket xen, menggunakan openSUSE Leap 15.4.

1. Kita update terlebih dahulu os kita  
   $sudo zypper update  
2. Kemudian kita install xen tersebut  
   $sudo zypper in -t pattern xen

Setelah paket xen beserta tools pendukungnya terinstall, kita tinggal buat virtual mesin yang kita mau, bisa menggunakan gui atau melalui terminal mode.


