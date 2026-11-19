<div align="center">
<img src="assets/logo/UPNYK.png" alt="Logo UPNYK" height="48" />
&nbsp;&nbsp;&nbsp;
<img src="assets/logo/LOGO_IF.png" alt="Logo Informatika" height="48" />
&nbsp;&nbsp;&nbsp;
<img src="assets/logo/LOGO_HIMA.png" alt="Logo HIMA Informatika" height="50" />

# Responsi Praktikum Struktur Data

![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

**Sistem Manajemen & Penyerapan Energi** — Informatika, UPN "Veteran" Yogyakarta

</div>

## Identitas Mahasiswa
* **Nama:** Gega Ramadhan
* **NIM:** 123250112
* **Kelas:** IF-C

## Deskripsi Proyek
Aplikasi berbasis *Command Line Interface* (CLI) yang ditulis dalam bahasa C++ untuk mensimulasikan alur masuk, pemrosesan, pencatatan riwayat, hingga penggunaan energi di dalam "Organ". Proyek ini mengintegrasikan tiga struktur data dinamis berbasis pointer (**Queue**, **Stack**, dan **Binary Search Tree**) dalam satu siklus alur data yang saling terhubung.


## Teknologi & Lingkungan Pengembangan
* **Bahasa Pemrograman:** C++ (Standard Library `<iostream>` dan `<string>`)
* **Manajemen Memori:** Alokasi memori dinamis (`new` dan `delete`) menggunakan *struct* dan *pointer*
* **Editor & Compiler:** Visual Studio Code dengan compiler MinGW / GCC (`g++`)
* **Target Sistem:** Windows Terminal / Command Prompt

## Implementasi Struktur Data (Detail Teknis)
Program ini menghubungkan tiga struktur data utama secara berurutan:

1. **Queue / Antrean (`nodeQueue` — FIFO):**
   * Diimplementasikan menggunakan *Single Linked List* dengan pointer `front` dan `last`.
   * Berfungsi menampung energi baru yang didaftarkan pengguna sebelum diproses.
   * Dilengkapi validasi keunikan `kodeEnergi` dengan mengecek seluruh node aktif di dalam *Queue* maupun *Stack* agar tidak terjadi duplikasi kode.

2. **Stack / Tumpukan (`nodeStack` — LIFO):**
   * Diimplementasikan menggunakan *Single Linked List* dengan pointer `top`.
   * Berfungsi menyimpan log riwayat energi yang telah berhasil diproses (*terserap*) secara kronologis terbalik (data terbaru berada di posisi paling atas).

3. **Binary Search Tree (`nodeTree` — BST):**
   * Diimplementasikan menggunakan *node* bercabang dua (`kiri` dan `kanan`) dengan pointer utama `root`, diurutkan berdasarkan nilai `kodeEnergi`.
   * Merepresentasikan penyimpanan energi aktif di dalam **Organ** yang siap dicari, ditelusuri, maupun digunakan kembali.
   * Mendukung operasi rekursif untuk penyisipan (`tambah_tree`), pencarian (`cari_tree`), penelusuran (`preorder`, `inorder`, `postorder`), serta penghapusan node (`hapus_tree`) yang menangani kasus 0 anak (*leaf*), 1 anak, maupun 2 anak menggunakan metode *in-order successor* (nilai terkecil dari *subtree* kanan).

##

| Menu | Nama Fitur | Fungsi & Mekanisme Teknis |
| :---: | :--- | :--- |
| **[1]** | **Tambah Energi** | Menambahkan data `kodeEnergi` (> 0) dan `nama` ke belakang antrean (*enqueue* pada `last`). Mendukung input berulang (`Y/N`) serta validasi tipe input dan duplikasi kode. |
| **[2]** | **Lihat Antrean Energi** | Melakukan *traversal* pada *Queue* dari `front` hingga `last` untuk menampilkan seluruh daftar energi yang sedang menunggu diproses. |
| **[3]** | **Proses Energi** | Mengambil elemen terdepan dari *Queue* (*dequeue* dari `front`), menyalinnya ke puncak *Stack* (*push* ke `top`), memasukkannya ke dalam *BST* (`root`), lalu membebaskan memori node antrean lama (`delete`). |
| **[4]** | **Lihat Energi yang Terserap** | Menampilkan daftar riwayat energi yang sudah diproses dengan menelusuri *Stack* mulai dari elemen paling atas (`top`). |
| **[5]** | **Hapus Riwayat Energi Teratas** | Menghapus catatan riwayat terbaru dengan operasi *pop* pada pointer `top` dari *Stack* dan membersihkan alokasi memorinya. |
| **[6]** | **Cari Energi di Organ** | Melakukan pencarian biner secara rekursif (`cari_tree`) berdasarkan `kodeEnergi` di dalam *Binary Search Tree*. |
| **[7]** | **Lihat Isi Organ** | Menampilkan seluruh energi yang tersimpan di *BST* melalui sub-menu pilihan metode *traversal*: **Pre-Order** (*Root-Left-Right*), **In-Order** (*Left-Root-Right* / terurut menaik), dan **Post-Order** (*Left-Right-Root*). |
| **[8]** | **Gunakan Energi** | Mencari energi berdasarkan kode di dalam *BST*, menampilkan detailnya sebagai energi yang digunakan, lalu menghapus node tersebut dari pohon (`hapus_tree`). |
| **[0]** | **Keluar** | Menghentikan perulangan utama program dan menutup aplikasi konsol. |


## Struktur Folder dan File

```text
responsi-struktur-data/
    ├── 123250112-Responsi.cpp 
    └── README.md  

```
