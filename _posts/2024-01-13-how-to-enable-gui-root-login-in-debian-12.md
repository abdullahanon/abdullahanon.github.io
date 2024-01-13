---
title: Bagaimana menghidupkan fungsi root login gui pada debian 12
layout: post
---

Untuk merubah ukuran partisi home/user pada debian dibutuhkan login melalui root agar terlepas dari mounting home/user, sayangnya secara default
fungsi ini di disable oleh debian untuk masalah keamanan, alhamdulillah bisa kita atasi dengan beberapa langkah berikut:

1. Ubah user kita menjadi root, kemudian edit file /etc/gdm3/daemon.conf, dibawah [security] ketik AllowRoot = true, Simpan dan keluar dari daemon.conf.
2. Setelah kita tutup file daemon.conf diatas kemudian kita edit file /etc/pam.d/gdm-password, kemudian aktifkan tanda komentar pada #auth	required	pam_succeed_if.so user != root quiet_success,
Simpan dan keluar dari file gdm-password.
3. Kemudian reboot komputer kita, maka akan muncul root login GUI yang nantinya bisa kita gunakan untuk merubah ukuran partisi home/user pada komputer kita.