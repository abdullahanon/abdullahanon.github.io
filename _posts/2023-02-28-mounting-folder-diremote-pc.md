---
title: Mounting folder remote pc
layout: post
---

Ketika pengguna linux seperti saya ingin mengakses folder yang telah dishare oleh pengguna windows dalam satu jaringan, contohnya pada jaringan kantor tempat saya bekerja, cara dibawah ini lah yang biasa saya kerjakan.

1. Periksa terlebih dulu folder yang mau kita akses diremote pc dengan perintah:  
   $sudo smbclient -L //ipremote pc/ -U administrator  

   masukkan password administrator, kemudian  
   $sudo mount -t cifs //ipremote pc/sharing-folder/ /mnt/hd/ --verbose -o user=administrator  

   masukkan kembali password administrator yang diminta..  

2. Maka folder diremote pc dapat diakses pada folder /mnt/hd/ dikomputer lokal milik kita..  

Sekian, semoga bermanfaat ...barakallah fiikum.

