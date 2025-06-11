---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 2: Fractional Knapsack"
date:   2025-06-11 21:41:00 +0800
categories: rangkuman-lengkap algoritma
tags: greedy-algorithm knapsack optimization
---

## Definisi dan Konsep Dasar
**Knapsack Problem** adalah sebuah masalah optimasi di mana kita harus memilih barang-barang dari sekumpulan item yang tersedia untuk dimasukkan ke dalam ransel (knapsack) agar nilai totalnya maksimal, tanpa melebihi kapasitas berat ransel tersebut.

Terdapat dua variasi utama dari masalah ini:
1.  **0/1 Knapsack**: Pada variasi ini, kita hanya bisa memilih untuk mengambil seluruh barang atau tidak sama sekali. Barang tidak boleh dipotong. Masalah ini lebih kompleks dan biasanya diselesaikan dengan metode pemrograman dinamis.
2.  **Fractional Knapsack**: Ini adalah variasi di mana kita diizinkan untuk mengambil sebagian (fraksi) dari sebuah barang. Tujuannya adalah untuk memaksimalkan nilai total barang dengan kemungkinan memotong barang sesuai kebutuhan.

## Karakteristik dan Strategi Penyelesaian
Karakteristik utama dari *Fractional Knapsack* adalah setiap barang memiliki berat (*weight*) dan nilai (*value*), dan barang tersebut boleh dipotong atau diambil sebagian. Karena sifat ini, masalah ini dapat diselesaikan secara efisien menggunakan pendekatan **Greedy Algorithm**.

Strategi penyelesaiannya adalah sebagai berikut:
1.  **Hitung Rasio Value/Weight**: Untuk setiap item, hitung rasio nilai per satuan beratnya (value/weight). Rasio ini merepresentasikan "kepadatan nilai" dari setiap item.
2.  **Urutkan Item**: Urutkan semua item berdasarkan rasio yang telah dihitung, dari yang tertinggi hingga terendah.
3.  **Isi Knapsack**: Mulai dari item dengan rasio tertinggi, ambil sebanyak mungkin hingga knapsack penuh. Jika sebuah item tidak dapat dimasukkan seluruhnya karena kapasitas yang tersisa tidak mencukupi, ambil sebagian (fraksi) dari item tersebut untuk mengisi sisa kapasitas knapsack.

## Analisis Kompleksitas
* **Kompleksitas Waktu**: Kompleksitas waktu dominan dari algoritma ini adalah **O(n log n)**, yang berasal dari langkah pengurutan item berdasarkan rasio nilainya. Proses memasukkan item ke dalam tas setelah diurutkan hanya memerlukan waktu O(n).
* **Kompleksitas Ruang**: Dibutuhkan ruang O(n) untuk menyimpan data item.

## Aplikasi di Dunia Nyata
Meskipun terdengar abstrak, konsep *Fractional Knapsack* memiliki banyak aplikasi praktis, antara lain:
* Penjadwalan tugas dengan sumber daya yang terbatas
* Alokasi dana investasi ke beberapa proyek
* Pengalokasian *bandwidth* dalam jaringan komputer
* Optimisasi masalah logistik

## Kesimpulan
*Fractional Knapsack* adalah variasi dari *Knapsack Problem* yang dapat diselesaikan secara efisien dan optimal menggunakan algoritma *greedy*. Berbeda dengan versi 0/1, pada versi ini barang boleh diambil sebagian (fraksional). Dengan menghitung rasio nilai per berat dan memprioritaskan item dengan rasio tertinggi, kita bisa mendapatkan solusi optimal secara cepat dan sederhana. Pendekatan *greedy* ini efektif karena pilihan optimal lokal (memilih item dengan kepadatan nilai tertinggi) akan mengarah pada solusi optimal global dalam kasus *Fractional Knapsack*.