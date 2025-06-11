---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 5: Subset Sum Problem"
date:   2025-06-11 21:44:00 +0800
categories: rangkuman-lengkap algoritma
tags: np-complete dynamic-programming recursive
---

## Definisi dan Konsep Dasar
[cite_start]**Subset Sum Problem (SSP)** adalah sebuah masalah klasik dalam ilmu komputer yang termasuk dalam kategori **NP-Complete**.  [cite_start]Masalah ini menanyakan: diberikan sebuah himpunan (atau array) bilangan bulat dan sebuah nilai target, apakah ada sebuah *subset* (himpunan bagian) dari himpunan tersebut yang jumlah total elemennya sama persis dengan nilai target yang diberikan?.  [cite_start]SSP merupakan *decision problem*, yang berarti jenis masalah ini hanya membutuhkan jawaban "ya" atau "tidak" ("True" atau "False"). 

## Variasi-variasi Subset Sum Problem
Masalah SSP memiliki beberapa variasi penting yang masing-masing memiliki batasan dan aplikasi yang berbeda:
* [cite_start]**Bounded Subset Sum Problem**: Setiap elemen dalam himpunan hanya boleh digunakan satu kali dalam pembentukan subset.  Ini adalah bentuk paling umum dari SSP.
* [cite_start]**Unbounded Subset Sum Problem**: Setiap elemen dalam himpunan boleh digunakan berulang kali untuk mencapai jumlah target. 
* [cite_start]**Partition Problem**: Sebuah kasus khusus di mana tujuannya adalah membagi sebuah himpunan bilangan bulat menjadi dua subset yang memiliki jumlah total yang sama. 
* [cite_start]**Exact k Elements Subset Sum**: Menambahkan batasan bahwa subset yang ditemukan harus terdiri dari tepat *k* elemen. 
* [cite_start]**Multi-target Subset Sum**: Mencari subset yang harus memenuhi lebih dari satu kriteria secara bersamaan, misalnya total harga dan total berat. 
* [cite_start]**Approximate Subset Sum**: Jika tidak ada subset yang jumlahnya tepat sama dengan target, maka dicari subset yang jumlahnya paling mendekati target tanpa melebihinya. 

## Pendekatan Solusi
Ada beberapa pendekatan untuk menyelesaikan SSP:
1.  [cite_start]**Pendekatan Rekursif (Brute-Force)**: Ini adalah pendekatan paling dasar yang secara eksplisit memeriksa semua kemungkinan subset.  [cite_start]Untuk setiap elemen, ada dua pilihan: sertakan elemen tersebut dalam subset, atau abaikan.  [cite_start]Pendekatan ini memiliki kompleksitas waktu eksponensial **O(2^n)**, sehingga sangat tidak efisien untuk himpunan yang besar. 
2.  [cite_start]**Pendekatan Dynamic Programming (DP)**: Pendekatan ini jauh lebih efisien dan merupakan solusi standar untuk SSP.  [cite_start]Kompleksitas waktunya adalah **O(n × sum)**. 
    * [cite_start]**Memoization (Top-Down)**: Menggabungkan pendekatan rekursif dengan penyimpanan hasil submasalah yang sudah dihitung dalam sebuah *cache* untuk menghindari perhitungan berulang. 
    * [cite_start]**Tabulation (Bottom-Up)**: Menggunakan pendekatan iteratif dengan membangun sebuah tabel DP `dp[n+1][sum+1]` dari kasus terkecil ke atas. 
    * [cite_start]**Optimasi Ruang (Space Optimization)**: Pendekatan tabulasi dapat dioptimalkan untuk mengurangi penggunaan memori dari `O(n × sum)` menjadi hanya **O(sum)**. 

## Aplikasi Dunia Nyata
[cite_start]SSP memiliki banyak aplikasi penting dalam dunia praktis, di antaranya: 
* [cite_start]**Kriptografi**: Digunakan dalam sistem kriptografi berbasis ransel. 
* [cite_start]**Alokasi Sumber Daya**: Membantu memilih subset proyek atau item agar sesuai dengan anggaran yang tersedia. 
* [cite_start]**Genetika dan Bioinformatika**: Menganalisis kombinasi gen atau fragmen DNA. 
* [cite_start]**Keuangan dan Investasi**: Menentukan apakah target investasi dapat dicapai dengan kombinasi aset yang tepat.