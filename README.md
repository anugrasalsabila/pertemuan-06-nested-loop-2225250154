# Pertemuan 06 Nested Loop Python

Nama: Intan Anugra Salsabila  
NIM: 2225250154  
Kelas: 3F

## Tujuan

Menggunakan nested loop, pola, akumulasi, dan pencacahan.

## Cara Menjalankan

```bash
python3 tugas/tabel_perkalian_dan_statistik.py
```

## Algoritma Tugas 3

1. Meminta input bilangan bulat positif `n`.
2. Memvalidasi input menggunakan `while` sampai nilai `n` valid.
3. Menginisialisasi `total_semua = 0` dan `count_genap = 0`.
4. Mengulangi loop luar untuk nilai `i` dari 1 sampai `n`.
5. Menginisialisasi `total_baris = 0` pada setiap baris.
6. Mengulangi loop dalam untuk nilai `j` dari 1 sampai `n`.
7. Menghitung `hasil = i * j`.
8. Menambahkan `hasil` ke `total_baris` dan `total_semua`.
9. Jika `hasil % 2 == 0`, menambah `count_genap` sebanyak 1.
10. Menampilkan jumlah setiap baris setelah loop dalam selesai.
11. Menampilkan total keseluruhan dan banyak hasil genap setelah kedua loop selesai.

**Peran setiap bagian program:**

- **Loop luar (`i`):** Mengatur baris tabel perkalian.
- **Loop dalam (`j`):** Mengatur kolom tabel perkalian.
- **Akumulator `total_baris`:** Menghitung jumlah hasil perkalian pada setiap baris.
- **Akumulator `total_semua`:** Menghitung jumlah seluruh hasil perkalian.
- **Counter `count_genap`:** Menghitung banyak hasil perkalian yang genap.
- **Kondisi:** Memeriksa apakah hasil perkalian genap.
- **Validasi:** Memastikan nilai `n` merupakan bilangan bulat positif.

## Hasil Pengujian

| Input | Hasil yang diharapkan | Keluaran aktual | Status |
|---|---|---|---|
| `n = 1` | Pasangan = 1, total = 1, genap = 0 | Pasangan = 1, total = 1, genap = 0 | Berhasil |
| `n = 2` | Pasangan = 4, total = 9, genap = 3 | Pasangan = 4, total = 9, genap = 3 | Berhasil |
| `n = 3` | Pasangan = 9, total = 36, genap = 5 | Pasangan = 9, total = 36, genap = 5 | Berhasil |

### Keluaran Aktual

**Input `n = 1`**

```text
Tabel Perkalian dan Statistik
n: 1
1
Jumlah baris 1: 1
Jumlah pasangan: 1
Total keseluruhan: 1
Banyak hasil genap: 0
```

**Input `n = 2`**

```text
Tabel Perkalian dan Statistik
n: 2
1  2
Jumlah baris 1: 3
2  4
Jumlah baris 2: 6
Jumlah pasangan: 4
Total keseluruhan: 9
Banyak hasil genap: 3
```

**Input `n = 3`**

```text
Tabel Perkalian dan Statistik
n: 3
1  2  3
Jumlah baris 1: 6
2  4  6
Jumlah baris 2: 12
3  6  9
Jumlah baris 3: 18
Jumlah pasangan: 9
Total keseluruhan: 36
Banyak hasil genap: 5
```

Hasil pengujian sesuai dengan test case yang ditentukan.

## Analisis Efisiensi

Loop luar berjalan sebanyak `n` kali dan loop dalam berjalan sebanyak `n` kali untuk setiap iterasi loop luar.

Jumlah eksekusi pernyataan `hasil = i * j` adalah:

```python
n * n
```

Dengan demikian, jumlah eksekusi adalah `n²` kali.

Contoh:
- `n = 1`: 1 kali.
- `n = 2`: 4 kali.
- `n = 3`: 9 kali.
- `n = 10`: 100 kali.

Kompleksitas waktu program adalah **O(n²)** karena menggunakan dua perulangan bersarang.

## Refleksi

Salah satu kesalahan dalam penggunaan nested loop adalah menempatkan inisialisasi akumulator pada posisi yang tidak tepat. Jika `total_baris` tidak direset pada setiap iterasi loop luar, hasil penjumlahan baris sebelumnya akan ikut terbawa ke baris berikutnya.

Cara memperbaikinya adalah menempatkan `total_baris = 0` di dalam loop luar dan sebelum loop dalam. Sementara itu, `total_semua` dan `count_genap` diinisialisasi sebelum loop luar agar nilainya terus bertambah sampai seluruh perulangan selesai.

### Refleksi Teknis

**1. Mengapa `total_baris` direset di setiap iterasi loop luar?**

Karena `total_baris` hanya digunakan untuk menjumlahkan hasil perkalian pada satu baris. Ketika berpindah ke baris baru, nilainya harus kembali menjadi 0 agar tidak tercampur dengan hasil baris sebelumnya.

**2. Mengapa `total_semua` tidak direset di setiap baris?**

Karena `total_semua` digunakan untuk menjumlahkan seluruh hasil perkalian dari semua baris. Jika direset setiap baris, jumlah yang telah dikumpulkan sebelumnya akan hilang.

**3. Untuk `n`, berapa kali pernyataan `hasil = i * j` dieksekusi?**

Pernyataan tersebut dieksekusi sebanyak `n²` kali karena loop luar berjalan `n` kali dan loop dalam berjalan `n` kali pada setiap iterasi loop luar.

**4. Bagaimana Anda membuktikan `count_genap` benar?**

Setiap hasil perkalian diperiksa menggunakan kondisi berikut:

```python
if hasil % 2 == 0:
    count_genap += 1
```

Counter hanya bertambah jika hasil perkalian habis dibagi 2. Untuk `n = 3`, hasil genapnya adalah 2, 2, 4, 6, dan 6. Jadi, `count_genap = 5`.

**5. Apa bagian program yang akan paling banyak melakukan operasi ketika `n` membesar?**

Loop dalam merupakan bagian yang paling banyak melakukan operasi karena dijalankan sebanyak `n²` kali. Di bagian ini, program menghitung hasil perkalian, memperbarui akumulator, dan memeriksa kondisi bilangan genap.

## Kesimpulan

Nested loop dapat digunakan untuk membuat tabel perkalian dan memproses setiap pasangan baris dan kolom. Akumulator digunakan untuk menghitung jumlah, sedangkan counter digunakan untuk menghitung banyaknya hasil yang memenuhi kondisi tertentu.

Melalui tugas ini, saya memahami pentingnya penempatan variabel, penggunaan kondisi, validasi input, dan pengujian program agar hasilnya sesuai dengan perhitungan manual.