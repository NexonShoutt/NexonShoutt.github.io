---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 4: N-Queens Problem"
date:   2025-06-11 21:43:00 +0800
categories: rangkuman-lengkap algoritma
tags: backtracking csp recursive
---

## Definisi Masalah
**N-Queens Problem** adalah sebuah permasalahan klasik dalam ilmu komputer dan matematika kombinatorik.  Tantangannya adalah menempatkan N buah ratu catur pada sebuah papan catur berukuran N×N sedemikian rupa sehingga tidak ada dua ratu yang saling menyerang.  Menurut aturan catur, seorang ratu dapat menyerang secara horizontal, vertikal, dan diagonal.  Oleh karena itu, solusi yang valid harus memastikan bahwa tidak ada dua ratu yang berada pada baris, kolom, atau diagonal yang sama. 

## Tujuan dan Pentingnya Masalah
Tujuan utama dari masalah N-Queens adalah:
1.  **Menemukan Semua Konfigurasi**: Mengidentifikasi semua kemungkinan penempatan ratu yang memenuhi syarat tidak saling menyerang. 
2.  **Menguji Algoritma**: Menjadi studi kasus untuk mengembangkan dan menguji efisiensi berbagai algoritma pencarian seperti *backtracking*, *Depth-First Search (DFS)*, dan algoritma genetika. 
3.  **Melatih Logika**: Melatih logika pemrograman, terutama dalam konteks *Constraint Satisfaction Problem (CSP)*, yaitu masalah yang melibatkan pemenuhan serangkaian batasan (constraints). 

## N-Queens sebagai Masalah Backtracking
**Backtracking** adalah teknik penyelesaian masalah yang paling umum digunakan untuk N-Queens.  Ini adalah pendekatan pencarian solusi secara sistematis yang mencoba membangun solusi langkah demi langkah dan akan "mundur" (*backtrack*) ketika menemui jalan buntu. 

Cara kerja *backtracking* dalam N-Queens:
1.  **Pendekatan Bertahap**: Kita menempatkan ratu satu per satu, biasanya dimulai dari kolom pertama. 
2.  **Pemeriksaan Batasan (Constraint Check)**: Untuk setiap baris di kolom saat ini, kita mencoba meletakkan ratu dan memeriksa apakah posisi tersebut aman (yaitu, tidak diserang oleh ratu yang telah ditempatkan di kolom-kolom sebelumnya). 
3.  **Eksplorasi Rekursif**: Jika posisi tersebut aman, kita secara rekursif melanjutkan pencarian ke kolom berikutnya untuk menempatkan ratu selanjutnya. 
4.  **Backtrack**: Jika di sebuah kolom tidak ada baris yang aman untuk menempatkan ratu, berarti pilihan di kolom sebelumnya salah. Algoritma akan mundur ke kolom sebelumnya, menghapus ratu dari posisi terakhirnya (*undo*), dan mencoba menempatkannya di baris lain yang valid. 
5.  **Basis Kasus**: Jika semua N ratu telah berhasil ditempatkan (yaitu, kita telah mencapai kolom setelah kolom terakhir), maka satu solusi telah ditemukan dan dapat dicatat. 

## Aplikasi Dunia Nyata
Meskipun berbasis permainan catur, prinsip di balik N-Queens dapat diterapkan dalam masalah nyata seperti penjadwalan tugas, penempatan modul dalam sirkuit elektronik, dan pengalokasian sumber daya yang saling eksklusif. 

## Kesimpulan
N-Queens adalah masalah fundamental yang menjadi contoh utama dari *Constraint Satisfaction Problem* dan sangat relevan untuk mempelajari teknik algoritma *backtracking*.  Masalah ini menunjukkan bagaimana kompleksitas dapat meningkat secara eksponensial seiring dengan bertambahnya nilai N, menjadikannya tolok ukur yang baik untuk mengevaluasi efisiensi algoritma.