---
title: Mounting folder remote pc
layout: post
---

Untuk mengakses folder diremote pc yang berbasis os windows dari linux, ada beberapa langkah yang perlu dilakukan, dan ini adalah yang biasa saya kerjakan :)

1. Periksa terlebih dulu folder yang mau kita akses diremote pc dengan perintah:

   > $sudo smbclient -L //ipremote pc/ -U administrator

   > masukkan password administrator, kemudian

   > $sudo mount -t cifs //ipremote pc/sharing-folder/ /mnt/hd/ --verbose -o user=administrator

   > masukkan kembali password administrator yang diminta..

2. Maka folder diremote pc dapat diakses pada folder /mnt/hd/ dikomputer lokal milik kita..<br>
Sekian, semoga bermanfaat ...barakallah fiikum.

