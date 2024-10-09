# <h1 align="center">Laporan Praktikum Modul Pengolahan Data Movie classification</h1>
<p align="center">Wisnu Aji Sanjaya</p>

## Dasar Teori

**PENGOLAHAN DATA DENGAN PYTHON**

Pengolahan data adalah proses penting dalam mengubah data mentah menjadi informasi yang lebih berguna dan terstruktur[1]. Python, sebagai salah satu bahasa pemrograman yang paling populer untuk analisis data, menawarkan sintaksis yang sederhana dan berbagai pustaka yang mendukung, seperti Pandas, NumPy, Matplotlib, dan Seaborn. Pandas menjadi pustaka utama untuk manipulasi dan analisis data, dengan struktur data seperti `DataFrame` dan `Series` yang memungkinkan pengguna untuk bekerja dengan data dalam format yang mirip dengan tabel. 

Dalam pengolahan data, pengguna dapat membaca data dari berbagai format file menggunakan fungsi seperti `pd.read_csv()` dan `pd.read_excel()`, serta menyimpannya kembali ke dalam file menggunakan metode seperti `to_csv()` dan `to_excel()`. Selain itu, manipulasi data yang meliputi filtering, grouping, dan aggregation dapat dilakukan dengan mudah. Pembersihan data juga merupakan langkah penting, di mana pengguna dapat menangani data yang hilang atau duplikat menggunakan fungsi seperti `dropna()` dan `fillna()`[2]. 

Analisis data dapat dilakukan dengan menghitung nilai statistik menggunakan metode `describe()` untuk mendapatkan ringkasan statistik[3]. Visualisasi data juga berperan penting dalam analisis, dengan penggunaan grafik seperti histogram, box plot, dan scatter plot untuk menyajikan hasil analisis secara visual. Contoh penerapan pengolahan data dengan Python dapat terlihat pada analisis data penjualan, data keuangan, atau data hasil survei. Kesimpulannya, Python, bersama dengan pustaka-pustaka yang ada, menyediakan alat yang kuat dan fleksibel untuk pengolahan dan analisis data, didukung oleh komunitas yang besar serta banyak sumber daya pembelajaran yang memudahkan pengguna untuk mendalami topik ini.

## UNGUIDED

**NOMOR 1**

Load data (movie classification)
```Python
import pandas as pd

# Memuat data CSV
df = pd.read_csv('Movie_classification.csv')

# Menampilkan data
df.head()
```
Penjelasan : 
`import pandas as pd` : Baris ini mengimpor pustaka Pandas dengan alias pd. Pustaka ini digunakan untuk manipulasi dan analisis data, terutama untuk bekerja dengan data dalam bentuk tabel.

`df = pd.read_csv('Movie_classification.csv')` : Fungsi pd.read_csv() digunakan untuk membaca file CSV yang bernama Movie_classification.csv. Hasilnya disimpan dalam variabel df, yang merupakan objek DataFrame. DataFrame adalah struktur data dua dimensi yang mirip dengan tabel, memungkinkan pengguna untuk menyimpan dan mengelola data dengan mudah.

`df.head()` : Metode head() digunakan untuk menampilkan lima baris pertama dari DataFrame df. Ini berguna untuk memberikan gambaran awal tentang data yang dimuat, seperti nama kolom dan beberapa entri data.

## HASIL OUTPUT
![image](https://github.com/user-attachments/assets/63180720-13fa-4525-9685-3890989fbbbf)

![image](https://github.com/user-attachments/assets/04a7cfdc-d3db-49a7-94cd-abbaf729dffa)

Penjelasan :

Tabel: Output akan ditampilkan dalam format tabel dengan kolom-kolom yang sesuai dengan nama-nama kolom yang ada di dalam file CSV.

Kolom: Setiap kolom dalam tabel mewakili fitur atau atribut dari data film. Misalnya, kolom-kolom tersebut mungkin termasuk:

Marketing expense: Pengeluaran untuk pemasaran film.

Production expense: Pengeluaran untuk produksi film.

Multiplex coverage: Jumlah multiplex yang menayangkan film tersebut.

Budget: Anggaran yang dialokasikan untuk film.

Movie_length: Durasi film dalam menit.

Lead Actor Rating: Rating dari aktor utama.

Collection: Pendapatan yang diperoleh dari film.

Start Tech Oscar: Apakah film tersebut dinominasikan untuk Oscar (1 untuk ya, 0 untuk tidak).

Baris: Setiap baris dalam tabel mewakili satu entri atau record, yang berarti satu film. Data pada setiap baris memberikan informasi spesifik tentang film tersebut berdasarkan kolom yang ada.

Indeks: Biasanya, setiap baris juga memiliki indeks yang menunjukkan urutan baris dalam DataFrame, mulai dari 0 hingga n-1, di mana n adalah jumlah total baris.

**NOMOR 2**

Cek nilai duplikat
```Python
df.duplicated()
```
Penjelasan :

Fungsi `df.duplicated()` pada objek DataFrame di Pandas digunakan untuk mengidentifikasi baris-baris yang duplikat dalam DataFrame df. Hasilnya adalah serangkaian nilai boolean yang menunjukkan apakah setiap baris adalah duplikat dari baris sebelumnya atau tidak. Fungsi ini sangat berguna ketika kamu ingin memeriksa atau menghapus duplikasi data dalam suatu dataset
## HASIL OUTPUT 

![image](https://github.com/user-attachments/assets/2daea239-23d3-46ea-a03e-9fcb3271bc95)

Penjelasanc :

Hasil dari df.duplicated() adalah sebuah Series boolean, di mana setiap elemen dalam Series ini menunjukkan apakah baris yang bersangkutan adalah duplikat dari baris sebelumnya atau tidak.

Nilai True menunjukkan bahwa baris tersebut adalah duplikat, sedangkan False menunjukkan bahwa baris tersebut unik (bukan duplikat).

**NOMOR 3**

Menemukan null values buat presentase
```Python
null_percentage = df.isnull().mean() * 100

null_percentage
```
Penjelasan :

Fungsi df.isnull().mean() * 100 digunakan untuk menghitung persentase nilai yang hilang (missing values atau NaN) dalam setiap kolom dari DataFrame df.

`df.isnull()`: Menghasilkan DataFrame boolean dengan True untuk nilai yang hilang (NaN) dan False untuk nilai yang ada.

`.mean()`: Menghitung rata-rata dari setiap kolom, yang sebenarnya menghitung proporsi nilai True (nilai hilang) di kolom tersebut. Ini bekerja karena True bernilai 1 dan False bernilai 0 dalam konteks perhitungan.

`* 100`: Mengonversi proporsi nilai yang hilang menjadi persentase.

## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/fbc71fa0-5832-4a9d-a618-902f4ca1cdc5)

Penjelasan :

Nama Kolom:

Kolom-kolom yang ditampilkan, seperti Marketing expense, Production expense, Multiplex coverage, dan lainnya, menunjukkan atribut atau fitur dari dataset film.
Nilai 0.000000:

Angka tersebut menunjukkan bahwa tidak ada nilai yang hilang untuk masing-masing kolom. Artinya, semua data di kolom-kolom ini lengkap dan tidak ada entri yang hilang.
dtype: float64:

Ini menunjukkan bahwa tipe data dari nilai yang ditampilkan adalah float64, yang biasanya digunakan untuk angka desimal dalam pandas

**NOMOR 4**

Drop missing value berdasarkan baris, kolom, imputasi dengan mean, modus, median

## Part 1
```Python
df_dropped_rows = df.dropna()

df_dropped_rows
```
Penjelasan :

Fungsi df.dropna() digunakan untuk menghapus baris yang mengandung nilai NaN (hilang) dari DataFrame. Hasilnya adalah DataFrame baru, di mana semua baris yang memiliki setidaknya satu nilai NaN akan dihapus.

`df.dropna()`: Menghapus baris yang mengandung nilai NaN (hilang).
Secara default, fungsi ini akan menghapus baris, tetapi bisa disesuaikan untuk kolom atau baris tertentu.
## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/f153b307-6d86-484c-9064-aa0b6c8c5055)

![image](https://github.com/user-attachments/assets/c81048a5-eb54-4534-bd2f-4b34a9035c79)

Penjelasan :

Output ini memberikan gambaran umum tentang atribut film yang tercatat dalam dataset. Data tersebut dapat digunakan untuk analisis lebih lanjut, seperti analisis performa film, hubungan antara pengeluaran dan pendapatan, atau karakteristik genre film.

## Part 2
```Python
df_dropped_columns = df.dropna(axis=1)

df_dropped_columns
```
Penjelasan :

Fungsi `df.dropna(axis=1)` digunakan untuk menghapus kolom yang mengandung nilai NaN (hilang) dalam DataFrame df. Secara default, dropna() bekerja pada baris, tetapi dengan menambahkan parameter axis=1, kamu bisa menghapus kolom-kolom yang memiliki nilai hilang.

`axis=1`: Mengarahkan fungsi untuk bekerja pada kolom. Jika ada nilai NaN di dalam kolom mana pun, kolom tersebut akan dihapus.

`dropna()`: Menghapus entitas (baris atau kolom) yang mengandung nilai hilang (NaN).

## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/460017b9-82a1-46fb-b730-477b2eee161d)

![image](https://github.com/user-attachments/assets/cdacc4b7-950d-4b44-8d64-f227b8e4e99e)

Penjelasan :

Output dari df_dropped_columns adalah DataFrame baru yang berisi semua kolom dari df, tetapi tanpa kolom yang memiliki nilai hilang (NaN).

Contoh Output: Misalnya, jika DataFrame df awalnya memiliki 19 kolom dan ada 3 kolom yang memiliki nilai hilang, maka df_dropped_columns akan memiliki 16 kolom.

Jika tidak ada kolom yang memiliki nilai hilang, maka output df_dropped_columns akan identik dengan df.

## Part 3
```Python
import pandas as pd

print(df.dtypes)

for column in df.columns:
    df[column] = pd.to_numeric(df[column], errors='coerce')

df_mean_imputed = df.fillna(df.mean())

print(df_mean_imputed)
```
Penjelasan :

`pd.to_numeric(df[column], errors='coerce')`: Kode ini mencoba mengonversi setiap kolom dalam DataFrame ke tipe numerik.

Jika ada data yang tidak bisa dikonversi (misalnya, teks), opsi errors='coerce' akan menggantinya dengan NaN.
Ini dilakukan untuk setiap kolom dalam DataFrame, sehingga semua data non-numerik akan diganti dengan NaN, memungkinkan perhitungan matematis seperti pengisian nilai rata-rata.

`df.mean()`: Menghitung rata-rata dari setiap kolom.

`df.fillna(df.mean())`: Mengisi nilai yang hilang (NaN) di setiap kolom dengan rata-rata kolom yang bersangkutan. Ini merupakan metode imputasi rata-rata yang sering digunakan dalam menangani missing data.

## HASIL OUTPUT
![image](https://github.com/user-attachments/assets/d5a06351-5df5-41ad-ad70-4bf1549086b9)

![image](https://github.com/user-attachments/assets/5e7b3c81-d6dd-4899-b645-8c0d0df3c85c)

![image](https://github.com/user-attachments/assets/497a66d9-8241-462b-a68d-64c193a787fa)

![image](https://github.com/user-attachments/assets/1d46352c-c1dd-41b1-9ae6-74074e9587f3)

![image](https://github.com/user-attachments/assets/05c44979-4fa5-4da1-918f-e4c0aeb8c0f6)

![image](https://github.com/user-attachments/assets/44918724-2c0c-401e-88f9-3ba1d66931dc)

Penjelasan :

Output dari kode ini memberikan informasi yang berguna mengenai tipe data dalam DataFrame, dan juga menunjukkan bagaimana nilai yang hilang dapat diatasi dengan mengganti nilai NaN dengan nilai rata-rata kolom yang bersangkutan. Ini adalah langkah umum dalam pembersihan data dan persiapan sebelum melakukan analisis lebih lanjut.

## Part 4
```Python
df_median_imputed = df.fillna(df.median())

df_median_imputed
```
Penjelasan :

`df.median()`: Menghitung median dari setiap kolom dalam DataFrame df. Median adalah nilai tengah dari data yang diurutkan. Jika jumlah data genap, median adalah rata-rata dari dua nilai tengah.

`df.fillna(df.median())`: Mengganti semua nilai yang hilang (NaN) di DataFrame df dengan nilai median dari kolom yang bersangkutan.

## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/11354b48-0526-4871-ac0b-e2dc16c12b48)

![image](https://github.com/user-attachments/assets/912468d7-c858-4e6d-83c2-ec160752cd4f)

Penjelasan :

Output dari df_median_imputed adalah DataFrame baru yang sama dengan df, tetapi semua nilai NaN di setiap kolom telah diganti dengan nilai median dari kolom tersebut.

Misalnya, jika sebelumnya ada nilai NaN pada kolom Marketing expense, dan nilai median kolom tersebut adalah 205.462, maka semua NaN pada kolom itu akan diganti dengan 205.462

## Part 5
```Python
df_mode_imputed = df.fillna(df.mode().iloc[0])

df_mode_imputed
```
Penjelasan :

`df.mode()`: Menghitung modus dari setiap kolom dalam DataFrame df. Modus adalah nilai yang paling sering muncul dalam sebuah kolom.

`.iloc[0]`: Modus mengembalikan DataFrame yang bisa memiliki lebih dari satu modus (jika ada lebih dari satu nilai yang paling sering muncul). Dengan iloc[0], kamu memilih modus pertama (jika ada beberapa modus).

`df.fillna(df.mode().iloc[0])`: Mengganti semua nilai yang hilang (NaN) di DataFrame df dengan modus dari kolom yang bersangkutan.

## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/6493b012-1890-4dcd-9f66-e338e862a3b7)

![image](https://github.com/user-attachments/assets/01900c87-4468-4153-ab6b-ff80b0bc85f8)

Penjelasan :

DataFrame baru yang sama dengan df, tetapi semua nilai NaN di setiap kolom telah diganti dengan nilai modus dari kolom tersebut

**NOMOR 5**

Export data ke csv dan excel

```Python
output_csv_path = 'Movie_classification.csv'
df.to_csv(output_csv_path, index=False)
print(f"Data telah disimpan ke {output_csv_path}")

output_excel_path = 'Movie_classification.xlsx'
df.to_excel(output_excel_path, index=False)
print(f"Data telah disimpan ke {output_excel_path}")
```
Penjelasan :

`output_csv_path = 'Movie_classification.csv'`: Mendefinisikan path untuk menyimpan file CSV.

`df.to_csv(output_csv_path, index=False)`: Menyimpan DataFrame df ke file CSV tanpa menyertakan index (karena index=False).

`print(f"Data telah disimpan ke {output_csv_path}")`: Mencetak pesan yang mengonfirmasi bahwa file CSV telah disimpan.

`output_excel_path = 'Movie_classification.xlsx'`: Mendefinisikan path untuk menyimpan file Excel.

`df.to_excel(output_excel_path, index=False)`: Menyimpan DataFrame df ke file Excel tanpa menyertakan index (karena index=False).

`print(f"Data telah disimpan ke {output_excel_path}")`: Mencetak pesan yang mengonfirmasi bahwa file Excel telah disimpan.

## HASIL OUTPUT
![image](https://github.com/user-attachments/assets/eef42d48-b975-48db-b015-b316d2395444)

Penjelasan :

Kode ini adalah langkah terakhir dalam proses analisis dan manipulasi data, di mana Anda menyimpan data yang telah diproses ke dalam format yang dapat digunakan untuk analisis lebih lanjut atau untuk berbagi dengan orang lain

## KESIMPULAN

Kesimpulan dari laporan praktikum ini menunjukkan bahwa pengolahan data menggunakan Python, khususnya dengan pustaka Pandas, merupakan proses yang efisien dan efektif dalam mengubah data mentah menjadi informasi yang terstruktur dan bermanfaat. Dalam praktik ini, langkah-langkah seperti memuat data, mengidentifikasi nilai duplikat, menangani nilai hilang melalui berbagai metode imputasi (rata-rata, median, dan modus), serta menyimpan hasil pengolahan ke dalam format CSV dan Excel, telah dilakukan dengan baik. Proses ini tidak hanya membantu meningkatkan kualitas data tetapi juga mempersiapkan data untuk analisis lebih lanjut, yang merupakan kunci dalam pengambilan keputusan berbasis data.

## REFERENSI 

(1). Nawassyarif, M. K. (2020). SISTEM INFORMASI PENGOLAHAN DATA TERNAK UNIT PELAKSANA . 32-39.

(2). ER1, R. F. (2023). Sistem Informasi Pengelolaan Data Nilai Siswa. 700-710.

(3). Soband, A. (2002). PENGOLAHAN DATA DALAM SISTEM INFORMASI. 89-95.

