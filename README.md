# Pertemuan 06 Nested Loop Python

**Nama:** Intan Anugra Salsabila  
**NIM:** 2225250154  
**Kelas:** 2F  

## Tujuan

Menggunakan nested loop, pola, akumulasi, dan pencacahan.

## Cara Menjalankan

```bash
python3 tugas/tabel_perkalian_dan_statistik.py
```

## Algoritma Tugas 3

- **Loop luar (`i`)** digunakan untuk mengatur setiap baris tabel perkalian.
- **Loop dalam (`j`)** digunakan untuk mengatur setiap kolom pada baris.
- **Akumulator `total_baris`** digunakan untuk menjumlahkan hasil perkalian pada setiap baris.
- **Akumulator `total_semua`** digunakan untuk menjumlahkan seluruh hasil perkalian.
- **Counter `count_genap`** digunakan untuk menghitung banyak hasil perkalian yang bernilai genap.
- **Counter `jumlah_pasangan`** digunakan untuk menghitung banyak pasangan `i` dan `j` yang diproses.

## Hasil Pengujian

| Input n | Jumlah Pasangan | Total Semua | Banyak Hasil Genap | Status |
|---|---:|---:|---:|---|
| 1 | 1 | 1 | 0 | Berhasil |
| 2 | 4 | 9 | 3 | Berhasil |
| 3 | 9 | 36 | 5 | Berhasil |

### Pengujian n = 1

```text
Tabel Perkalian dan Statistik
n: 1
   1
Jumlah baris 1: 1
Jumlah pasangan: 1
Total keseluruhan: 1
Banyak hasil genap: 0
```

### Pengujian n = 2

```text
Tabel Perkalian dan Statistik
n: 2
   1   2
Jumlah baris 1: 3
   2   4
Jumlah baris 2: 6
Jumlah pasangan: 4
Total keseluruhan: 9
Banyak hasil genap: 3
```

### Pengujian n = 3

```text
Tabel Perkalian dan Statistik
n: 3
   1   2   3
Jumlah baris 1: 6
   2   4   6
Jumlah baris 2: 12
   3   6   9
Jumlah baris 3: 18
Jumlah pasangan: 9
Total keseluruhan: 36
Banyak hasil genap: 5
```

## Analisis Efisiensi

Untuk input `n`, loop luar berjalan sebanyak `n` kali dan loop dalam juga berjalan sebanyak `n` kali pada setiap baris.

Jadi, badan loop dalam berjalan sebanyak:

**n × n = n² kali**

Contoh:
- n = 1 → 1 kali
- n = 2 → 4 kali
- n = 3 → 9 kali

Semakin besar nilai `n`, semakin banyak operasi yang dilakukan.

## Refleksi

Kesalahan yang dapat terjadi pada nested loop adalah salah indentasi atau menempatkan perintah di luar loop yang seharusnya masih berada di dalam loop. Kesalahan tersebut dapat menyebabkan hasil tabel atau jumlah baris menjadi tidak sesuai.

Cara memperbaikinya adalah memastikan loop dalam berada di dalam loop luar dan menggunakan indentasi yang benar.

## Refleksi Teknis

**1. Mengapa `total_baris` direset di setiap iterasi loop luar?**

Karena `total_baris` digunakan untuk menghitung jumlah pada satu baris. Setelah berpindah ke baris berikutnya, nilainya harus dimulai kembali dari 0.

**2. Mengapa `total_semua` tidak direset di setiap baris?**

Karena `total_semua` digunakan untuk menyimpan jumlah seluruh hasil perkalian dari semua baris. Jika direset setiap baris, jumlah keseluruhan tidak akan benar.

**3. Untuk n, berapa kali pernyataan `hasil = i * j` dieksekusi?**

Pernyataan tersebut dieksekusi sebanyak **n² kali**, karena terdapat nested loop dengan `n` iterasi pada loop luar dan `n` iterasi pada loop dalam.

**4. Bagaimana membuktikan `count_genap` benar?**

Setiap hasil diperiksa menggunakan kondisi:

```python
if hasil % 2 == 0:
```

Jika hasil habis dibagi 2, maka `count_genap` bertambah satu. Dengan demikian hanya hasil yang genap yang dihitung.

**5. Apa bagian program yang akan paling banyak melakukan operasi ketika n membesar?**

Bagian nested loop, terutama pernyataan `hasil = i * j`, karena jumlah eksekusinya bertambah sebesar **n²**.