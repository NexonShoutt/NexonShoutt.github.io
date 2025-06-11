---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 1: Activity Selection Problem"
date:   2025-06-11 21:40:00 +0800
categories: rangkuman-lengkap algoritma
tags: greedy-algorithm optimization scheduling
---

## Pendahuluan dan Definisi Masalah
**Activity Selection Problem** adalah sebuah masalah optimasi klasik dalam ilmu komputer. Tujuannya adalah untuk memilih jumlah aktivitas maksimum yang dapat dilakukan oleh satu orang atau satu sumber daya dari sekumpulan aktivitas yang tersedia, di mana setiap aktivitas memiliki waktu mulai (s) dan waktu selesai (f) yang telah ditentukan. Kunci dari masalah ini adalah aktivitas yang dipilih tidak boleh saling tumpang tindih secara waktu. Dua aktivitas dianggap **kompatibel** jika salah satunya selesai sebelum aktivitas lainnya dimulai. Tantangannya adalah menemukan subset aktivitas kompatibel yang terbesar.

## Konsep Kunci: Pendekatan Algoritma Greedy
Masalah ini dapat diselesaikan secara efisien menggunakan **algoritma *greedy*** (serakah). Algoritma *greedy* adalah strategi yang membuat pilihan yang tampak paling optimal pada setiap langkahnya, dengan harapan akan menghasilkan solusi optimal secara global. Algoritma ini disebut "serakah" karena tidak mempertimbangkan konsekuensi di masa depan; ia hanya mengambil pilihan terbaik yang tersedia saat itu.

Dalam konteks *Activity Selection Problem*, strategi *greedy* yang terbukti efektif adalah **memilih aktivitas dengan waktu selesai (finish time) paling awal**. Ide di baliknya adalah dengan menyelesaikan sebuah aktivitas secepat mungkin, kita akan memaksimalkan sisa waktu yang tersedia untuk memilih lebih banyak aktivitas lain yang tidak bentrok.

## Langkah-langkah Algoritma
Proses penyelesaian masalah ini mengikuti langkah-langkah terstruktur sebagai berikut:
1.  **Urutkan Aktivitas**: Langkah pertama dan paling krusial adalah mengurutkan semua aktivitas berdasarkan waktu selesainya (*finish time*) dalam urutan menaik.
2.  **Pilih Aktivitas Pertama**: Selalu pilih aktivitas pertama dari daftar yang sudah diurutkan (yaitu, aktivitas dengan waktu selesai paling awal) dan masukkan ke dalam himpunan solusi.
3.  **Iterasi dan Pilih Aktivitas Berikutnya**: Untuk setiap aktivitas berikutnya dalam daftar, periksa apakah waktu mulainya lebih besar atau sama dengan waktu selesai dari aktivitas terakhir yang dipilih. Jika ya (artinya tidak tumpang tindih), pilih aktivitas tersebut dan tambahkan ke himpunan solusi.

## Analisis Kompleksitas
* **Kompleksitas Waktu**: Total kompleksitas waktu algoritma ini adalah **O(n log n)**. Langkah yang paling memakan waktu adalah pengurutan awal aktivitas, yang menggunakan algoritma efisien seperti *Quick Sort* atau *Merge Sort*. Setelah diurutkan, proses pemilihan aktivitas hanya memerlukan satu kali iterasi (pass) melalui daftar, yang memakan waktu O(n).
* **Kompleksitas Ruang**: Kompleksitas ruang yang dibutuhkan adalah **O(n)** untuk menyimpan daftar aktivitas dan hasilnya.

## Aplikasi dan Kesimpulan
* **Aplikasi Dunia Nyata**: Konsep ini sangat berguna dalam berbagai skenario penjadwalan, seperti penjadwalan ruang kelas, jadwal rapat, alokasi penggunaan laboratorium, jadwal proses di CPU, hingga alokasi *bandwidth* di jaringan telekomunikasi.
* **Kekuatan dan Keterbatasan**: Kekuatan utama algoritma ini adalah kesederhanaannya, efisiensinya pada dataset besar, dan kemampuannya memberikan solusi optimal. Namun, keterbatasannya adalah ia memerlukan proses pengurutan dan kurang cocok untuk masalah dengan banyak batasan tambahan seperti prioritas atau biaya.
* **Kesimpulan**: *Activity Selection Problem* adalah masalah optimasi untuk memilih aktivitas sebanyak mungkin tanpa tumpang tindih. Masalah ini dapat diselesaikan secara efisien menggunakan pendekatan *greedy* dengan mengurutkan aktivitas berdasarkan waktu selesai, menghasilkan solusi optimal dengan kompleksitas O(n log n). Meskipun sangat efektif untuk penjadwalan sederhana, kasus yang lebih kompleks mungkin memerlukan metode lain seperti pemrograman dinamis.