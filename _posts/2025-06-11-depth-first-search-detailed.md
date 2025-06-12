---
layout: post
title:  "Ulasan Lengkap Materi Kelompok 8: Depth-First Search (DFS)"
date:   2025-06-11 21:47:00 +0800
categories: rangkuman-lengkap algoritma
tags: graph-traversal dfs recursive
---

## Definisi dan Prinsip Utama
**Depth-First Search (DFS)** adalah sebuah algoritma pencarian atau penelusuran pada struktur data graf atau pohon.  Berbeda dengan BFS yang melebar, DFS bekerja dengan cara menjelajahi satu cabang **sedalam mungkin** hingga mencapai titik akhir, sebelum akhirnya mundur (*backtrack*) untuk melanjutkan penelusuran ke cabang lain yang belum dijelajahi. 

Untuk mengelola urutan penelusuran ini, DFS secara implisit atau eksplisit menggunakan struktur data **Stack (tumpukan)**, yang bekerja berdasarkan prinsip *Last-In, First-Out* (LIFO). 

## Langkah-langkah Algoritma DFS
Proses penelusuran menggunakan DFS, terutama dalam implementasi iteratif menggunakan stack, adalah sebagai berikut:
1.  **Inisialisasi**: Masukkan simpul akar (atau simpul awal) ke dalam sebuah *stack*. 
2.  **Loop Utama**: Selama *stack* tidak kosong, lakukan langkah-langkah berikut: 
    a.  **Pop**: Ambil simpul dari bagian paling atas *stack*. 
    b.  **Periksa Kunjungan**: Jika simpul tersebut belum dikunjungi:
        i.  Tandai simpul tersebut sebagai "sudah dikunjungi".
        ii. Cek apakah simpul ini adalah solusi yang dicari. Jika ya, pencarian bisa dihentikan. 
        iii. Jika bukan solusi, masukkan seluruh node anak (tetangga) yang belum dikunjungi dari simpul tersebut ke dalam *stack*.  Urutan memasukkan anak akan mempengaruhi jalur penelusuran.
3.  **Selesai**: Pencarian berakhir jika solusi ditemukan atau jika *stack* sudah kosong. 

## Kelebihan dan Kekurangan
* **Kelebihan**:
    * **Penggunaan Memori Lebih Efisien**: DFS biasanya membutuhkan lebih sedikit memori dibandingkan BFS. 
    * **Mudah Diimplementasikan**: Terutama menggunakan rekursi, implementasi DFS bisa sangat sederhana dan elegan. 
    * **Cocok untuk Kedalaman Maksimal**: Sangat baik digunakan untuk menemukan solusi yang berada jauh di dalam pohon pencarian. 
* **Kekurangan**:
    * **Tidak Menjamin Solusi Terbaik**: DFS tidak menjamin ditemukannya jalur terpendek atau solusi yang paling optimal. 
    * **Risiko Infinite Loop**: Pada graf yang memiliki siklus (*cyclic graph*), DFS bisa terjebak dalam perulangan tak terbatas jika tidak ada mekanisme untuk melacak simpul yang sudah dikunjungi. 
    * **Kurang Efisien pada Graf Dangkal dan Lebar**: Jika solusi berada dekat dengan akar tetapi pada cabang yang berbeda, DFS mungkin harus menjelajahi cabang yang sangat dalam terlebih dahulu sebelum menemukannya. 

## Kesimpulan
DFS adalah algoritma penelusuran yang menjelajahi simpul sedalam mungkin pada satu cabang sebelum melakukan *backtracking*.  Dengan menggunakan prinsip LIFO dari sebuah *stack*,  DFS sangat efisien dalam penggunaan memori dan cocok untuk mencari solusi di kedalaman maksimal.  Urutan penelusuran DFS bisa berbeda-beda tergantung pada urutan pemrosesan simpul anaknya.