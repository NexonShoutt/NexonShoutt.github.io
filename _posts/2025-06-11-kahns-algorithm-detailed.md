---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 9: Kahn's Algorithm"
date:   2025-06-11 21:48:00 +0800
categories: rangkuman-lengkap algoritma
tags: topological-sort graph dag
---

## Definisi dan Tujuan
**Algoritma Kahn** adalah sebuah algoritma yang digunakan untuk melakukan **pengurutan topologis (*topological sorting*)**.  Pengurutan topologis adalah proses untuk menentukan urutan linear dari simpul-simpul dalam sebuah **Directed Acyclic Graph (DAG)**.  Dalam urutan ini, untuk setiap sisi yang terarah dari simpul `u` ke simpul `v` (`u → v`), simpul `u` harus selalu muncul sebelum simpul `v`.  Algoritma Kahn pada dasarnya adalah pendekatan berbasis **Breadth-First Search (BFS)** untuk menyelesaikan masalah ini. 

## Kapan Algoritma Kahn Dibutuhkan?
Algoritma ini sangat penting dalam skenario di mana urutan eksekusi atau pemrosesan bergantung pada prasyarat, seperti: 
* **Menjadwalkan Tugas**: Menentukan urutan tugas dalam sebuah proyek di mana beberapa tugas harus diselesaikan sebelum yang lain dapat dimulai. 
* **Memproses Dependensi**: Misalnya dalam *build system* (kompilasi program) atau manajer paket, di mana dependensi harus diinstal atau dikompilasi terlebih dahulu. 
* **Mendeteksi Siklus**: Algoritma ini juga dapat digunakan untuk mendeteksi apakah sebuah graf terarah memiliki siklus atau tidak. 

## Cara Kerja Algoritma Kahn
Algoritma ini bekerja secara sistematis dengan memanfaatkan konsep **in-degree** (jumlah sisi yang masuk ke sebuah simpul). 
1.  **Hitung In-degree**: Pertama, hitung *in-degree* untuk setiap simpul dalam graf. 
2.  **Inisialisasi Antrean (Queue)**: Identifikasi semua simpul yang memiliki *in-degree* sama dengan 0.  Simpul-simpul ini tidak memiliki prasyarat dan dapat dieksekusi pertama kali. Masukkan semua simpul ini ke dalam sebuah *queue*. 
3.  **Proses Antrean**: Selama *queue* tidak kosong: 
    a.  Keluarkan sebuah simpul (`u`) dari depan *queue*. Tambahkan simpul ini ke dalam daftar hasil pengurutan topologis.
    b.  Untuk setiap simpul tetangga (`v`) dari `u` (yaitu, ada sisi `u → v`):
        i.  Kurangi *in-degree* dari `v` sebesar 1. Ini secara simbolis berarti satu prasyarat untuk `v` telah terpenuhi.
        ii. Jika setelah pengurangan, *in-degree* dari `v` menjadi 0, masukkan `v` ke dalam *queue*.
4.  **Verifikasi Hasil**: Setelah loop selesai, periksa apakah jumlah simpul dalam daftar hasil sama dengan jumlah total simpul dalam graf. Jika ya, urutan tersebut valid dan graf tersebut adalah DAG. Jika tidak, graf tersebut mengandung setidaknya satu siklus. 

## Kelebihan dan Kekurangan
* **Kelebihan**:
    * **Efisien**: Memiliki kompleksitas waktu **O(V + E)**, di mana V adalah jumlah simpul dan E adalah jumlah sisi, membuatnya sangat efisien. 
    * **Deteksi Siklus**: Secara inheren mampu mendeteksi keberadaan siklus dalam graf berarah. 
    * **Sangat Cocok untuk Masalah Dependensi**: Merupakan solusi standar untuk masalah yang melibatkan prasyarat. 
* **Kekurangan**:
    * **Hanya untuk DAG**: Tidak dapat digunakan pada graf yang mengandung siklus. 
    * **Output Bervariasi**: Bisa menghasilkan lebih dari satu urutan topologis yang valid, tergantung pada urutan pemrosesan simpul di dalam *queue*. 
    * **Struktur Data Tambahan**: Memerlukan struktur data tambahan untuk menyimpan graf dan nilai *in-degree*. 

## Kesimpulan
Algoritma Kahn adalah metode yang efisien dan sistematis untuk melakukan pengurutan topologis pada DAG.  Dengan memanfaatkan *in-degree* dan *queue*, algoritma ini mampu menyusun simpul berdasarkan ketergantungan serta mendeteksi siklus.  Dengan kompleksitas waktu O(V+E), algoritma ini sangat berguna dalam berbagai aplikasi nyata.