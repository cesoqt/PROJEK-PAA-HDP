# README - Fitur Penentuan Titik Manual dan Otomatis

## Deskripsi

Fitur penentuan titik merupakan bagian penting dalam sistem pencarian rute karena digunakan untuk menentukan lokasi awal (start) dan lokasi tujuan (goal) sebelum algoritma Dijkstra melakukan proses pencarian jalur terpendek.

Pada sistem ini tersedia dua metode penentuan titik, yaitu metode manual dan metode otomatis. Kedua metode tersebut dirancang untuk memberikan fleksibilitas kepada pengguna dalam menentukan lokasi awal dan tujuan sesuai kebutuhan.

---

## Penentuan Titik Manual

### Tujuan

Metode manual memungkinkan pengguna memilih sendiri lokasi awal dan tujuan secara langsung pada peta.

### Cara Kerja

Pengguna memilih tombol **Pilih Awal** atau **Pilih Tujuan**, kemudian mengklik lokasi yang diinginkan pada peta. Sistem akan membaca posisi klik dan secara otomatis mencari ruas jalan terdekat dari lokasi tersebut.

Setelah jalan terdekat ditemukan, koordinat titik akan disimpan sebagai titik awal atau titik tujuan sesuai mode yang sedang aktif.

### Keunggulan

- Pengguna bebas menentukan lokasi sesuai kebutuhan.
- Titik selalu berada pada jaringan jalan yang valid.
- Hasil pencarian rute menjadi lebih akurat.
- Mudah digunakan dalam simulasi pencarian rute tertentu.

---

## Penentuan Titik Otomatis (Acak)

### Tujuan

Metode otomatis digunakan untuk mempercepat proses pengujian sistem tanpa harus memilih titik secara manual.

### Cara Kerja

Sistem mengambil seluruh node jalan yang tersedia pada peta kemudian memilih titik awal dan titik tujuan secara acak. Untuk menghasilkan rute yang lebih representatif, sistem memastikan bahwa jarak antara titik awal dan tujuan tidak terlalu dekat.

Jika jarak yang diperoleh masih terlalu pendek, sistem akan mencari kandidat tujuan lain hingga ditemukan lokasi yang memenuhi syarat.

### Keunggulan

- Mempercepat proses simulasi.
- Menghasilkan variasi rute yang berbeda pada setiap percobaan.
- Mempermudah pengujian algoritma Dijkstra.
- Tidak memerlukan interaksi pengguna.

---

## Perbandingan Metode

| Aspek               | Manual            | Otomatis            |
| ------------------- | ----------------- | ------------------- |
| Pemilihan Lokasi    | Dipilih pengguna  | Dipilih sistem      |
| Fleksibilitas       | Tinggi            | Sedang              |
| Kecepatan Pengujian | Lebih lambat      | Lebih cepat         |
| Cocok Untuk         | Simulasi tertentu | Pengujian algoritma |
| Interaksi Pengguna  | Diperlukan        | Tidak diperlukan    |

---

## Hasil Implementasi

Fitur penentuan titik manual dan otomatis berhasil diintegrasikan dengan sistem pencarian rute. Titik yang dihasilkan dapat digunakan sebagai input algoritma Dijkstra untuk menemukan jalur terpendek pada peta kota 2D.

Metode manual memberikan kebebasan kepada pengguna dalam menentukan lokasi, sedangkan metode otomatis mempercepat proses pengujian dengan menghasilkan titik secara acak. Kedua metode mampu menghasilkan titik yang valid sehingga proses pencarian rute dapat berjalan dengan baik.

---

## Kesimpulan

Pengembangan fitur penentuan titik manual dan otomatis berhasil meningkatkan fleksibilitas serta kemudahan penggunaan sistem. Metode manual cocok digunakan ketika pengguna ingin menentukan lokasi secara spesifik, sedangkan metode otomatis sangat membantu dalam proses simulasi dan pengujian algoritma. Kedua metode tersebut menjadi tahap awal yang penting sebelum algoritma Dijkstra melakukan pencarian rute terpendek.
