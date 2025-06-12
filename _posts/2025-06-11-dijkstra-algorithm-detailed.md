---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 10: Algoritma Dijkstra"
date:   2025-06-11 21:49:00 +0800
categories: rangkuman-lengkap algoritma
tags: shortest-path graph dijkstra
---

## Definisi dan Tujuan
**Algoritma Dijkstra** adalah sebuah metode atau algoritma serakah (*greedy*) yang digunakan untuk menyelesaikan masalah pencarian **jalur terpendek** (*shortest path*) dari satu titik ke semua titik lain dalam sebuah graf berbobot.  Graf tersebut terdiri dari sekumpulan simpul (titik) dan sisi (hubungan) yang setiap sisinya memiliki **bobot** non-negatif yang merepresentasikan jarak, waktu, atau biaya.  Tujuan utama algoritma ini adalah untuk menemukan jalur dengan total bobot minimum dari sebuah simpul awal (*source*) ke setiap simpul lain dalam graf. 

## Cara Kerja Algoritma
Algoritma Dijkstra bekerja dengan cara membangun sebuah himpunan simpul yang jalur terpendeknya dari sumber sudah diketahui.  Berikut adalah langkah-langkah kerjanya:
1.  **Inisialisasi**: Buat sebuah tabel atau array untuk menyimpan jarak terpendek dari simpul awal ke setiap simpul lainnya.  Inisialisasi jarak ke simpul awal sebagai 0, dan jarak ke semua simpul lainnya sebagai tak terhingga (infinity).
2.  **Pilih Simpul Awal**: Tentukan simpul awal dan tandai sebagai simpul saat ini. 
3.  **Kunjungi Tetangga**: Dari simpul saat ini, periksa semua simpul tetangganya yang belum dikunjungi. Hitung jarak baru ke setiap tetangga melalui simpul saat ini (jarak simpul saat ini + bobot sisi ke tetangga). 
4.  **Perbarui Jarak (Relaxation)**: Jika jarak yang baru dihitung lebih pendek dari jarak yang tercatat saat ini di tabel, perbarui jaraknya. 
5.  **Pilih Simpul Berikutnya**: Setelah mengunjungi semua tetangga dari simpul saat ini, tandai simpul saat ini sebagai "telah dikunjungi". Kemudian, pilih simpul yang belum dikunjungi dengan jarak terpendek dari tabel sebagai simpul saat ini yang baru. 
6.  **Ulangi**: Ulangi langkah 3-5 sampai semua simpul telah dikunjungi.  Jalur terpendek ke setiap simpul kini telah ditemukan.

## Aplikasi di Dunia Nyata
Algoritma Dijkstra sangat fundamental dan memiliki banyak aplikasi praktis, di antaranya:
* **Sistem Navigasi (GPS)**: Untuk mencari rute terpendek atau tercepat dari satu lokasi ke lokasi lain.  Jalanan adalah sisi dan persimpangan adalah simpul, dengan bobot berupa jarak atau waktu tempuh.
* **Jaringan Komputer**: Untuk menemukan jalur terbaik dalam mengirimkan paket data dari satu router ke router lain (*routing*). 
* **Logistik dan Pengiriman Barang**: Perusahaan ekspedisi menggunakannya untuk menentukan rute pengiriman yang paling efisien agar hemat waktu dan biaya. 

## Kelebihan dan Kekurangan
* **Kelebihan**:
    * **Optimal**: Selalu menjamin ditemukannya jalur terpendek selama semua bobot sisi bernilai non-negatif. 
    * **Efisien**: Sangat efisien untuk banyak aplikasi, terutama jika diimplementasikan dengan struktur data *priority queue*. 
    * **Fleksibel**: Dapat menemukan jalur terpendek dari satu sumber ke semua tujuan lain dalam sekali eksekusi. 
* **Kekurangan**:
    * **Tidak Bekerja dengan Bobot Negatif**: Algoritma ini akan gagal memberikan hasil yang benar jika terdapat sisi dengan bobot negatif dalam graf. 
    * **Kurang Efisien pada Graf Besar dan Jarang**: Pada graf yang sangat besar dan *sparse* (jarang terhubung), kinerjanya bisa lebih lambat dibandingkan algoritma lain. 
    * **Perhitungan Luas**: Jika hanya butuh jalur dari A ke B, Dijkstra tetap menghitung jarak ke semua simpul lain yang bisa jadi tidak efisien. 

## Kesimpulan
Algoritma Dijkstra adalah salah satu algoritma pencarian jalur terpendek yang paling efisien dan banyak digunakan.  Dengan pendekatan *greedy*-nya, Dijkstra secara akurat menemukan solusi optimal untuk graf berbobot non-negatif  dan menjadi tulang punggung bagi banyak aplikasi di dunia nyata.