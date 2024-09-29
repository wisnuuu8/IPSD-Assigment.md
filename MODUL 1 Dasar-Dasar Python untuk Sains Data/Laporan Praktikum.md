# <h1 align="center">Laporan Praktikum Modul Dasar-Dasar Python untuk Sains Data</h1>
<p align="center">Wisnu Aji Sanjaya</p>

## Dasar Teori

 **Dasar Dasar Python untuk sains data**:

### 1. **Variabel dan Tipe Data**
   - **Variabel**: Menyimpan nilai yang bisa digunakan kembali.
   - **Tipe data dasar**:
     - `int`: Bilangan bulat (misal: `x = 10`)
     - `float`: Bilangan desimal (misal: `y = 10.5`)
     - `str`: Teks (misal: `nama = "Data Science"`)
     - `bool`: Nilai benar/salah (misal: `is_active = True`)

### 2. **Struktur Data**
   - **List**: Kumpulan nilai terurut (misal: `data = [1, 2, 3]`)
   - **Dictionary**: Pasangan kunci-nilai (misal: `data = {'nama': 'Andi', 'umur': 25}`)
   - **Tuple**: Kumpulan nilai tidak bisa diubah (misal: `koordinat = (10, 20)`)
   - **Set**: Kumpulan nilai unik (misal: `angka_unik = {1, 2, 3}`)

### 3. **Kontrol Alur**
   - **If-else**: Struktur untuk membuat keputusan.
   - **Looping**: Untuk iterasi, menggunakan `for` dan `while`.

### 4. **Fungsi**
   - Memudahkan modularisasi kode. Contoh:
     ```python
     def hitung_rata_rata(data):
         return sum(data) / len(data)
     ```

### 5. **Libraries untuk Data Science**
   - **NumPy**: Untuk komputasi numerik.
   - **Pandas**: Untuk manipulasi dan analisis data.
   - **Matplotlib dan Seaborn**: Untuk visualisasi data.
   - **Scikit-learn**: Untuk machine learning dan statistik.

### 6. **File I/O**
   - Membaca dan menulis data, seperti file CSV, menggunakan Pandas:
     ```python
     import pandas as pd
     df = pd.read_csv('data.csv')
     ```

### 7. **Jupyter Notebook**
   - Alat interaktif untuk eksplorasi data, penulisan catatan, dan visualisasi langsung.

## Guided 1

### 1. [Lambda dan Higher-Order Functions]
**89. Buat fungsi lambda untuk menghitung kuadrat dari sebuah angka.**
```Python
# Fungsi lambda untuk menghitung kuadrat
kuadrat = lambda x: x ** 2

# Memasukkan input dari pengguna
angka = int(input("Masukkan sebuah angka: "))

# Menghitung kuadrat dari angka yang dimasukkan
hasil = kuadrat(angka)

# Menampilkan hasil
print(f"Kuadrat dari {angka} adalah {hasil}")
```
```Python
# Fungsi lambda untuk menghitung kuadrat
kuadrat = lambda x: x ** 2
```
Penjelasan :

- fungsi Lambda:

kuadrat adalah fungsi lambda yang menerima satu argumen x dan mengembalikan kuadrat dari x.

```Python
# Memasukkan input dari pengguna
angka = int(input("Masukkan sebuah angka: "))
```
Penjelasan :

- Input Pengguna

Program meminta pengguna untuk memasukkan sebuah angka dan mengonversinya menjadi int.

```Python
# Menghitung kuadrat dari angka yang dimasukkan
hasil = kuadrat(angka)
# Menampilkan hasil
print(f"Kuadrat dari {angka} adalah {hasil}")
```
Penjelasan : 

- Menghitung dan Menampilkan Hasil 

Program menghitung kuadrat dari angka yang dimasukkan menggunakan fungsi lambda dan kemudian menampilkan hasilnya.

## Hasil output
```Python
Masukkan sebuah angka:  2
Kuadrat dari 2 adalah 4
```
Penjelasan :

Program ini memberikan cara sederhana untuk menghitung kuadrat dari angka yang dimasukkan oleh pengguna dan mencetak hasilnya. Anda dapat mencoba dengan berbagai angka untuk melihat hasilnya. 

## Guided 2

### 2. [ Modules dan Packages ]
**84. Buat program yang meng-import modul matematika dan menggunakan fungsi `sqrt`.**
```Python
# Meng-import modul matematika
import math

# Memasukkan input dari pengguna
angka = float(input("Masukkan sebuah angka: "))

# Menggunakan fungsi sqrt dari modul math untuk menghitung akar kuadrat
hasil = math.sqrt(angka)

# Menampilkan hasil
print(f"Akar kuadrat dari {angka} adalah {hasil}")
```
```Python
# Meng-import modul matematika
import math
```
Penjelasan : 

- Mengimpor Modul

import math: Mengimpor modul matematika yang menyediakan berbagai fungsi matematis, termasuk sqrt.

```Python
# Memasukkan input dari pengguna
angka = float(input("Masukkan sebuah angka: "))
```
Penjelasan : 

- Input Pengguna

Program meminta pengguna untuk memasukkan sebuah angka dan mengonversinya menjadi tipe float untuk memungkinkan angka desimal.

```Python
# Menggunakan fungsi sqrt dari modul math untuk menghitung akar kuadrat
hasil = math.sqrt(angka)
```
Penjelasan :

math.sqrt(angka): Menghitung akar kuadrat dari angka yang dimasukkan

```Python
# Menampilkan hasil
print(f"Akar kuadrat dari {angka} adalah {hasil}")
```
Penjelasan : 

- Menampilkan Hasil

Program menampilkan hasil akar kuadrat dalam format yang jelas.

## Hasil output 
```Python
Masukkan sebuah angka:  4
Akar kuadrat dari 4.0 adalah 2.0
```
Penjelasan :

Program menampilkan "Akar kuadrat dari 25.0 adalah 5.0".
25.0 menunjukkan bahwa angka yang dimasukkan telah dikonversi menjadi tipe float.
5.0 menunjukkan bahwa hasilnya juga ditampilkan dalam format float.

## Guided 3
### 3. [ Miscellaneous ]
**93. Buat program untuk menghitung jumlah huruf vokal dalam sebuah string.**
```Python
## Miscellaneous
def hitung_huruf_vokal(teks):
    vokal = "aiueoAIUEO"
    jumlah_vokal = 0

    for huruf in teks:
        if huruf in vokal:
            jumlah_vokal += 1

    return jumlah_vokal

# Contoh penggunaan
teks = input("Masukkan sebuah string: ")
jumlah = hitung_huruf_vokal(teks)

print(f"Jumlah huruf vokal dalam string adalah: {jumlah}")
```
Penjelasan :

Fungsi hitung_huruf_vokal(teks):

Fungsi ini menerima satu argumen, teks, yang merupakan string input dari pengguna.
Di dalam fungsi, terdapat variabel vokal yang berisi daftar huruf vokal dalam format huruf kecil dan besar.
Variabel jumlah_vokal diinisialisasi dengan nilai 0, yang akan digunakan untuk menghitung jumlah huruf vokal.
Looping dan Pengecekan:

Menggunakan loop for, program mengiterasi setiap huruf dalam string teks.
Dengan menggunakan pernyataan if, program memeriksa apakah huruf saat ini ada dalam daftar vokal.
Jika huruf adalah vokal, jumlah_vokal akan ditambahkan 1.
Pengembalian Hasil:

Setelah selesai mengiterasi, fungsi mengembalikan total jumlah huruf vokal yang ditemukan.
Contoh Penggunaan:

Program meminta pengguna untuk memasukkan sebuah string.
Fungsi hitung_huruf_vokal(teks) dipanggil dengan string tersebut untuk menghitung jumlah huruf vokal.
Hasil jumlah vokal ditampilkan di layar.

## Hssil output 
```Python
Masukkan sebuah string:  wisnu aji sanjaya 
Jumlah huruf vokal dalam string adalah: 7
```
Penjelasan : 

Program ini memberikan cara yang sederhana dan efektif untuk menghitung huruf vokal dalam sebuah teks. 

## Guided 4
### 4. [ OOP (Object-Oriented Programming) ]
**76. Buat class `Mahasiswa` yang memiliki atribut nama dan umur.**
```Python
class Mahasiswa:
    # Konstruktor untuk inisialisasi atribut nama dan umur
    def __init__(self, nama, umur):
        self.nama = nama
        self.umur = umur

    # Method untuk menampilkan informasi mahasiswa
    def tampilkan_info(self):
        print(f"Nama: {self.nama}")
        print(f"Umur: {self.umur}")

# Memasukkan data mahasiswa dari input pengguna
nama = input("Masukkan nama mahasiswa: ")
umur = int(input("Masukkan umur mahasiswa: "))

# Membuat objek Mahasiswa dengan input pengguna
mahasiswa = Mahasiswa(nama, umur)

# Memanggil method untuk menampilkan informasi
mahasiswa.tampilkan_info()
```
```Python
class Mahasiswa:
    # Konstruktor untuk inisialisasi atribut nama dan umur
    def __init__(self, nama, umur):
        self.nama = nama
        self.umur = umur

    # Method untuk menampilkan informasi mahasiswa
    def tampilkan_info(self):
        print(f"Nama: {self.nama}")
        print(f"Umur: {self.umur}")
```
Penjelasan :

Definisi Kelas Mahasiswa:

class Mahasiswa: Mendefinisikan kelas bernama Mahasiswa.
Konstruktor:
__init__(self, nama, umur): Metode khusus (konstruktor) yang dipanggil saat objek dari kelas ini dibuat. Ia menginisialisasi atribut nama dan umur berdasarkan argumen yang diberikan saat objek dibuat.

Atribut:
self.nama: Menyimpan nama mahasiswa.
self.umur: Menyimpan umur mahasiswa.

```Python
# Memasukkan data mahasiswa dari input pengguna
nama = input("Masukkan nama mahasiswa: ")
umur = int(input("Masukkan umur mahasiswa: "))
```
Penjelasan :

- Input Pengguna

nama = input("Masukkan nama mahasiswa: "): Meminta pengguna untuk memasukkan nama mahasiswa.
umur = int(input("Masukkan umur mahasiswa: ")): Meminta pengguna untuk memasukkan umur mahasiswa, yang kemudian dikonversi menjadi tipe int

```python
# Membuat objek Mahasiswa dengan input pengguna
mahasiswa = Mahasiswa(nama, umur)

# Memanggil method untuk menampilkan informasi
mahasiswa.tampilkan_info()
```
Penjelasan :

Membuat Objek Mahasiswa:

mahasiswa = Mahasiswa(nama, umur): Membuat objek baru dari kelas Mahasiswa dengan nama dan umur yang dimasukkan oleh pengguna.
Menampilkan Informasi:

mahasiswa.tampilkan_info(): Memanggil method tampilkan_info() pada objek mahasiswa untuk menampilkan informasi yang telah diinput.

## Hasil output 
```Python
Masukkan nama mahasiswa:  wisnu
Masukkan umur mahasiswa:  16
Nama: wisnu
Umur: 16
```
Penjelasan :

Program ini merupakan contoh dasar OOP di Python, di mana kita mendefinisikan kelas dengan atribut dan method. Program ini memungkinkan pengguna untuk berinteraksi dengan kelas Mahasiswa, menciptakan objek baru, dan menampilkan informasi yang relevan. 

## Unguided 1

### 1. [Memecahkan Masalah Unik dengan Loop dan If-Else]
**Soal**: Buatlah program yang dapat menghasilkan pola berbentuk angka seperti di bawah ini, dengan syarat angka yang ditampilkan adalah hasil dari penjumlahan bilangan prima sebelumnya:

```Python
def is_prime(n):
    """Cek apakah suatu bilangan adalah bilangan prima."""
    if n <= 1:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def generate_primes(num_primes):
    """Menghasilkan daftar bilangan prima sebanyak num_primes."""
    primes = []
    candidate = 2  
    while len(primes) < num_primes:
        if is_prime(candidate):
            primes.append(candidate)
        candidate += 1
    return primes

def generate_pattern(rows):
    """Menghasilkan pola bilangan prima sesuai jumlah baris yang diinginkan."""
    primes = generate_primes((rows * (rows + 1)) // 2) 
    index = 0  # Indeks untuk mengambil bilangan prima

    for i in range(1, rows + 1):
        line = []
        for j in range(i):  
            line.append(primes[index])
            index += 1
        print(" ".join(map(str, line)))

generate_pattern(5)
```
```Python
def is_prime(n):
    """Cek apakah suatu bilangan adalah bilangan prima."""
    if n <= 1:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True
```
Penjelasan :

Fungsi `is_prime(n)` adalah fungsi yang digunakan untuk memeriksa apakah suatu bilangan merupakan bilangan prima. Fungsi ini menerima satu argumen, `n`, yang merupakan bilangan yang akan diperiksa. Di dalam fungsi, terdapat dokumentasi yang menjelaskan tujuan fungsi tersebut, yaitu untuk mengecek apakah suatu bilangan adalah bilangan prima. Pertama, fungsi memeriksa apakah `n` kurang dari atau sama dengan 1. Bilangan prima adalah bilangan bulat positif yang lebih besar dari 1; oleh karena itu, jika `n` memenuhi kondisi tersebut, fungsi akan mengembalikan nilai `False`. Selanjutnya, fungsi melakukan loop untuk memeriksa apakah `n` dapat dibagi oleh bilangan bulat dari 2 hingga akar kuadrat dari `n`, yang dihitung menggunakan `int(n**0.5)`. Hal ini dilakukan karena jika `n` dapat dibagi oleh suatu bilangan `i`, maka `n` juga dapat dibagi oleh `n/i`, dan salah satu dari kedua bilangan ini pasti kurang dari atau sama dengan akar kuadrat dari `n`. Di dalam loop, fungsi memeriksa apakah `n` habis dibagi oleh `i` dengan menggunakan operator modulus (`%`). Jika `n` habis dibagi oleh `i`, maka `n` bukan bilangan prima, dan fungsi mengembalikan nilai `False`. Namun, jika tidak ada faktor pembagi yang ditemukan selama proses pengecekan, maka dapat disimpulkan bahwa `n` adalah bilangan prima, sehingga fungsi mengembalikan nilai `True`.

```Python
def generate_primes(num_primes):
    """Menghasilkan daftar bilangan prima sebanyak num_primes."""
    primes = []
    candidate = 2  
    while len(primes) < num_primes:
        if is_prime(candidate):
            primes.append(candidate)
        candidate += 1
    return primes
```
Penjelasan :

Generate_primes(num_primes) ini menyediakan cara yang efisien untuk menghasilkan sejumlah bilangan prima. Dengan menggunakan fungsi is_prime untuk memeriksa keprimaan setiap kandidat, fungsi ini secara bertahap membangun daftar bilangan prima yang diinginkan.

```Python
def generate_pattern(rows):
    """Menghasilkan pola bilangan prima sesuai jumlah baris yang diinginkan."""
    primes = generate_primes((rows * (rows + 1)) // 2) 
    index = 0  # Indeks untuk mengambil bilangan prima

    for i in range(1, rows + 1):
        line = []
        for j in range(i):  
            line.append(primes[index])
            index += 1
        print(" ".join(map(str, line)))

generate_pattern(5)
```
Penjelasan :

Fungsi `generate_pattern(rows)` menghasilkan pola bilangan prima dalam format segitiga berdasarkan jumlah baris yang ditentukan oleh argumen `rows`. Fungsi ini pertama-tama memanggil `generate_primes` untuk menghitung total bilangan prima yang dibutuhkan, menggunakan rumus `(rows * (rows + 1)) // 2`. Dengan menggunakan loop dari 1 hingga `rows`, fungsi ini menambahkan bilangan prima ke dalam daftar `line` sesuai dengan jumlah yang diperlukan untuk setiap baris, kemudian mencetaknya sebagai string yang dipisahkan oleh spasi. Misalnya, jika dijalankan dengan argumen `5`, fungsi ini akan menghasilkan pola segitiga bilangan prima dengan 5 baris. Fungsi ini menyediakan cara efisien untuk menampilkan bilangan prima dalam format menarik dan dapat disesuaikan.

## Hasil output
```Python
2
3 5
7 11 13
17 19 23 29
31 37 41 43 47
```
Penjelasan :

