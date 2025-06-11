---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 3: Huffman Coding"
date:   2025-06-11 21:42:00 +0800
categories: rangkuman-lengkap algoritma
tags: kompresi lossless huffman-tree
---

## Pengantar Huffman Coding
**Huffman Coding** adalah sebuah algoritma kompresi data *lossless* yang sangat terkenal, dikembangkan oleh David A. Huffman pada tahun 1952. *Lossless* berarti tidak ada data yang hilang selama proses kompresi dan dekompresi; data asli dapat dipulihkan sepenuhnya. Tujuan utama dari algoritma ini adalah untuk mengurangi ukuran data dengan cara mengganti simbol (karakter) yang sering muncul dengan kode bit yang lebih pendek. Algoritma ini umum digunakan dalam format kompresi populer seperti JPEG dan MP3.

## Konsep Dasar dan Prinsip Kerja
Prinsip kerja Huffman Coding sepenuhnya didasarkan pada frekuensi kemunculan setiap karakter dalam data.
* **Karakter Frekuensi Tinggi**: Diberi kode biner yang pendek.
* **Karakter Frekuensi Rendah**: Diberi kode biner yang panjang.

Untuk merepresentasikan kode-kode ini, Huffman Coding menggunakan struktur data **pohon biner** khusus yang disebut **Pohon Huffman**. Dalam pohon ini, setiap daun (leaf node) mewakili sebuah karakter, dan jalur dari akar ke daun menentukan kode biner untuk karakter tersebut.

## Proses Pembuatan Pohon Huffman
Proses pembuatan kode Huffman mengikuti langkah-langkah *greedy* sebagai berikut:
1.  **Hitung Frekuensi**: Pertama, hitung frekuensi kemunculan setiap karakter unik dalam data sumber.
2.  **Buat Simpul Daun**: Buat simpul daun (leaf node) untuk setiap karakter, di mana setiap simpul berisi karakter itu sendiri dan frekuensinya.
3.  **Gabungkan Simpul Terkecil**: Dari semua simpul yang ada, pilih dua simpul dengan frekuensi paling kecil. Gabungkan kedua simpul ini menjadi satu simpul internal baru. Frekuensi simpul baru ini adalah jumlah dari frekuensi kedua simpul anaknya.
4.  **Ulangi Penggabungan**: Ulangi langkah 3 secara terus-menerus hingga semua simpul tergabung menjadi satu pohon tunggal (Pohon Huffman).
5.  **Tentukan Kode Biner**: Setelah pohon terbentuk, tentukan kode biner untuk setiap karakter dengan melakukan traversal dari akar ke daun. Biasanya, pergerakan ke cabang kiri diberi label '0' dan ke cabang kanan diberi label '1'.

## Analisis Kompleksitas
* **Kompleksitas Waktu**: Jika menggunakan *min-heap* untuk menyimpan simpul dan frekuensinya, kompleksitas waktu untuk membangun Pohon Huffman adalah **O(n log n)**, di mana *n* adalah jumlah karakter unik.

## Kelebihan dan Kekurangan
* **Kelebihan**:
    * Kompresi bersifat *lossless*, sehingga data asli tidak rusak.
    * Sangat efisien untuk data dengan distribusi frekuensi karakter yang tidak merata.
    * Digunakan secara luas dalam sistem kompresi file standar.
* **Kekurangan**:
    * Kurang optimal jika frekuensi kemunculan semua karakter hampir merata.
    * Memerlukan pengiriman atau penyimpanan tabel kode agar data dapat didekompresi.