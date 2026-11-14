# Dataset Putusan Pidana Khusus Narkotika dan Psikotropika – PN Bangkalan

## Deskripsi

Dataset ini berisi 50 dokumen putusan Pengadilan Negeri Bangkalan pada perkara pidana khusus yang berkaitan dengan narkotika. Dokumen dikumpulkan dari Direktori Putusan Mahkamah Agung Republik Indonesia dan disusun untuk keperluan pembelajaran serta penelitian Temu Kembali Informasi (TKI/Information Retrieval).

## Tujuan

1. Mengakuisisi dokumen putusan pengadilan dari sumber publik.
2. Menyusun kumpulan dokumen hukum yang terstruktur.
3. Menyediakan metadata ringkas berupa nomor putusan, lembaga peradilan, barang bukti, dan amar putusan.
4. Menyiapkan dataset sebagai bahan eksplorasi/pengembangan sistem temu kembali informasi pada domain hukum.

## Sumber Data

* Direktori Putusan Mahkamah Agung Republik Indonesia: https://putusan3.mahkamahagung.go.id/direktori.html
* Pengadilan: Pengadilan Negeri Bangkalan (PN Bkl)
* Klasifikasi: Pidana Khusus – Narkotika dan Psikotropika
* Tahun nomor perkara: 2024 dan 2025 (masih dalam rentang rekomendasi 2023–2025 pada instruksi tugas)

## Kriteria Seleksi

1. Nomor putusan menunjukkan perkara `Pid.Sus` pada Pengadilan Negeri Bangkalan.
2. Isi dokumen memuat perkara yang berkaitan dengan narkotika, antara lain narkotika golongan I, sabu/metamfetamina, atau penyalahgunaan narkotika.
3. Dokumen memiliki bagian amar putusan dan penetapan barang bukti yang dapat dibaca.
4. Dipilih 50 dokumen unik, dengan distribusi 25 dokumen bernomor perkara tahun 2024 dan 25 dokumen bernomor perkara tahun 2025.
5. File duplikat identik dihapus agar satu putusan tidak dihitung lebih dari satu kali.
6. Satu PDF hasil pindai tanpa lapisan teks tidak dimasukkan ke dalam 50 dokumen utama agar format dokumen yang dipilih konsisten dan metadata dapat diekstrak secara lebih andal.

## Status Berkekuatan Hukum Tetap (BHT)

Status BHT tidak dapat dipastikan hanya dari isi PDF putusan. Status tersebut harus diperiksa secara terpisah melalui Sistem Informasi Penelusuran Perkara (SIPP) Pengadilan Negeri Bangkalan: https://sipp.pn-bangkalan.go.id/index.php/detil\_perkara

Tim pengumpul menyatakan telah melakukan pemeriksaan status perkara melalui SIPP pada tahap pengumpulan. Untuk menjaga ketepatan data, status setiap nomor perkara tetap perlu dicocokkan kembali dengan SIPP pada tanggal pemeriksaan terakhir sebelum dataset diserahkan. Simpan tangkapan layar atau catatan pemeriksaan sebagai bukti verifikasi. 

## Struktur Repository

```text
.
├── Dataset
│   ├── Narkotika.zip
│   └── Overview
│       └── Overview.xlsx
└── README.md
```

## Isi Dataset

* `Dataset/Narkotika.zip`: arsip berisi 50 file PDF putusan unik di dalam folder `Narkotika/`.
* `Overview/Overview.xlsx`: ringkasan 50 putusan.

  * Sheet `Overview`: lima kolom sesuai contoh tugas, yaitu No, No Putusan, Lembaga Peradilan, Barang Bukti, dan Amar Putusan.
  * Sheet `Metadata`: pemetaan nomor putusan ke nama file PDF, tahun nomor perkara, tanggal putusan, dan jumlah halaman.

## Proses Pengolahan

1. Membuka ZIP awal dan memeriksa jumlah file PDF.
2. Menghapus satu salinan PDF yang identik berdasarkan hash SHA-256.
3. Memeriksa keterbacaan teks, nomor perkara, nama pengadilan, klasifikasi, amar putusan, dan bagian barang bukti.
4. Memilih 50 dokumen dengan distribusi seimbang berdasarkan tahun nomor perkara.
5. Menormalkan nama file PDF agar mudah dicocokkan dengan nomor putusan pada Excel.
6. Menyusun ringkasan Excel berdasarkan bagian amar putusan dan barang bukti pada dokumen asli.
7. Nomor SIM/telepon/IMEI yang muncul di ringkasan barang bukti disamarkan karena tidak diperlukan untuk ringkasan dataset.

## Catatan

* Ringkasan pada Excel merupakan ekstraksi/ikhtisar dari dokumen PDF. Jika diperlukan kutipan persis, rujuk kembali PDF sumber.
* Nama terdakwa tidak dibuat sebagai kolom tersendiri karena format tabel tugas tidak meminta kolom tersebut.
* Untuk kepentingan akademik, jangan mengubah isi putusan asli. Perubahan yang dilakukan hanya pada nama file dan penyusunan metadata/ringkasan.
* Anggota kelompok:

  * Anggota 1: Fandy Rohman Sifa Aminulloh – 202310370311241
  * Anggota 2: Putra Maulana Rahardiyanto – 202310370311249

