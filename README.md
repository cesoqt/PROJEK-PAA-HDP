# PROJEK PAA - Pencarian Rute Terpendek Menggunakan Algoritma Dijkstra

Project ini dibuat untuk memenuhi tugas mata kuliah **Perancangan dan Analisis Algoritma (PAA)**. Project ini berfokus pada simulasi pencarian rute terpendek pada peta kota berbasis graph menggunakan **Algoritma Dijkstra**.

Pada project ini, peta kota dibentuk dari kumpulan titik jalan atau persimpangan yang disebut **node**, serta ruas jalan penghubung antar titik yang disebut **edge**. Data node dan edge tersebut digunakan sebagai graph untuk proses pencarian rute. Algoritma Dijkstra digunakan untuk mencari jalur terpendek dari titik awal menuju titik tujuan berdasarkan bobot atau jarak antar titik.

Selain pencarian rute, project ini juga memiliki fitur visualisasi peta, animasi kendaraan, pembentukan jalan, serta analisis kompleksitas algoritma untuk mengetahui performa pencarian rute berdasarkan jumlah node dan edge.

---

## Daftar Isi

1. [Deskripsi Project](#deskripsi-project)
2. [Tujuan Project](#tujuan-project)
3. [Fitur Utama](#fitur-utama)
4. [Konsep Dasar Project](#konsep-dasar-project)
5. [Struktur Folder](#struktur-folder)
6. [Penjelasan Folder dan File](#penjelasan-folder-dan-file)
7. [Algoritma Dijkstra](#algoritma-dijkstra)
8. [Alur Kerja Sistem](#alur-kerja-sistem)
9. [Analisis Kompleksitas](#analisis-kompleksitas)
10. [File Analisis Kompleksitas](#file-analisis-kompleksitas)
11. [Cara Menjalankan Project](#cara-menjalankan-project)
12. [Cara Menjalankan Analisis Kompleksitas](#cara-menjalankan-analisis-kompleksitas)
13. [Contoh Output Analisis](#contoh-output-analisis)
14. [Pembagian Modul Project](#pembagian-modul-project)
15. [Kesimpulan](#kesimpulan)

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

## Struktur Folder

Struktur umum project:

```text
PROJEK-PAA-HDP/
│
├── algo/
│   ├── dijkstra.py
│   └── pencarian.py
│
├── map/
│   ├── grid/
│   │   └── grid_kota.py
│   ├── roads.py
│   └── render/
│
├── ui/
│   └── app.py
│
├── analisis_kompleksitas.py
│
└── README.md
```

Catatan: struktur folder dapat berbeda sedikit tergantung versi project, tetapi secara umum project memiliki bagian algoritma, peta, tampilan, dan analisis kompleksitas.

---

## Penjelasan Folder dan File

### 1. Folder `algo/`

Folder ini berisi file yang berhubungan dengan algoritma pencarian rute.

#### `dijkstra.py`

File ini berisi implementasi utama algoritma Dijkstra. Fungsi di dalam file ini digunakan untuk mencari rute terpendek berdasarkan node dan edge yang sudah terbentuk.

Secara umum, file ini bertugas untuk:

1. Membuat graph dari data node dan edge.
2. Menentukan node awal dan node tujuan.
3. Menghitung jarak antar node.
4. Menjalankan proses pencarian rute.
5. Menghasilkan rute terpendek.

#### `pencarian.py`

File ini berisi fungsi pendukung untuk proses pencarian. File ini dapat digunakan untuk menghubungkan proses pencarian rute dengan bagian tampilan atau sistem utama.

---

### 2. Folder `map/`

Folder ini berisi file yang berhubungan dengan pembuatan dan pengolahan peta.

Folder ini bertugas untuk:

1. Membentuk struktur peta kota.
2. Membuat jalan.
3. Membuat variasi bentuk jalan.
4. Menghasilkan node dan edge.
5. Menyediakan data graph untuk algoritma Dijkstra.

#### `grid/grid_kota.py`

File ini digunakan untuk membangun peta kota. Di dalam file ini terdapat proses pembentukan grid, jalan, node, dan edge.

Contoh penggunaan:

```python
grid = GridKota()
grid.bangun(seed=seed, noise=noise, rapat=rapat)
nodes, edges = grid.get_vector_dijkstra()
```

Penjelasan:

1. `GridKota()` digunakan untuk membuat objek peta kota.
2. `bangun()` digunakan untuk membangun peta berdasarkan parameter tertentu.
3. `get_vector_dijkstra()` digunakan untuk mengambil node dan edge yang akan dipakai oleh Dijkstra.

#### `roads.py`

File ini berisi proses pembentukan jalan. Jalan yang dibuat dapat berupa jalan luar, jalan dalam, jalan horizontal, jalan vertikal, atau jalan penghubung.

#### Folder `render/`

Folder ini berhubungan dengan proses visualisasi atau tampilan peta.

---

### 3. Folder `ui/`

Folder ini berisi file yang berhubungan dengan tampilan program dan interaksi pengguna.

#### `app.py`

File ini biasanya menjadi bagian utama untuk menjalankan tampilan aplikasi. Di dalam file ini terdapat pengaturan tampilan peta, rute, kendaraan, tombol, serta game loop atau animasi.

Secara umum, file ini bertugas untuk:

1. Menampilkan peta.
2. Menampilkan titik awal dan tujuan.
3. Menampilkan rute hasil Dijkstra.
4. Menjalankan animasi kendaraan.
5. Mengatur tombol start, stop, dan reset.
6. Menghubungkan tampilan dengan algoritma pencarian rute.

---

### 4. File `analisis_kompleksitas.py`

File ini digunakan untuk melakukan analisis kompleksitas algoritma Dijkstra. File ini menjalankan pengujian dengan beberapa seed peta, lalu menampilkan jumlah node, jumlah edge, estimasi kompleksitas, total jarak, jumlah titik rute, dan waktu eksekusi.

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
Bangun peta kota
  |
  v
Bentuk jalan
  |
  v
Konversi jalan menjadi node dan edge
  |
  v
Tentukan titik awal dan titik tujuan
  |
  v
Jalankan algoritma Dijkstra
  |
  v
Dapatkan rute terpendek
  |
  v
Tampilkan rute pada peta
  |
  v
Gerakkan kendaraan mengikuti rute
  |
  v
Selesai
```

Penjelasan alur:

1. Sistem membangun peta kota terlebih dahulu.
2. Jalan pada peta dibuat dan divariasikan.
3. Jalan dikonversi menjadi node dan edge.
4. Pengguna atau sistem menentukan titik awal dan tujuan.
5. Algoritma Dijkstra mencari rute terpendek.
6. Rute hasil pencarian divisualisasikan pada peta.
7. Kendaraan bergerak mengikuti rute tersebut.

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

### Fungsi Uji Satu Seed

```python
def uji_satu_seed(seed=42, noise=40, rapat=168):
    grid = GridKota()
    grid.bangun(seed=seed, noise=noise, rapat=rapat)

    nodes, edges = grid.get_vector_dijkstra()

    if len(nodes) < 2:
        return None
```

Fungsi ini digunakan untuk melakukan pengujian pada satu bentuk peta berdasarkan seed tertentu.

Penjelasan:

1. Program membuat objek `GridKota`.
2. Program membangun peta menggunakan `grid.bangun()`.
3. Program mengambil node dan edge menggunakan `get_vector_dijkstra()`.
4. Jika node kurang dari 2, maka pengujian tidak bisa dilakukan.

### Pemilihan Titik Awal dan Tujuan

```python
awal = random.choice(nodes)
tujuan = random.choice(nodes)

for _ in range(300):
    kandidat = random.choice(nodes)
    jarak = math.hypot(kandidat[1] - awal[1], kandidat[2] - awal[2])
    if jarak > 550:
        tujuan = kandidat
        break
```

Bagian ini digunakan untuk memilih titik awal dan titik tujuan secara acak.

Penjelasan:

1. `awal` dipilih secara acak dari daftar node.
2. `tujuan` juga dipilih secara acak dari daftar node.
3. Program mencoba mencari tujuan yang cukup jauh dari titik awal.
4. Jarak dihitung menggunakan `math.hypot()`.
5. Jika jaraknya lebih dari 550 piksel, titik tersebut digunakan sebagai tujuan.
6. Perulangan dibatasi sebanyak 300 kali agar proses tidak berjalan terus-menerus.

Tujuan dari proses ini adalah agar rute yang diuji tidak terlalu pendek. Jika rute terlalu pendek, maka waktu eksekusi bisa sangat kecil dan kurang mewakili performa algoritma.

### Menjalankan Dijkstra dan Menghitung Waktu

```python
start_xy = (awal[1], awal[2])
goal_xy = (tujuan[1], tujuan[2])

t0 = time.perf_counter()
rute, total_jarak = cari_rute_koordinat(nodes, edges, start_xy, goal_xy)
t1 = time.perf_counter()
```

Bagian ini adalah inti dari pengujian.

Penjelasan:

1. `start_xy` menyimpan koordinat titik awal.
2. `goal_xy` menyimpan koordinat titik tujuan.
3. `t0` menyimpan waktu sebelum Dijkstra dijalankan.
4. Fungsi `cari_rute_koordinat()` menjalankan pencarian rute.
5. `t1` menyimpan waktu setelah Dijkstra selesai.
6. Selisih `t1 - t0` digunakan untuk menghitung waktu eksekusi.

Waktu eksekusi dihitung dalam milidetik dengan rumus:

```python
(t1 - t0) * 1000
```

### Menyimpan Hasil Pengujian

```python
v = len(nodes)
e = len(edges)

return {
    "seed": seed,
    "node_v": v,
    "edge_e": e,
    "estimasi_big_o": estimasi_kompleksitas(v, e),
    "jumlah_titik_rute": len(rute),
    "total_jarak": total_jarak,
    "waktu_ms": (t1 - t0) * 1000,
}
```

Bagian ini menyimpan hasil pengujian dalam bentuk dictionary.

Data yang disimpan adalah:

1. `seed`, yaitu variasi peta yang digunakan.
2. `node_v`, yaitu jumlah node.
3. `edge_e`, yaitu jumlah edge.
4. `estimasi_big_o`, yaitu estimasi kompleksitas relatif.
5. `jumlah_titik_rute`, yaitu jumlah titik pada rute hasil Dijkstra.
6. `total_jarak`, yaitu total jarak rute.
7. `waktu_ms`, yaitu waktu eksekusi dalam milidetik.

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

## Pembagian Modul Project

Project ini dapat dibagi menjadi beberapa modul utama:

### 1. Modul Konstruksi Peta

Modul ini bertugas membangun peta kota, membuat jalan, mengatur variasi bentuk jalan, dan menghasilkan struktur jalan yang dapat digunakan oleh sistem.

### 2. Modul Konversi Graph

Modul ini bertugas mengubah jalan menjadi node dan edge. Data node dan edge tersebut menjadi input utama untuk algoritma Dijkstra.

### 3. Modul Algoritma Dijkstra

Modul ini bertugas mencari rute terpendek dari titik awal menuju titik tujuan berdasarkan graph yang sudah terbentuk.

### 4. Modul Visualisasi

Modul ini bertugas menampilkan peta, node, edge, rute, dan kendaraan pada tampilan program.

### 5. Modul Animasi Kendaraan

Modul ini bertugas menggerakkan kendaraan mengikuti rute hasil pencarian. Modul ini juga mengatur pergerakan agar kendaraan terlihat berjalan mengikuti jalur.

### 6. Modul Analisis Kompleksitas

Modul ini bertugas menghitung estimasi kompleksitas dan waktu eksekusi algoritma Dijkstra. Modul ini digunakan untuk membuktikan efisiensi algoritma berdasarkan jumlah node dan edge.

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

Secara keseluruhan, project ini menunjukkan hubungan antara pembentukan peta, graph, algoritma Dijkstra, visualisasi rute, animasi kendaraan, dan analisis kompleksitas dalam satu sistem pencarian rute terpendek.

---

## Author

Project ini dibuat untuk tugas mata kuliah **Perancangan dan Analisis Algoritma (PAA)**.

```
Nama  : Kelompok Project PAA
Topik : Pencarian Rute Terpendek Menggunakan Algoritma Dijkstra
```
