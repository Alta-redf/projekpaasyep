# 💻 LAPORAN PROYEK: PENGEMBANGAN WEB SERVER DAN APLIKASI SEDERHANA BY KELOMPOK 4

**Proyek:** Apache2

Proyek ini dibuat untuk memenuhi tugas mata pelajaran **Administrasi Sistem Jaringan (ASJ)**, yang merupakan salah satu elemen Capaian Pembelajaran Konsentrasi Keahlian Teknik Komputer dan Jaringan (**CP KKTKJ**) pada program TJKT. Proyek ini berfokus pada implementasi layanan Web Server, konfigurasi PHP, dan pengamanan koneksi menggunakan SSL/HTTPS.

---

### 1. 👥 Informasi Kelompok dan Spesifikasi Lingkungan Praktik

#### 1.1. Informasi Kelompok

| Peran | Nama Lengkap | Kelas |
| :--- | :--- | :--- |
| **Ketua Kelompok** | Alta Wisnu Murti Priyanto | XI TJKT 2 |
| Anggota 1 | Nika D Nugrahani | XI TJKT 2 |
| Anggota 2 | Sofia Nur Ramadani.K | XI TJKT 2 |
| Anggota 3 | Azmi Roudotunnisa | XI TJKT 2 |
| **Nama Sekolah/Institusi** | SMKN 1 SOREANG | |

#### 1.2. Spesifikasi Alat dan Bahan (Host) 🛠️

| Komponen | Deskripsi / Versi |
| :--- | :--- |
| **Virtualisasi** | VMware Workstation 17 Pro |
| **Sistem Operasi Host** | OS yang digunakan di laptop/PC utama, Windows 11 |
| **RAM Host (Minimal)** | 4 GB |
| **CPU Host** | Intel Celeron N4020 |

#### 1.3. Spesifikasi Server Virtual (VM) 🖥️

| Spesifikasi | Detail |
| :--- | :--- |
| **Sistem Operasi Tamu (Guest OS)** | Debian Trixie (12.x) |
| **Alamat IP Server** | `172.16.54.1` |
| **RAM VM** | 2 GB |
| **vCPU** | 2 Core |
| **Web Server yang Dipilih** | **Apache2** |
| **Versi PHP yang Dipakai** | **** |

---

### 2. 📝 Dokumentasi Teknis dan Langkah-Langkah Pengerjaan

#### 2.1. Persiapan Dasar (Debian Trixie di VMware)

1.  Melakukan *update* dan *upgrade* sistem.
    ```bash
    apt update && apt upgrade
    ```
2.  Memastikan konfigurasi jaringan (Bridge/NAT/Host-Only) sudah benar.

#### 2.2. Instalasi dan Konfigurasi Web Server 🌐

Kami menggunakan **Apache**. Berikut langkah-langkah utamanya:

* **Instalasi:**
    ```bash
    # apt install apache2
    # systemctl enable apache2
    # systemctl start apache2
    # systemctl status apache2
    ```
* **Konfigurasi Virtual Host/Server Block:**
    untuk Document Root saya menggunakan html dan untuk port 80.



#### 2.3. Implementasi SSL (HTTPS) 🔒

Untuk mengaktifkan akses HTTPS, kami membuat *self-signed certificate*.

1.  Membuat direktori untuk *certificate*.
2.  Membuat *Key* dan *Certificate* menggunakan OpenSSL.
3.  Memodifikasi konfigurasi *Web Server* untuk menggunakan port **443** dan menunjuk ke *certificate* yang telah dibuat, serta memastikan akses dapat dilakukan melalui `https://172.16.54.217`.

---

### 3. 📊 Analisis Web Server

Berdasarkan pengalaman kami dalam proyek ini, berikut adalah analisis kelebihan dan kekurangan dari *Web server* yang kami gunakan:

| Aspek | Kelebihan (Apache) 👍 | Kekurangan (Apache) 👎 |
| :--- | :--- | :--- |
| **Performa & Kecepatan** | Apache sangat mumpuni untuk situs web dengan lalu lintas rendah hingga sedang. Dengan konfigurasi default dan penyesuaian yang tepat, kinerjanya sangat memuaskan dan stabil. | Apache menggunakan arsitektur berbasis proses atau thread untuk setiap koneksi yang masuk (tergantung Multi-Processing Module/MPM yang digunakan). Hal ini menyebabkan konsumsi memori dan CPU yang signifikan saat lalu lintas meningkat, menjadikannya kurang efisien dalam penggunaan sumber daya dibandingkan server berbasis event-driven |
| **Kemudahan Konfigurasi**|  Relatif mudah diatur, bahkan bagi pemula, dan sangat cocok untuk situs seperti WordPress. | kekurangannya adalah konfigurasi yang terlalu fleksibel ini bisa membuka celah keamanan jika tidak ditangani dengan benar, serta potensi kesalahan yang lebih besar akibat kustomisasi. |
| **Fitur & Modularitas** | Struktur berbasis modul memungkinkan administrator untuk mengaktifkan atau menonaktifkan fitur sesuai kebutuhan tanpa harus mengubah kode inti. | Kekurangannya adalah kemudahan konfigurasi yang bisa menjadi celah keamanan jika tidak dikelola dengan benar, serta performa yang dapat menurun di bawah lalu lintas tinggi, terutama saat banyak permintaan ditangani oleh process tunggal.  |

---

### 4. 🧠 Refleksi Proyek: Kesan dan Kendala

#### 4.1. Kesan Selama Proses Pengerjaan ✨

 "Ternyata kerja kelompok itu lebih mudah jika dengan orang yg se frekuaensi, namun terkadang kerja kelompok justru lebih menegangkan dan dan degdegan jika dengan orang yang tidak se frekuesi, hal inilah yg membuat kami mulai belajar keluar dari zona nyaman,  don't give up"


#### 4.2. Kendala dan Solusi yang Diterapkan 💡
  
| Kendala yang Kalian Hadapi 🚧 | Solusi yang Ditemukan ✅ |
| :--- | :--- |
| Kurangnya komunikasi dan kekompokan | Kami mulai untuk mencoba memahami kondisi masing masing anggota kelompok 4, mulai dari pembagian tugas, pemilihan waktu, kami semua sesuaikan dengan kemampuan masing masing kelompok |

---

### 5. 📂 Dokumentasi Konten Website

Seluruh *source code* (Halaman Utama dan Halaman Profil) yang berada di *document root* server telah disalin dan di-*commit* ke dalam folder `/html` di *repository* GitHub ini.

---

### 6. 🎬 Dokumentasi Video Pengerjaan

Seluruh proses pengerjaan telah direkam dan diunggah ke YouTube.

**Link Video YouTube:**

[![Thumbnail Video Pengerjaan](https://img.youtube.com/vi/1-qlNtQS1OA/0.jpg)](https://www.youtube.com/watch?v=1-qlNtQS1OA)
