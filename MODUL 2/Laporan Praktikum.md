# <h1 align="center">Laporan Praktikum Modul Pengolahan Data Movie classification</h1>
<p align="center">Wisnu Aji Sanjaya</p>

## Dasar Teori

**PENGOLAHAN DATA DENGAN PYTHON**

Pengolahan data adalah proses penting dalam mengubah data mentah menjadi informasi yang lebih berguna dan terstruktur. Python, sebagai salah satu bahasa pemrograman yang paling populer untuk analisis data, menawarkan sintaksis yang sederhana dan berbagai pustaka yang mendukung, seperti Pandas, NumPy, Matplotlib, dan Seaborn. Pandas menjadi pustaka utama untuk manipulasi dan analisis data, dengan struktur data seperti `DataFrame` dan `Series` yang memungkinkan pengguna untuk bekerja dengan data dalam format yang mirip dengan tabel. 

Dalam pengolahan data, pengguna dapat membaca data dari berbagai format file menggunakan fungsi seperti `pd.read_csv()` dan `pd.read_excel()`, serta menyimpannya kembali ke dalam file menggunakan metode seperti `to_csv()` dan `to_excel()`. Selain itu, manipulasi data yang meliputi filtering, grouping, dan aggregation dapat dilakukan dengan mudah. Pembersihan data juga merupakan langkah penting, di mana pengguna dapat menangani data yang hilang atau duplikat menggunakan fungsi seperti `dropna()` dan `fillna()`. 

Analisis data dapat dilakukan dengan menghitung nilai statistik menggunakan metode `describe()` untuk mendapatkan ringkasan statistik. Visualisasi data juga berperan penting dalam analisis, dengan penggunaan grafik seperti histogram, box plot, dan scatter plot untuk menyajikan hasil analisis secara visual. Contoh penerapan pengolahan data dengan Python dapat terlihat pada analisis data penjualan, data keuangan, atau data hasil survei. Kesimpulannya, Python, bersama dengan pustaka-pustaka yang ada, menyediakan alat yang kuat dan fleksibel untuk pengolahan dan analisis data, didukung oleh komunitas yang besar serta banyak sumber daya pembelajaran yang memudahkan pengguna untuk mendalami topik ini.

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

**NOMOR 2**

Cek nilai duplikat
```Python
df.duplicated()
```
Penjelasan :

Fungsi ini mengembalikan sebuah Series boolean yang menunjukkan apakah setiap baris dalam DataFrame adalah duplikat atau tidak.

## HASIL OUTPUT 

![image](https://github.com/user-attachments/assets/2daea239-23d3-46ea-a03e-9fcb3271bc95)


