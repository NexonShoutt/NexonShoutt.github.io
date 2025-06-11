---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 7: Breadth-First Search (BFS)"
date:   2025-06-11 21:46:00 +0800
categories: rangkuman-lengkap algoritma
tags: graph-traversal bfs shortest-path
---

## Pengertian dan Konsep Dasar
[cite_start]**Breadth-First Search (BFS)** adalah sebuah algoritma untuk menjelajahi atau mencari dalam struktur data graf atau pohon.  [cite_start]Ciri khas utama dari BFS adalah cara penelusurannya yang **melebar** atau **berdasarkan level**.  [cite_start]BFS akan mengeksplorasi semua simpul (node) yang berada pada jarak terdekat dari titik awal terlebih dahulu, sebelum beralih ke simpul-simpul yang berada di level yang lebih jauh.  [cite_start]Ini sering diilustrasikan seperti sedang memeriksa seluruh ruangan di lantai pertama sebuah gedung sebelum naik ke lantai berikutnya. 

[cite_start]Untuk mengelola urutan penelusuran ini, BFS menggunakan struktur data **Queue (antrian)**, yang bekerja berdasarkan prinsip *First-In, First-Out* (FIFO). 

## Langkah-langkah Algoritma BFS
[cite_start]Proses penelusuran menggunakan BFS mengikuti langkah-langkah sistematis berikut: 
1.  [cite_start]**Inisialisasi**: Tentukan simpul awal (*start node*) dan masukkan ke dalam sebuah *queue*.  Tandai simpul awal ini sebagai "sudah dikunjungi" untuk menghindari pemrosesan ulang.
2.  [cite_start]**Loop Utama**: Selama *queue* tidak kosong, lakukan langkah-langkah berikut: 
    a.  **Dequeue**: Keluarkan simpul dari bagian paling depan *queue*.  Simpul ini menjadi simpul aktif saat ini.
    b.  **Periksa Tujuan**: Cek apakah simpul aktif ini adalah simpul tujuan (*goal node*).  Jika ya, pencarian berhasil dan dapat dihentikan.
    c.  **Kunjungi Tetangga**: Untuk setiap simpul tetangga dari simpul aktif, periksa apakah tetangga tersebut sudah pernah dikunjungi. 
    d.  **Enqueue**: Jika seorang tetangga belum dikunjungi, tandai sebagai "sudah dikunjungi" dan masukkan tetangga tersebut ke bagian belakang *queue*. 
3.  **Selesai**: Jika *queue* menjadi kosong dan simpul tujuan belum ditemukan, berarti tidak ada jalur dari simpul awal ke simpul tujuan. 

## Aplikasi Nyata BFS
[cite_start]BFS sangat berguna untuk menemukan jalur terpendek pada graf yang tidak berbobot (*unweighted graph*) dan memiliki banyak aplikasi praktis: 
* [cite_start]**Pencarian Jalur di Peta dan Navigasi**: Digunakan untuk menemukan rute terpendek dari titik A ke B dengan asumsi semua edge memiliki bobot yang sama (misal, jumlah jalan, bukan jarak). 
* [cite_start]**Jaringan Sosial**: Platform seperti Facebook atau LinkedIn menggunakan BFS untuk fitur seperti "Orang yang mungkin Anda kenal".  [cite_start]Algoritma ini akan mencari teman Anda (level 1), lalu teman dari teman Anda (level 2), dan seterusnya. 
* [cite_start]**Jaringan Komputer**: BFS digunakan untuk memetakan semua perangkat yang terhubung dalam sebuah jaringan (misalnya, *crawling* jaringan) atau untuk menemukan semua komputer yang dapat dijangkau dari satu titik. 
* [cite_start]**Permainan dan Labirin**: Dalam game, BFS digunakan untuk menghitung rute terpendek bagi karakter untuk bergerak dari satu titik ke titik lain. 

## Kelebihan dan Kekurangan
* [cite_start]**Kelebihan**: BFS **menjamin ditemukannya solusi yang paling baik** (optimal dan komplit) jika ada, khususnya untuk mencari jalur terpendek pada graf tak berbobot. 
* [cite_start]**Kekurangan**: Membutuhkan **memori dan waktu yang cukup banyak** karena harus menyimpan semua simpul pada satu level di dalam *queue* sebelum melanjutkan ke level berikutnya. 

## Kesimpulan
[cite_start]BFS adalah algoritma penelusuran graf yang menjelajahi simpul secara berlapis dari titik awal.  [cite_start]Dengan menggunakan *queue*, BFS memastikan semua simpul pada jarak terdekat dijelajahi terlebih dahulu,  [cite_start]membuatnya ideal untuk mencari jalur terpendek pada graf tak berbobot  [cite_start]dan efektif dalam berbagai aplikasi.