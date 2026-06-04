# PROJEK PAA - Pencarian Rute Terpendek Menggunakan Algoritma Dijkstra

Project ini dibuat untuk memenuhi tugas mata kuliah **Perancangan dan Analisis Algoritma (PAA)**. Project ini berfokus pada simulasi pencarian rute terpendek pada peta kota berbasis graph menggunakan **Algoritma Dijkstra**.

Pada project ini, peta kota dibentuk dari kumpulan titik jalan atau persimpangan yang disebut **node**, serta ruas jalan penghubung antar titik yang disebut **edge**. Data node dan edge tersebut digunakan sebagai graph untuk proses pencarian rute. Algoritma Dijkstra digunakan untuk mencari jalur terpendek dari titik awal menuju titik tujuan berdasarkan bobot atau jarak antar titik.

Selain pencarian rute, project ini juga memiliki fitur visualisasi peta, animasi kendaraan, konstruksi peta, serta analisis kompleksitas algoritma untuk mengetahui performa pencarian rute berdasarkan jumlah node dan edge.

---

## Daftar Isi

1. [Deskripsi Project](#deskripsi-project)
2. [Tujuan Project](#tujuan-project)
3. [Fitur Utama](#fitur-utama)
4. [Konsep Dasar Project](#konsep-dasar-project)
5. [Struktur Project Berdasarkan Modul](#struktur-project-berdasarkan-modul)
6. [Penjelasan Setiap Modul](#penjelasan-setiap-modul)
7. [Algoritma Dijkstra](#algoritma-dijkstra)
8. [Alur Kerja Sistem](#alur-kerja-sistem)
9. [Analisis Kompleksitas](#analisis-kompleksitas)
10. [File Analisis Kompleksitas](#file-analisis-kompleksitas)
11. [Cara Menjalankan Project](#cara-menjalankan-project)
12. [Cara Menjalankan Analisis Kompleksitas](#cara-menjalankan-analisis-kompleksitas)
13. [Contoh Output Analisis](#contoh-output-analisis)
14. [Kesimpulan](#kesimpulan)

---

## Deskripsi Project

Project ini merupakan simulasi pencarian rute terpendek pada peta kota. Peta kota pada project ini dibangun menggunakan struktur jalan yang kemudian diubah menjadi graph. Graph tersebut terdiri dari node dan edge.

Node merepresentasikan titik jalan, titik persimpangan, atau titik penting pada peta. Edge merepresentasikan ruas jalan yang menghubungkan satu node dengan node lainnya. Setiap edge memiliki bobot yang menggambarkan jarak antar titik.

Setelah graph terbentuk, algoritma Dijkstra digunakan untuk mencari rute terpendek dari titik awal menuju titik tujuan. Hasil pencarian rute kemudian divisualisasikan pada tampilan program, sehingga pengguna dapat melihat jalur yang dipilih oleh sistem.

Project ini juga menyediakan file khusus untuk melakukan analisis kompleksitas. Analisis tersebut digunakan untuk mengetahui bagaimana jumlah node dan edge memengaruhi waktu eksekusi algoritma Dijkstra.

---

## Tujuan Project

Tujuan dari project ini adalah:

1. Membangun simulasi peta kota berbasis graph.
2. Mengubah data jalan menjadi node dan edge.
3. Mengimplementasikan algoritma Dijkstra untuk mencari rute terpendek.
4. Menampilkan hasil pencarian rute secara visual.
5. Membuat animasi kendaraan yang bergerak mengikuti rute.
6. Menguji performa pencarian rute menggunakan beberapa variasi peta.
7. Menganalisis kompleksitas algoritma Dijkstra.
8. Mengetahui hubungan antara jumlah node, edge, dan waktu eksekusi.
9. Membuktikan bahwa Dijkstra lebih efisien dibandingkan pencarian brute force.

---

## Fitur Utama

Fitur utama dalam project ini adalah:

1. Pembuatan peta kota secara otomatis.
2. Pembentukan jalan luar dan jalan dalam.
3. Pembentukan node dari titik-titik jalan.
4. Pembentukan edge dari ruas jalan.
5. Konversi peta menjadi graph.
6. Penentuan titik awal dan titik tujuan.
7. Pencarian rute terpendek menggunakan Dijkstra.
8. Visualisasi rute pada peta.
9. Animasi kendaraan yang mengikuti jalur.
10. Pengujian algoritma berdasarkan beberapa seed peta.
11. Perhitungan estimasi kompleksitas Big-O.
12. Pengukuran waktu eksekusi algoritma dalam milidetik.

---

## Konsep Dasar Project

Project ini menggunakan konsep graph untuk merepresentasikan peta kota.

### 1. Node

Node adalah titik yang terdapat pada peta. Dalam project ini, node dapat berupa titik jalan, persimpangan, titik awal, titik tujuan, atau titik yang dilalui kendaraan.

Contoh node dalam bentuk koordinat:

```text
Node 1 = (x1, y1)
Node 2 = (x2, y2)
Node 3 = (x3, y3)
```

### 2. Edge

Edge adalah hubungan antara dua node. Edge merepresentasikan ruas jalan.

Contoh edge:

```text
A -> B
B -> C
C -> D
```

### 3. Bobot

Bobot adalah nilai jarak pada edge. Bobot digunakan oleh algoritma Dijkstra untuk menentukan jalur yang paling pendek.

Contoh:

```text
A -> B = 10
B -> C = 15
A -> C = 30
```

Dari contoh tersebut, jalur dari A ke C yang lebih pendek adalah:

```text
A -> B -> C
```

Karena total jaraknya:

```text
10 + 15 = 25
```

Sedangkan jalur langsung:

```text
A -> C = 30
```

---

## Struktur Project Berdasarkan Modul

Struktur project dibuat berdasarkan modul agar setiap bagian program memiliki tugas yang jelas.

````text
PROJEK-PAA-HDP/
│
├── 01_MODUL_KONSTRUKSI_PETA/
│   ├── map/
│   │   ├── grid/
│   │   │   └── grid_kota.py
│   │   ├── roads.py
│   │   └── render/
│   └── README_MODUL.md
│
├── 02_MODUL_VISUALISASI_KENDARAAN/
│   ├── ui/
│   │   └── app.py
│   ├── map/
│   │   ├── kamera.py
│   │   └── render/
│   └── README_MODUL.md
│
├── 03_MODUL_ALGORITMA_DIJKSTRA/
│   ├── algo/
│   │   ├── dijkstra.py
│   │   └── pencarian.py
│   └── README_MODUL.md
│
├── 04_MODUL_ANALISIS_KOMPLEKSITAS/
│   ├── analisis_kompleksitas.py
│   └── README_MODUL.md
│
├── main.py
└── README.md


## Penjelasan Setiap Modul

### 1. Modul Konstruksi Peta

Modul konstruksi peta bertugas membangun peta kota yang digunakan sebagai dasar pencarian rute. Pada modul ini, jalan dibentuk menjadi beberapa bagian seperti jalan luar, jalan dalam, jalan horizontal, jalan vertikal, dan jalan penghubung.

Tugas utama modul konstruksi peta:

1. Membuat struktur peta kota.
2. Membentuk jalan luar atau ring road.
3. Membentuk jalan bagian dalam.
4. Memberikan variasi bentuk jalan menggunakan noise.
5. Membuat jalan horizontal dan vertikal.
6. Melakukan clipping agar jalan tetap berada pada area yang valid.
7. Membentuk jalan penghubung.
8. Menghasilkan data jalan untuk dikonversi menjadi graph.

Contoh bagian kode yang berhubungan dengan modul konstruksi peta:

```python
grid = GridKota()
grid.bangun(seed=seed, noise=noise, rapat=rapat)
````

Penjelasan:

1. `GridKota()` digunakan untuk membuat objek peta.
2. `bangun()` digunakan untuk membangun peta berdasarkan parameter tertentu.
3. `seed` digunakan agar bentuk peta dapat diuji dengan variasi berbeda.
4. `noise` digunakan untuk membuat bentuk jalan lebih bervariasi.
5. `rapat` digunakan untuk mengatur kerapatan jalan.

---

### 2. Modul Konversi Graph

Modul konversi graph bertugas mengubah struktur jalan menjadi data node dan edge. Data inilah yang menjadi input utama bagi algoritma Dijkstra.

Tugas utama modul konversi graph:

1. Mengambil titik-titik jalan dari peta.
2. Mengubah titik jalan menjadi node.
3. Menghubungkan node dengan edge.
4. Menghitung bobot edge berdasarkan jarak antar node.
5. Menyediakan data graph untuk algoritma Dijkstra.

Contoh kode:

```python
nodes, edges = grid.get_vector_dijkstra()
```

Penjelasan:

1. `nodes` berisi daftar titik jalan atau persimpangan.
2. `edges` berisi daftar ruas jalan yang menghubungkan antar node.
3. Data ini kemudian digunakan sebagai input pencarian rute.

---

### 3. Modul Algoritma Dijkstra

Modul algoritma Dijkstra bertugas mencari rute terpendek dari titik awal menuju titik tujuan berdasarkan graph yang sudah terbentuk.

Tugas utama modul Dijkstra:

1. Menerima input node dan edge.
2. Membentuk graph dari data tersebut.
3. Menentukan node awal terdekat.
4. Menentukan node tujuan terdekat.
5. Menghitung jarak terpendek.
6. Menyimpan rute yang dilalui.
7. Mengembalikan hasil rute dan total jarak.

Contoh pemanggilan fungsi Dijkstra:

```python
rute, total_jarak = cari_rute_koordinat(nodes, edges, start_xy, goal_xy)
```

Penjelasan:

1. `nodes` adalah daftar titik jalan.
2. `edges` adalah daftar ruas jalan.
3. `start_xy` adalah koordinat awal.
4. `goal_xy` adalah koordinat tujuan.
5. `rute` adalah hasil jalur yang ditemukan.
6. `total_jarak` adalah total jarak dari rute tersebut.

---

### 4. Modul Visualisasi

Modul visualisasi bertugas menampilkan hasil project secara visual kepada pengguna. Modul ini biasanya berada pada bagian `ui/app.py`.

Tugas utama modul visualisasi:

1. Menampilkan peta kota.
2. Menampilkan node dan edge.
3. Menampilkan titik awal dan tujuan.
4. Menampilkan rute hasil Dijkstra.
5. Menampilkan kendaraan.
6. Mengatur tampilan program agar mudah digunakan.

Contoh fungsi modul visualisasi:

```text
Menampilkan peta -> memilih titik awal dan tujuan -> menampilkan rute -> menjalankan animasi
```

---

### 5. Modul Animasi Kendaraan

Modul animasi kendaraan bertugas menggerakkan kendaraan mengikuti rute hasil pencarian Dijkstra. Kendaraan bergerak dari titik awal menuju titik tujuan berdasarkan daftar titik rute.

Tugas utama modul animasi kendaraan:

1. Mengambil rute hasil Dijkstra.
2. Mengatur posisi kendaraan.
3. Menghitung arah kendaraan.
4. Mengatur rotasi kendaraan saat berbelok.
5. Menjalankan game loop animasi.
6. Mengatur start, pause, stop, dan reset animasi.

Contoh alur animasi:

```text
Ambil rute -> kendaraan mulai bergerak -> mengikuti titik rute -> berbelok -> sampai tujuan
```

---

### 6. Modul Analisis Kompleksitas

Modul analisis kompleksitas bertugas menguji performa algoritma Dijkstra. Modul ini menghitung jumlah node, jumlah edge, estimasi kompleksitas, total jarak, jumlah titik rute, dan waktu eksekusi.

Tugas utama modul analisis kompleksitas:

1. Membangun peta berdasarkan seed.
2. Mengambil node dan edge dari peta.
3. Memilih titik awal dan tujuan.
4. Menjalankan algoritma Dijkstra.
5. Menghitung estimasi kompleksitas.
6. Mengukur waktu eksekusi.
7. Menampilkan hasil analisis.

Contoh kode:

```python
def estimasi_kompleksitas(v, e):
    if v <= 1:
        return 0
    return int((v + e) * math.log2(v))
```

Rumus yang digunakan:

```text
O((V + E) log V)
```

Keterangan:

```text
V = jumlah node
E = jumlah edge
```

---

## Algoritma Dijkstra

Algoritma Dijkstra adalah algoritma yang digunakan untuk mencari jalur terpendek dari satu node awal ke node tujuan pada graph berbobot.

Dalam project ini, graph berasal dari peta kota. Node merepresentasikan titik jalan, sedangkan edge merepresentasikan ruas jalan. Bobot pada edge merepresentasikan jarak antar node.

### Cara Kerja Dijkstra

Secara sederhana, langkah kerja algoritma Dijkstra adalah:

1. Tentukan node awal dan node tujuan.
2. Berikan nilai jarak awal sebesar 0 pada node awal.
3. Berikan nilai tak hingga pada node lainnya.
4. Pilih node dengan jarak terkecil.
5. Periksa semua node tetangga dari node tersebut.
6. Jika ditemukan jarak yang lebih pendek, perbarui nilai jaraknya.
7. Simpan node sebelumnya untuk membentuk rute akhir.
8. Ulangi proses sampai node tujuan ditemukan.
9. Bentuk rute dari node tujuan kembali ke node awal.
10. Tampilkan rute terpendek.

### Contoh Sederhana

Misalnya terdapat graph:

```text
A --5-- B --4-- C
A --12- C
```

Jika ingin mencari rute dari A ke C, maka ada dua pilihan:

```text
A -> C = 12
A -> B -> C = 5 + 4 = 9
```

Maka rute terpendek adalah:

```text
A -> B -> C
```

Karena total jaraknya adalah 9, lebih kecil dibandingkan jalur langsung A ke C yang bernilai 12.

---

## Alur Kerja Sistem

Alur kerja sistem pada project ini adalah:

```text
Mulai
  |
  v
Modul Konstruksi Peta
  |
  v
Modul Konversi Graph
  |
  v
Modul Algoritma Dijkstra
  |
  v
Modul Visualisasi Rute
  |
  v
Modul Animasi Kendaraan
  |
  v
Modul Analisis Kompleksitas
  |
  v
Selesai
```

Penjelasan alur:

1. Modul konstruksi peta membangun peta kota.
2. Modul konversi graph mengubah jalan menjadi node dan edge.
3. Modul Dijkstra mencari rute terpendek.
4. Modul visualisasi menampilkan hasil rute.
5. Modul animasi kendaraan menjalankan kendaraan mengikuti rute.
6. Modul analisis kompleksitas mengukur performa algoritma.

---

## Analisis Kompleksitas

Analisis kompleksitas digunakan untuk mengetahui seberapa efisien algoritma ketika jumlah data semakin besar.

Pada project ini, kompleksitas yang dianalisis adalah kompleksitas algoritma Dijkstra.

Rumus kompleksitas Dijkstra yang digunakan adalah:

```text
O((V + E) log V)
```

Keterangan:

```text
V = jumlah node atau titik jalan
E = jumlah edge atau ruas jalan
```

### Penjelasan Rumus

Rumus:

```text
O((V + E) log V)
```

memiliki arti bahwa waktu eksekusi algoritma dipengaruhi oleh jumlah node dan edge pada graph.

Bagian:

```text
V + E
```

menunjukkan bahwa algoritma perlu memproses node dan edge yang ada pada graph.

Bagian:

```text
log V
```

muncul karena implementasi Dijkstra biasanya menggunakan priority queue atau heap. Struktur data heap membuat proses pemilihan node dengan jarak terkecil menjadi lebih efisien.

Jika jumlah node dan edge semakin banyak, maka proses pencarian rute akan semakin berat. Namun, penggunaan priority queue membuat algoritma tetap lebih efisien dibandingkan brute force.

---

## File Analisis Kompleksitas

File `analisis_kompleksitas.py` berisi proses pengujian performa Dijkstra.

Isi utama file tersebut adalah:

1. Menghitung estimasi kompleksitas.
2. Membangun peta berdasarkan seed.
3. Mengambil node dan edge dari peta.
4. Memilih titik awal dan tujuan.
5. Menjalankan Dijkstra.
6. Menghitung waktu eksekusi.
7. Menampilkan hasil pengujian.

### Import Library dan Modul

```python
import math
import random
import time

from algo.dijkstra import cari_rute_koordinat
from map.grid.grid_kota import GridKota
```

Penjelasan:

1. `math` digunakan untuk perhitungan matematika.
2. `random` digunakan untuk memilih titik secara acak.
3. `time` digunakan untuk menghitung waktu eksekusi.
4. `cari_rute_koordinat` digunakan untuk menjalankan Dijkstra.
5. `GridKota` digunakan untuk membangun peta kota.

### Fungsi Estimasi Kompleksitas

```python
def estimasi_kompleksitas(v, e):
    if v <= 1:
        return 0
    return int((v + e) * math.log2(v))
```

Fungsi ini digunakan untuk menghitung estimasi kompleksitas relatif berdasarkan jumlah node dan edge.

Penjelasan:

1. `v` adalah jumlah node.
2. `e` adalah jumlah edge.
3. Jika node kurang dari atau sama dengan 1, maka proses pencarian tidak dilakukan.
4. Jika node cukup, maka program menghitung estimasi dengan rumus `(v + e) * log2(v)`.

Rumus tersebut mewakili kompleksitas:

```text
O((V + E) log V)
```

---

## Cara Menjalankan Project

Pastikan Python sudah terinstall di perangkat. Setelah itu, masuk ke folder project melalui terminal.

```bash
cd PROJEK-PAA-HDP
```

Untuk menjalankan program utama:

```bash
python main.py
```

Jika program utama berada di folder `ui`, jalankan:

```bash
python ui/app.py
```

Jika menggunakan Python 3:

```bash
python3 main.py
```

atau:

```bash
python3 ui/app.py
```

---

## Cara Menjalankan Analisis Kompleksitas

Untuk menjalankan file analisis kompleksitas:

```bash
python analisis_kompleksitas.py
```

atau:

```bash
python3 analisis_kompleksitas.py
```

Setelah dijalankan, program akan menampilkan hasil analisis pencarian rute Dijkstra.

---

## Contoh Output Analisis

Contoh output yang akan muncul:

```text
========================================================================
ANALISIS KOMPLEKSITAS PENCARIAN RUTE DIJKSTRA
========================================================================
Rumus utama: O((V + E) log V)
V = jumlah node jalan
E = jumlah edge/ruas jalan
========================================================================
Seed             : 42
Node (V)          : 120
Edge (E)          : 250
Estimasi O        : 2556 operasi relatif
Jumlah titik rute : 18
Total jarak       : 785.43 px
Waktu eksekusi    : 1.2345 ms
------------------------------------------------------------------------
Kesimpulan:
Semakin besar jumlah node dan edge, proses Dijkstra semakin berat.
Namun karena memakai priority queue/heapq, kompleksitasnya tetap
lebih efisien dibanding mengecek semua kemungkinan rute secara brute force.
```

Catatan: angka pada output dapat berbeda tergantung seed, bentuk peta, jumlah node, jumlah edge, dan perangkat yang digunakan.

---

## Kesimpulan

Project ini berhasil menerapkan algoritma Dijkstra untuk mencari rute terpendek pada peta kota berbasis graph. Peta kota dibentuk dari node dan edge, kemudian digunakan sebagai input untuk proses pencarian rute.

Dijkstra bekerja dengan memilih node yang memiliki jarak terkecil, lalu memperbarui jarak ke node tetangga sampai rute terpendek ditemukan. Kompleksitas algoritma yang digunakan adalah:

```text
O((V + E) log V)
```

Dengan:

```text
V = jumlah node
E = jumlah edge
```

Berdasarkan analisis kompleksitas, semakin banyak node dan edge pada peta, maka proses pencarian rute akan semakin berat. Namun, karena Dijkstra menggunakan priority queue atau heap, algoritma tetap lebih efisien dibandingkan brute force.

Secara keseluruhan, project ini menunjukkan hubungan antara konstruksi peta, konversi graph, algoritma Dijkstra, visualisasi rute, animasi kendaraan, dan analisis kompleksitas dalam satu sistem pencarian rute terpendek.

---

## Author

Project ini dibuat untuk tugas mata kuliah **Perancangan dan Analisis Algoritma (PAA)**.

```text
Nama  : Kelompok HDP
Topik : Pencarian Rute Terpendek Menggunakan Algoritma Dijkstra
```
