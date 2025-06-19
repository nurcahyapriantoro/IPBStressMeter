<div align="center">
  <h1 align="center">IPB Stress-Meter</h1>
  <p align="center">
    <strong>Sistem Cerdas untuk Deteksi Stres Akademik Mahasiswa berbasis Fuzzy Inference System</strong>
    <br />
    <br />
  </p>
</div>

<div align="center">

![HTML5](https://img.shields.io/badge/HTML5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-%23F7DF1E.svg?style=for-the-badge&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![scikit-fuzzy](https://img.shields.io/badge/Scikit--Fuzzy-orange?style=for-the-badge)

</div>

---

## 📜 Tentang Proyek

IPB Stress-Meter adalah aplikasi web interaktif yang dirancang untuk membantu mahasiswa mengenali dan memahami tingkat stres akademik mereka. Dengan memanfaatkan kekuatan Logika Fuzzy, sistem ini mampu mengolah input yang bersifat subjektif menjadi sebuah skor kuantitatif yang logis, memberikan gambaran yang jelas mengenai kondisi mental pengguna.

### 🎯 Tujuan Proyek
Mengembangkan sebuah sistem cerdas yang mampu memberikan estimasi tingkat stres akademik mahasiswa IPB secara personal berdasarkan faktor-faktor kunci dalam kehidupan perkuliahan.

### 🧠 Masalah yang Dipecahkan
> Mahasiswa seringkali tidak menyadari tingkat stres yang dialaminya hingga mencapai level yang mengganggu kesehatan mental dan performa akademik. Dibutuhkan sebuah alat bantu yang objektif dan mudah diakses untuk deteksi dini, sehingga dapat dilakukan intervensi yang tepat sebelum stres berdampak lebih buruk.

---

## ✨ Fitur Utama

- **Antarmuka Interaktif & Modern**: Desain UI yang elegan dengan efek *glassmorphism* dan visualisasi hasil menggunakan diagram *gauge* yang dinamis.
- **Input Manual Presisi**: Pengguna dapat memasukkan data secara manual untuk mendapatkan hasil yang lebih akurat sesuai kondisi mereka.
- **Logika Fuzzy yang Kompleks**: Menggunakan 18 aturan inferensi untuk memastikan akurasi dan sensitivitas terhadap berbagai kombinasi kondisi mahasiswa.
- **Rekomendasi Personal**: Memberikan saran dan tips yang disesuaikan dengan tingkat stres pengguna.

---

## 🔬 Metodologi: Fuzzy Inference System (FIS)

Sistem ini dibangun menggunakan Logika Fuzzy, sebuah pendekatan yang meniru cara manusia berpikir dengan mengolah variabel yang tidak pasti. Prosesnya terbagi menjadi tiga tahap utama:

1.  **Fuzzifikasi**: Mengubah input numerik yang tegas (misal: SKS = 21, Jam Tidur = 5) menjadi nilai keanggotaan dalam himpunan fuzzy (misal: SKS `Banyak` bernilai 0.75, Jam Tidur `Kurang` bernilai 1.0).
2.  **Mesin Inferensi (Rule Evaluation)**: Mengevaluasi serangkaian aturan "IF-THEN" yang telah didefinisikan untuk menentukan kekuatan setiap kemungkinan output.
3.  **Defuzzifikasi**: Mengkonversi hasil fuzzy dari tahap inferensi kembali menjadi sebuah nilai numerik tunggal (skor 0-100) yang merepresentasikan level stres.

---

## ⚙️ Parameter Sistem (Variabel Fuzzy)

Sistem ini menggunakan 4 Variabel Input (Antecedents) dan 1 Variabel Output (Consequent).

### A. Variabel Input

| Variabel | Deskripsi | Himpunan Fuzzy & Rentang Nilai |
| :--- | :--- | :--- |
| **Jumlah SKS** | Total SKS yang diambil, mengukur beban studi formal. | • **Sedikit**: 1 - 8 SKS<br>• **Normal**: 9 - 18 SKS<br>• **Banyak**: 18 - 24 SKS |
| **Rata-rata Jam Tidur** | Durasi tidur setiap malam sebagai indikator pemulihan. | • **Kurang**: 3 - 5 jam<br>• **Cukup**: 5.5 - 7 jam<br>• **Ideal**: 7.5 - 10 jam ++ |
| **Tingkat Kesulitan Tugas** | Penilaian subjektif (skala 1-10) terhadap beban tugas. | • **Mudah**: 1 - 4<br>• **Menantang**: 5 - 7<br>• **Sangat Sulit**: 8 - 10 |
| **Aktivitas Non-Akademik** | Alokasi waktu (jam/minggu) untuk kegiatan di luar akademik. | • **Rendah**: 1 - 5 jam<br>• **Sedang**: 6 - 12 jam<br>• **Tinggi**: 13 - 20 jam ++ |

### B. Variabel Output

| Variabel | Deskripsi | Himpunan Fuzzy & Rentang Nilai |
| :--- | :--- | :--- |
| **Level Stres** | Skor akhir (0-100) yang merepresentasikan estimasi stres. | • **Rendah**: 0 - 45<br>• **Sedang**: 35 - 75<br>• **Tinggi**: 65 - 100 |

<details>
<summary><strong>Klik untuk Lihat Detail 18 Aturan Fuzzy</strong></summary>

#### Aturan Pemicu Stres TINGGI (5 Aturan)
IF Jam Tidur 'Kurang' AND Kesulitan Tugas 'Sangat Sulit' THEN Stres 'Tinggi'.IF Jumlah SKS 'Banyak' AND Jam Tidur 'Kurang' THEN Stres 'Tinggi'.IF Jumlah SKS 'Banyak' AND Kesulitan Tugas 'Sangat Sulit' THEN Stres 'Tinggi'.IF Jam Tidur 'Kurang' AND Aktivitas Non-Akademik 'Tinggi' THEN Stres 'Tinggi'.IF Kesulitan Tugas 'Sangat Sulit' AND Aktivitas Non-Akademik 'Tinggi' THEN Stres 'Tinggi'.
#### Aturan Pemicu Stres SEDANG (9 Aturan)
IF Jumlah SKS 'Banyak' AND Jam Tidur 'Cukup' THEN Stres 'Sedang'.IF Jumlah SKS 'Normal' AND Kesulitan Tugas 'Sangat Sulit' THEN Stres 'Sedang'.IF Jumlah SKS 'Normal' AND Jam Tidur 'Kurang' THEN Stres 'Sedang'.IF Kesulitan Tugas 'Menantang' AND (Jam Tidur 'Kurang' OR Aktivitas Non-Akademik 'Tinggi') THEN Stres 'Sedang'.IF Kesulitan Tugas 'Sangat Sulit' AND Jam Tidur 'Ideal' THEN Stres 'Sedang'.IF Jumlah SKS 'Normal' AND Kesulitan Tugas 'Menantang' AND Aktivitas Non-Akademik 'Sedang' THEN Stres 'Sedang'.IF Jumlah SKS 'Banyak' AND Aktivitas Non-Akademik 'Rendah' AND Jam Tidur 'Ideal' THEN Stres 'Sedang'.IF Kesulitan Tugas 'Mudah' AND Aktivitas Non-Akademik 'Tinggi' THEN Stres 'Sedang'.IF Jumlah SKS 'Normal' AND Kesulitan Tugas 'Menantang' AND Jam Tidur 'Cukup' THEN Stres 'Sedang'.
#### Aturan Pemicu Stres RENDAH (4 Aturan)
IF Jumlah SKS 'Sedikit' THEN Stres 'Rendah'.IF Kesulitan Tugas 'Mudah' AND Aktivitas Non-Akademik 'Rendah' THEN Stres 'Rendah'.IF Jam Tidur 'Ideal' AND Kesulitan Tugas 'Menantang' AND Aktivitas Non-Akademik 'Rendah' THEN Stres 'Rendah'.IF Jumlah SKS 'Normal' AND Jam Tidur 'Ideal' AND Kesulitan Tugas 'Mudah' THEN Stres 'Rendah'.
</details>

---

## 🛠️ Alat dan Teknologi

-   **Aplikasi Web Interaktif**: HTML5, Tailwind CSS, JavaScript
-   **Pengembangan & Validasi Logika Awal**: Python, Scikit-fuzzy, Pandas, Matplotlib
-   **Pengumpulan Data**: Google Forms

---

## 🚀 Cara Menggunakan

Aplikasi ini dirancang untuk berjalan langsung di browser tanpa perlu instalasi apa pun.
1.  **Buka Aplikasi**: Buka file `ipb_stress_meter.html` di browser web modern (Chrome, Firefox, Edge, Safari).
2.  **Isi Data**: Masukkan nilai yang paling sesuai dengan kondisi Anda saat ini pada setiap kolom input.
3.  **Klik Tombol**: Tekan tombol **"Ayo Cek Level Stres Kamu"**.
4.  **Lihat Hasil**: Hasil akan ditampilkan secara visual pada diagram beserta level stres dan rekomendasi yang dipersonalisasi.

---

## 👨‍💻 Tim Pengembang

-   **Nurcahya Priantoro** (G6401221049)
-   **Rizky Rasyid Wirakusuma** (G6401221127)
-   **Muhammad Adelio Reynard** (G6401221113)
-   **Firdaus Rizqon Daron** (G6401221123)
-   **Chairul Rifky Tirta Cahyadi** (G6401221067)
