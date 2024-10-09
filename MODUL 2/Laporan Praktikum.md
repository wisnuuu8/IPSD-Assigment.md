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

**NOMOR 3**

Menemukan null values buat presentase
```Python
null_percentage = df.isnull().mean() * 100

null_percentage
```
Penjelasan :

## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/fbc71fa0-5832-4a9d-a618-902f4ca1cdc5)

**NOMOR 4**

Drop missing value berdasarkan baris, kolom, imputasi dengan mean, modus, median
```Python
df_dropped_rows = df.dropna()

df_dropped_rows
```
Penjelasan :

## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/f153b307-6d86-484c-9064-aa0b6c8c5055)

![image](https://github.com/user-attachments/assets/c81048a5-eb54-4534-bd2f-4b34a9035c79)

```Python
df_dropped_columns = df.dropna(axis=1)

df_dropped_columns
```
Penjelasan :

## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/460017b9-82a1-46fb-b730-477b2eee161d)

![image](https://github.com/user-attachments/assets/cdacc4b7-950d-4b44-8d64-f227b8e4e99e)

```Python
import pandas as pd

print(df.dtypes)

for column in df.columns:
    df[column] = pd.to_numeric(df[column], errors='coerce')

df_mean_imputed = df.fillna(df.mean())

print(df_mean_imputed)
```
Penjelasan :

![image](https://github.com/user-attachments/assets/d5a06351-5df5-41ad-ad70-4bf1549086b9)

![image](https://github.com/user-attachments/assets/5e7b3c81-d6dd-4899-b645-8c0d0df3c85c)

![image](https://github.com/user-attachments/assets/497a66d9-8241-462b-a68d-64c193a787fa)

![image](https://github.com/user-attachments/assets/1d46352c-c1dd-41b1-9ae6-74074e9587f3)

![image](https://github.com/user-attachments/assets/05c44979-4fa5-4da1-918f-e4c0aeb8c0f6)

![image](https://github.com/user-attachments/assets/44918724-2c0c-401e-88f9-3ba1d66931dc)

```Python
df_median_imputed = df.fillna(df.median())

df_median_imputed
```
Penjelasan :


## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/11354b48-0526-4871-ac0b-e2dc16c12b48)

![image](https://github.com/user-attachments/assets/912468d7-c858-4e6d-83c2-ec160752cd4f)

```Python
df_mode_imputed = df.fillna(df.mode().iloc[0])

df_mode_imputed
```


## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/6493b012-1890-4dcd-9f66-e338e862a3b7)

![image](https://github.com/user-attachments/assets/01900c87-4468-4153-ab6b-ff80b0bc85f8)

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


## HASIL OUTPUT
![image](https://github.com/user-attachments/assets/eef42d48-b975-48db-b015-b316d2395444)



