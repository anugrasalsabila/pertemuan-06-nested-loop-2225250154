# Pertemuan 06 Nested Loop Python

Nama: Intan Anugra Salsabila
NIM: 2225250154
Kelas: 3F
## Tujuan
Menggunakan nested loop, pola, akumulasi, dan pencacahan.
## Cara Menjalankan
python3 tugas/tabel_perkalian_dan_statistik.py
## Algoritma Tugas 3
Tuliskan peran loop luar, loop dalam, akumulator, dan counter.
## Hasil Pengujian
Catat input, hasil yang diharapkan, keluaran aktual, dan status.
## Analisis Efisiensi
Jelaskan berapa kali badan loop dalam berjalan untuk input n.
## Refleksi
Jelaskan satu kesalahan nested loop yang ditemukan dan cara memperbaikinya.
Refleksi Teknis
• Mengapa total_baris direset di setiap iterasi loop luar?
• Mengapa total_semua tidak direset di setiap baris?
• Untuk n, berapa kali pernyataan hasil = i * j dieksekusi?
• Bagaimana Anda membuktikan count_genap benar?
• Apa bagian program yang akan paling banyak melakukan operasi ketika n membesar?      lengakpi readme tersebut dengan hassil ter,inal ini, dan arahan bapak yag ini 7 Latihan di VS Code
Simpan setiap latihan dalam folder latihan. Untuk setiap program, tuliskan komentar singkat tentang peran loop
luar, loop dalam, kondisi, akumulator atau counter, dan output. Jalankan semua test case sebelum commit.
Latihan 1 Pasangan Indeks
Buat 01_pasangan_indeks.py. Program menampilkan seluruh pasangan (i, j) untuk i = 1..3 dan j = 1..4, lalu
menampilkan banyak pasangan.
count = 0
for i in range(1, 4):
for j in range(1, 5):
print(i, j)
count += 1
print(f"Banyak pasangan = {count}")
Hasil yang diharapkan: 12 pasangan dan count = 12.
Latihan 2 Pola Segitiga
Buat 02_pola_segitiga.py. Program menerima n positif dan menghasilkan pola bintang dengan 1 simbol pada baris
pertama sampai n simbol pada baris ke-n.
n = int(input("n: "))
for i in range(1, n + 1):
for j in range(i):
print("*", end=" ")
print()
Test case: n = 1, n = 3, dan n = 5.

Algoritma dan Pemrograman | Pertemuan 06 | 10

Checklist Latihan 1 dan 2
• [ ] Loop luar dan loop dalam memiliki peran yang dapat dijelaskan.
• [ ] Indentasi benar.
• [ ] Batas range sesuai spesifikasi.
• [ ] Jumlah iterasi dapat diprediksi sebelum program dijalankan.
Latihan 3 Jumlah per Baris
Buat 03_jumlah_per_baris.py. Untuk i = 1 sampai 4 dan j = 1 sampai 3, hitung nilai i * j dan tampilkan jumlah setiap
baris.
for i in range(1, 5):
total_baris = 0
for j in range(1, 4):
total_baris += i * j
print(f"Jumlah baris {i} = {total_baris}")
i Nilai i*j Jumlah
1 1, 2, 3 6
2 2, 4, 6 12
3 3, 6, 9 18
4 4, 8, 12 24

Latihan 4 Menghitung Pasangan
Buat 04_hitung_pasangan.py. Untuk i dan j dari 1 sampai n, hitung berapa pasangan yang memenuhi i + j <= n.
n = int(input("n: "))
count = 0
for i in range(1, n + 1):
for j in range(1, n + 1):
if i + j <= n:
count += 1
print(f"Banyak pasangan = {count}")
Test case wajib: n = 2, n = 3, dan n = 5. Lakukan tracing manual untuk n = 3.
Checklist Semua Latihan
• [ ] Akumulator atau counter diinisialisasi pada lokasi yang tepat.
• [ ] Setiap kondisi diperiksa terhadap seluruh pasangan yang relevan.
• [ ] Program diuji dengan kasus kecil yang dapat dihitung manual.
• [ ] Hasil aktual sama dengan hasil manual.
• [ ] Kode dapat dijelaskan tanpa membaca baris demi baris.
8 Tugas 3: Tabel Perkalian dan Statistik
Buat program tugas/tabel_perkalian_dan_statistik.py. Program menerima bilangan bulat positif n. Program
membentuk tabel perkalian 1 sampai n, menghitung jumlah seluruh hasil perkalian, menghitung banyak hasil yang
genap, dan menentukan jumlah setiap baris.
Spesifikasi
• Baca n sebagai integer positif.

Algoritma dan Pemrograman | Pertemuan 06 | 11

• Jika n <= 0, minta n kembali sampai valid.
• Gunakan nested loop for untuk membentuk tabel n x n.
• Pada setiap pasangan, hitung hasil = i * j.
• Tampilkan nilai hasil secara teratur per baris.
• Hitung total seluruh hasil perkalian.
• Hitung banyak hasil yang genap.
• Hitung dan tampilkan jumlah setiap baris.
• Setelah tabel selesai, tampilkan total keseluruhan dan banyak hasil genap.
Algoritma
1. Baca dan validasi n.
2. Set total_semua = 0 dan count_genap = 0.
3. Ulangi i dari 1 sampai n.
4. Set total_baris = 0 untuk baris i.
5. Ulangi j dari 1 sampai n.
6. Hitung hasil = i * j.
7. Tambahkan hasil ke total_baris dan total_semua.
8. Jika hasil genap, tambah count_genap.
9. Setelah loop dalam selesai, tampilkan total_baris.
10. Setelah kedua loop selesai, tampilkan total_semua dan count_genap.
Kerangka Program
print("Tabel Perkalian dan Statistik")
n = int(input("n: "))
# Lengkapi validasi n dengan while.
# Inisialisasi total keseluruhan dan counter genap.
# Gunakan nested loop untuk tabel, total baris, total keseluruhan, dan pencacahan.
Test Case Wajib
n Jumlah pasangan Total semua Banyak hasil genap
1 1 1 0
2 4 9 3
3 9 36 5

Kriteria Keberhasilan Tugas 3
• [ ] Program dapat dijalankan tanpa SyntaxError atau IndentationError.
• [ ] Validasi n berhenti tepat setelah input positif.
• [ ] Nested loop menghasilkan tepat n x n pasangan.
• [ ] Jumlah setiap baris benar.
• [ ] Total keseluruhan benar untuk seluruh test case.
• [ ] Counter genap benar dan hanya bertambah ketika hasil genap.
• [ ] Struktur kode jelas dan tidak mengulang proses yang tidak diperlukan.