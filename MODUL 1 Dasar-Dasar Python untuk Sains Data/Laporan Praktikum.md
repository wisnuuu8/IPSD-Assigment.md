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
   - Alat interaktif untuk eksplorasi data, penulisan catatan, dan visualisasi langsung.[1]

## Guided 1

### 1. [Lambda dan Higher-Order Functions]
**89. Buat fungsi lambda untuk menghitung kuadrat dari sebuah angka.**

![Screenshot 2024-09-29 171036](https://github.com/user-attachments/assets/94d0c26a-edf0-4f7b-95e4-6b9b642648c3)

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

Program menghitung kuadrat dari angka yang dimasukkan menggunakan fungsi lambda dan kemudian menampilkan hasilnya.[3]

## Hasil output
![Screenshot 2024-09-29 171125](https://github.com/user-attachments/assets/4639b0b9-015b-4fef-b6fa-47dc2daa8257)

Penjelasan :

Program ini memberikan cara sederhana untuk menghitung kuadrat dari angka yang dimasukkan oleh pengguna dan mencetak hasilnya. Anda dapat mencoba dengan berbagai angka untuk melihat hasilnya. 

## Guided 2

### 2. [ Modules dan Packages ]
**84. Buat program yang meng-import modul matematika dan menggunakan fungsi `sqrt`.**
![Screenshot 2024-09-29 171156](https://github.com/user-attachments/assets/805e990a-7d24-4b5a-9c11-0d8874714d06)

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
![Screenshot 2024-09-29 171230](https://github.com/user-attachments/assets/741ec8df-0de8-4a3c-a33c-9b5fa0c668fc)

Penjelasan :

Program menampilkan "Akar kuadrat dari 25.0 adalah 5.0".
25.0 menunjukkan bahwa angka yang dimasukkan telah dikonversi menjadi tipe float.
5.0 menunjukkan bahwa hasilnya juga ditampilkan dalam format float.

## Guided 3
### 3. [ Miscellaneous ]
**93. Buat program untuk menghitung jumlah huruf vokal dalam sebuah string.**
![Screenshot 2024-09-29 171308](https://github.com/user-attachments/assets/c366f3ee-3cd3-4934-8541-0fe8b5bbaac7)

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
![Screenshot 2024-09-29 171339](https://github.com/user-attachments/assets/d03350db-5d21-4753-8bf2-e70800402894)

Penjelasan : 

Program ini memberikan cara yang sederhana dan efektif untuk menghitung huruf vokal dalam sebuah teks. 

## Guided 4
### 4. [ OOP (Object-Oriented Programming) ]
**76. Buat class `Mahasiswa` yang memiliki atribut nama dan umur.**

![Screenshot 2024-09-29 171414](https://github.com/user-attachments/assets/4b4f9b5f-d282-4271-83cc-fb95e04968eb)

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
![Screenshot 2024-09-29 171542](https://github.com/user-attachments/assets/f1f6e67c-f4b8-4f32-8245-b831f84cd7cd)

Penjelasan :

Program ini merupakan contoh dasar OOP di Python, di mana kita mendefinisikan kelas dengan atribut dan method. Program ini memungkinkan pengguna untuk berinteraksi dengan kelas Mahasiswa, menciptakan objek baru, dan menampilkan informasi yang relevan. 

## Unguided 1

### 1. [Memecahkan Masalah Unik dengan Loop dan If-Else]
**Soal**: Buatlah program yang dapat menghasilkan pola berbentuk angka seperti di bawah ini, dengan syarat angka yang ditampilkan adalah hasil dari penjumlahan bilangan prima sebelumnya:

![Screenshot 2024-09-29 171627](https://github.com/user-attachments/assets/dc6f1f89-9751-4d9f-9126-a74dc35ad344)

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
![Screenshot 2024-09-29 171704](https://github.com/user-attachments/assets/1d389a0f-a249-43bc-9411-66e7d950c503)

Penjelasan :

Output menampilkan pola segitiga yang diisi dengan bilangan prima, sesuai dengan jumlah baris yang diminta. Ini menunjukkan bagaimana fungsi bekerja secara terintegrasi untuk menghasilkan dan menampilkan bilangan prima dalam format yang teratur dan mudah dibaca.

## Unguided 2

### 2. [Membuat Fungsi dengan Syarat Spesifik]
**Soal**: Buatlah sebuah fungsi yang menerima dua input berupa list angka. Fungsi ini harus mengembalikan sebuah list baru yang berisi elemen dari dua list input yang memiliki indeks ganjil. List baru tersebut juga harus diurutkan secara menurun berdasarkan nilai elemen.

![Screenshot 2024-09-29 171745](https://github.com/user-attachments/assets/55a75e60-3573-4639-b62c-949f07f60683)

```Python
def combine_and_sort_odd_indices(list1, list2):
    """Menggabungkan elemen dari dua list yang memiliki indeks ganjil dan mengurutkannya secara menurun."""
    # Mengambil elemen dengan indeks ganjil dari kedua list
    odd_indexed_elements = []
    
    # Menambahkan elemen dengan indeks ganjil dari list1
    odd_indexed_elements.extend(list1[i] for i in range(1, len(list1), 2))
    
    # Menambahkan elemen dengan indeks ganjil dari list2
    odd_indexed_elements.extend(list2[i] for i in range(1, len(list2), 2))
    
    # Mengurutkan elemen secara menurun
    odd_indexed_elements.sort(reverse=True)
    
    return odd_indexed_elements
```
Penjelassan :

Fungsi `combine_and_sort_odd_indices(list1, list2)` menggabungkan elemen-elemen dari dua list yang memiliki indeks ganjil dan mengurutkannya secara menurun. Pertama, fungsi mengumpulkan elemen dari `list1` dan `list2` yang terletak pada indeks ganjil ke dalam daftar `odd_indexed_elements`. Setelah semua elemen terkumpul, fungsi kemudian mengurutkannya dalam urutan menurun menggunakan metode `sort()`. Terakhir, fungsi mengembalikan daftar yang sudah digabungkan dan diurutkan.

## Hasil output 
![Screenshot 2024-09-29 171816](https://github.com/user-attachments/assets/b657b17a-5e8f-4e52-aac4-ad1a10052025)


## Unguided 3

### 3. [Exception Handling dalam Konteks Nyata]
**Soal**: Buat sebuah program untuk mensimulasikan transaksi ATM. Program harus:
![Screenshot 2024-09-29 171854](https://github.com/user-attachments/assets/a5ef8864-5985-480a-8bbc-45d3ca0d8e2e)
![Screenshot 2024-09-29 171930](https://github.com/user-attachments/assets/fad907ef-bcbe-4e36-a083-7cc90436ba2e)

```Python
def atm_simulation():
    # PIN dan saldo awal
    correct_pin = "1234"
    balance = 10000  # Saldo awal
    attempts = 3

    # Meminta pengguna untuk memasukkan PIN
    while attempts > 0:
        pin = input("Masukkan PIN Anda: ")
        if pin == correct_pin:
            print("PIN benar.")
            break
        else:
            attempts -= 1
            print(f"PIN salah. Sisa percobaan: {attempts}")

    if attempts == 0:
        print("Akses ditolak. Terlalu banyak percobaan.")
        return
```
Penjelasan :

Fungsi `atm_simulation()` mensimulasikan autentikasi PIN untuk akses mesin ATM. Pengguna diberikan tiga percobaan untuk memasukkan PIN yang benar, yaitu "1234". Jika PIN yang dimasukkan benar, fungsi mencetak "PIN benar." Jika salah, sisa percobaan akan berkurang dan ditampilkan. Setelah tiga percobaan yang gagal, program akan mencetak "Akses ditolak. Terlalu banyak percobaan." dan menghentikan proses. Fungsi ini dirancang untuk meningkatkan keamanan dengan membatasi percobaan autentikasi.

```Python
# Meminta jumlah penarikan
    try:
        amount = float(input("Masukkan jumlah yang ingin ditarik: "))
        
        if amount <= 0:
            raise ValueError("Jumlah penarikan harus lebih dari 0.")
        
        if amount > balance:
            raise ValueError("Saldo tidak cukup untuk penarikan ini.")

        # Melakukan penarikan
        balance -= amount
        print(f"Penarikan berhasil. Saldo akhir Anda adalah: {balance}")
        
    except ValueError as e:
        print(f"Kesalahan: {e}")

atm_simulation()
```
Penjelasan :

Bagian kode ini menambahkan fungsi untuk meminta pengguna memasukkan jumlah uang yang ingin ditarik setelah PIN berhasil diverifikasi. Pengguna diminta untuk memasukkan jumlah penarikan, dan kode melakukan validasi input dengan menggunakan blok `try` dan `except` untuk menangani kesalahan. Jika jumlah penarikan kurang dari atau sama dengan nol, atau jika saldo tidak cukup, akan muncul pesan kesalahan. Jika input valid, jumlah penarikan akan dikurangkan dari saldo dan saldo akhir ditampilkan. Dengan demikian, kode ini menyelesaikan simulasi penarikan uang dari mesin ATM.

## Hasil output
![Screenshot 2024-09-29 172002](https://github.com/user-attachments/assets/4bcbfee5-a289-46b4-8e71-2e9811e5181e)

Penjelasan :

Output menunjukkan langkah-langkah interaksi pengguna dengan mesin ATM. Pertama, pengguna memasukkan PIN "3" yang salah, dan program memberi tahu bahwa PIN salah dengan sisa percobaan 2. Selanjutnya, pengguna memasukkan PIN yang benar, "1234", dan berhasil diverifikasi. Setelah itu, pengguna diminta untuk memasukkan jumlah penarikan, yaitu 1000. Program berhasil memproses penarikan dan menampilkan saldo akhir sebagai 9000. Output mencerminkan proses autentikasi dan penarikan uang yang berhasil.

## Unguided 4

### 4. [Studi Kasus Pengelolaan Data]
**Soal**: Anda diberikan file CSV berisi data nilai ujian mahasiswa. Tugas Anda adalah menulis sebuah program yang:

![Screenshot 2024-09-29 172029](https://github.com/user-attachments/assets/8e402b4e-6100-4a3e-9392-7316092ed642)
![Screenshot 2024-09-29 172128](https://github.com/user-attachments/assets/0f6445df-565f-45db-8c72-c04873c79957)

```Python
import csv

def baca_data_csv(nama_file):
    # Membaca file CSV dan menyimpan data ke dalam dictionary
    data_mahasiswa = {}
    
    with open(nama_file, newline='') as file_csv:
        reader = csv.reader(file_csv)
        # Mengabaikan header jika ada
        next(reader)  
        for row in reader:
            nama = row[0]
            # Mengubah nilai menjadi float dan menyimpannya sebagai list
            nilai = list(map(float, row[1:]))
            data_mahasiswa[nama] = nilai
    
    return data_mahasiswa
```
Penjelasan :

Fungsi `baca_data_csv` digunakan untuk membaca data dari file CSV dan menyimpannya dalam bentuk dictionary. Parameter `nama_file` adalah nama file CSV yang akan dibaca. Fungsi ini membuka file, mengabaikan header (jika ada), dan kemudian mengiterasi setiap baris untuk mengambil nama mahasiswa dan nilai-nilainya. Nilai-nilai tersebut diubah menjadi float dan disimpan dalam bentuk list, yang kemudian dipetakan ke nama mahasiswa dalam dictionary `data_mahasiswa`. Akhirnya, fungsi mengembalikan dictionary yang berisi nama mahasiswa sebagai kunci dan list nilai sebagai nilai.

```Python
def hitung_rata_rata(data_mahasiswa):
    # Menghitung rata-rata nilai tiap mahasiswa
    rata_rata_mahasiswa = {}
    for nama, nilai in data_mahasiswa.items():
        rata_rata = sum(nilai) / len(nilai)
        rata_rata_mahasiswa[nama] = rata_rata
    
    return rata_rata_mahasiswa

def cari_mahasiswa_terbaik_terburuk(rata_rata_mahasiswa):
    # Mencari mahasiswa dengan nilai tertinggi dan terendah
    mahasiswa_terbaik = max(rata_rata_mahasiswa, key=rata_rata_mahasiswa.get)
    mahasiswa_terburuk = min(rata_rata_mahasiswa, key=rata_rata_mahasiswa.get)
    
    return mahasiswa_terbaik, mahasiswa_terburuk
```
Penjelasan :

Fungsi `hitung_rata_rata` digunakan untuk menghitung rata-rata nilai dari setiap mahasiswa yang terdapat dalam dictionary `data_mahasiswa`. Fungsi ini membuat dictionary baru bernama `rata_rata_mahasiswa`, di mana setiap nama mahasiswa menjadi kunci, dan nilai rata-ratanya (hasil dari jumlah nilai dibagi jumlah nilai) menjadi nilai. Setelah semua rata-rata dihitung, fungsi mengembalikan dictionary tersebut.

Fungsi `cari_mahasiswa_terbaik_terburuk` digunakan untuk menentukan mahasiswa dengan nilai tertinggi dan terendah berdasarkan rata-rata nilai yang dihitung sebelumnya. Fungsi ini menggunakan fungsi `max` untuk mencari mahasiswa dengan rata-rata tertinggi dan `min` untuk yang terendah. Keduanya dilakukan dengan menggunakan parameter `key` yang mengacu pada nilai dari dictionary `rata_rata_mahasiswa`. Fungsi ini mengembalikan nama mahasiswa terbaik dan terburuk.

```Python
nama_file = 'siswa_nilai (1).csv'

data_mahasiswa = baca_data_csv(nama_file)

rata_rata_mahasiswa = hitung_rata_rata(data_mahasiswa)

mahasiswa_terbaik, mahasiswa_terburuk = cari_mahasiswa_terbaik_terburuk(rata_rata_mahasiswa)

print("Rata-rata nilai tiap mahasiswa:")
for nama, rata_rata in rata_rata_mahasiswa.items():
    print(f"{nama}: {rata_rata:.2f}")

print(f"\nMahasiswa dengan nilai tertinggi: {mahasiswa_terbaik} dengan rata-rata {rata_rata_mahasiswa[mahasiswa_terbaik]:.2f}")
print(f"Mahasiswa dengan nilai terendah: {mahasiswa_terburuk} dengan rata-rata {rata_rata_mahasiswa[mahasiswa_terburuk]:.2f}")
```
Penjelasan :

Kode ini berfungsi untuk membaca data mahasiswa dari file CSV dan melakukan analisis performa akademis mereka. Pertama, fungsi `baca_data_csv` digunakan untuk mengimpor data ke dalam dictionary bernama `data_mahasiswa`. Selanjutnya, fungsi `hitung_rata_rata` menghitung rata-rata nilai untuk setiap mahasiswa dan menyimpannya dalam dictionary `rata_rata_mahasiswa`. Kemudian, fungsi `cari_mahasiswa_terbaik_terburuk` digunakan untuk menentukan mahasiswa dengan rata-rata nilai tertinggi dan terendah. Terakhir, program menampilkan rata-rata nilai tiap mahasiswa serta nama mahasiswa yang memiliki nilai tertinggi dan terendah, memberikan gambaran ringkas tentang kinerja akademis mereka.

## Hasil output
![Screenshot 2024-09-29 172220](https://github.com/user-attachments/assets/2afc596a-950b-4e77-9c53-1a4ed91e17d3)
![Screenshot 2024-09-29 172246](https://github.com/user-attachments/assets/3baf1c7f-d270-4431-b429-3865123e8da6)
![Screenshot 2024-09-29 172313](https://github.com/user-attachments/assets/618e20cf-d4ef-4fd5-a090-071b54009d2d)

Penjelasan :

Output ini menunjukkan rata-rata nilai untuk setiap mahasiswa yang terdaftar dalam dataset. Untuk setiap siswa, terdapat rata-rata nilai yang dihitung dari nilai-nilai yang mereka peroleh. Dari daftar tersebut, tampak bahwa **Siswa_7** memiliki rata-rata nilai tertinggi yaitu **100.00**, yang menunjukkan bahwa siswa tersebut berhasil mendapatkan nilai sempurna. Sebaliknya, **Siswa_5** memiliki rata-rata nilai terendah yaitu **50.00**, menandakan bahwa siswa ini berada di bawah standar yang diharapkan dalam hal nilai. Analisis ini memberikan gambaran umum tentang kinerja akademis mahasiswa yang dapat digunakan untuk evaluasi lebih lanjut.

## Unguided 5

### 5. [Kombinasi Logika dan Kreativitas]
**Soal**: Buatlah permainan sederhana menggunakan Python, di mana komputer akan memilih sebuah angka secara acak antara 1 hingga 100, dan pengguna harus menebak angka tersebut. Setiap tebakan yang salah akan memberikan petunjuk apakah angka yang ditebak lebih besar atau lebih kecil dari angka sebenarnya. Batasi jumlah percobaan menjadi 5 kali. Setelah permainan selesai, tampilkan apakah pemain menang atau kalah.

```Python
import random

def tebak_angka():
    angka_rahasia = random.randint(1, 100)
    percobaan = 5
    
    print("Selamat datang di permainan Tebak Angka!")
    print("Saya telah memilih sebuah angka antara 1 hingga 100.")
    print(f"Anda memiliki {percobaan} percobaan untuk menebaknya.")

    # Loop untuk percobaan menebak
    for i in range(percobaan):
        try:
            tebakan = int(input(f"Tebakan ke-{i + 1}: "))
            
            if tebakan < 1 or tebakan > 100:
                print("Tebakan harus antara 1 hingga 100. Coba lagi.")
                continue

            if tebakan < angka_rahasia:
                print("Tebakan Anda terlalu kecil.")
            elif tebakan > angka_rahasia:
                print("Tebakan Anda terlalu besar.")
            else:
                print(f"Selamat! Anda menebak angka yang benar: {angka_rahasia}!")
                break
        except ValueError:
            print("Input tidak valid. Silakan masukkan angka.")

    else:  # Jika loop selesai tanpa break, artinya pemain kalah
        print(f"Anda kehabisan percobaan. Angka yang benar adalah: {angka_rahasia}.")
        
# Menjalankan permainan
if __name__ == "__main__":
    tebak_angka()
```
Penjelasan :

Program "Tebak Angka" adalah permainan di mana pemain menebak angka rahasia antara 1 hingga 100. Program memilih angka secara acak dan memberikan pemain 5 percobaan untuk menebak. Setiap tebakan diperiksa; jika tebakan terlalu kecil atau besar, pemain mendapatkan umpan balik. Program juga menangani kesalahan input non-angka. Jika pemain menebak dengan benar, mereka menang, tetapi jika kehabisan percobaan, angka rahasia diungkapkan. Program ini mengilustrasikan pengendalian alur, penanganan kesalahan, dan interaksi pengguna dalam Python.

## Hasil output 
![Screenshot 2024-09-29 172453](https://github.com/user-attachments/assets/545d5152-3ac2-4496-886f-8a084a2e99cb)

Penjelasan :

Pemain mencoba menebak angka rahasia antara 1 hingga 100 dengan total 5 percobaan. 

- Pada percobaan pertama, tebakan **2** terlalu kecil. 
- Kedua, **70** terlalu besar. 
- Ketiga, **53** juga terlalu besar. 
- Keempat, **12** masih terlalu kecil. 
- Kelima, **43** terlalu besar.

Setelah 5 percobaan, pemain tidak berhasil menebak angka rahasia, yaitu **41**, dan program menginformasikan bahwa mereka telah kehabisan percobaan.

## Unguided 6

### 6. [Rekursi yang Tidak Biasa]
**Soal**: Buat fungsi rekursif yang menerima input bilangan bulat `n` dan menghasilkan urutan bilangan seperti berikut ini:

```Python
def faktorial(n):
    """Fungsi rekursif untuk menghitung faktorial dari n."""
    if n == 0 or n == 1:
        return 1
    else:
        return n * faktorial(n - 1)

def urutan_faktorial(n):
    """Fungsi untuk menghasilkan urutan faktorial dari 1 hingga n."""
    if n < 1:
        return []
    else:
        # Memanggil urutan_faktorial untuk n-1 dan menambahkan faktorial n
        return urutan_faktorial(n - 1) + [faktorial(n)]

# Contoh penggunaan
n = 4
output = urutan_faktorial(n)
print(output)  # Output: [1, 1, 2, 6, 24]
```
Penjelasan :

Program di atas terdiri dari dua fungsi: 

1. **`faktorial(n)`**: Menghitung faktorial dari bilangan bulat non-negatif `n` secara rekursif. Jika `n` adalah 0 atau 1, fungsi mengembalikan 1; jika tidak, fungsi mengalikan `n` dengan faktorial dari `n - 1`.

2. **`urutan_faktorial(n)`**: Menghasilkan daftar yang berisi faktorial dari 1 hingga `n`. Jika `n` kurang dari 1, mengembalikan daftar kosong; jika tidak, memanggil dirinya sendiri untuk `n - 1` dan menambahkan faktorial dari `n` ke hasilnya.

Pada contoh penggunaan dengan `n = 4`, outputnya adalah `[1, 2, 6, 24]`, yang merupakan faktorial dari 1, 2, 3, dan 4.

## Hasil output 
![Screenshot 2024-09-29 172542](https://github.com/user-attachments/assets/12c7f291-d141-4ed3-a6ea-10b2601773a4)

Penjelasan :

Output `[1, 2, 6, 24]` menunjukkan urutan faktorial dari angka 1 hingga 4, dihasilkan oleh fungsi `urutan_faktorial`. Rincian dari output ini adalah:

- **1! = 1**
- **2! = 2**
- **3! = 6**
- **4! = 24**

Masing-masing elemen dalam daftar adalah hasil dari menghitung faktorial untuk setiap bilangan bulat dari 1 hingga 4.

## Unguided 7

### 7. [ Pemrograman dengan Algoritma Greedy]
**Soal**: Buatlah program untuk memecahkan masalah "minimum coin change". Diberikan jumlah uang dan daftar nilai koin yang tersedia (misalnya, 1, 5, 10, 25), tentukan kombinasi minimum koin yang diperlukan untuk mencapai jumlah uang tersebut. Namun, program Anda harus bisa menangani koin-koin yang nilai dan jumlahnya ditentukan pengguna.

![Screenshot 2024-09-29 172621](https://github.com/user-attachments/assets/f8fdf0a1-9718-4b75-88fa-249d69a2771e)
![Screenshot 2024-09-29 172710](https://github.com/user-attachments/assets/a4f9bb5c-e741-42a8-ae8c-f19d8f30333a)

```Python
def min_coin_change(amount, coins):
    """Menghitung kombinasi minimum koin yang diperlukan untuk mencapai jumlah tertentu."""
    # Mengurutkan koin dari yang terbesar ke yang terkecil
    coins.sort(reverse=True)
    
    # Menyimpan jumlah koin yang digunakan
    coin_count = {}
    
    for coin in coins:
        if amount == 0:
            break
        
        # Menghitung jumlah koin yang bisa digunakan
        count = amount // coin
        if count > 0:
            coin_count[coin] = count
            amount -= coin * count
            
    if amount > 0:
        print("Tidak mungkin mencapai jumlah uang tersebut dengan koin yang tersedia.")
    else:
        print("Kombinasi koin yang diperlukan:")
        for coin, count in coin_count.items()
```
Penjelasan :

Fungsi `min_coin_change` menghitung kombinasi minimum koin yang diperlukan untuk mencapai jumlah tertentu (amount) menggunakan daftar koin yang diberikan. Fungsi ini bekerja dengan langkah-langkah berikut:

1. **Pengurutan Koin**: Koin diurutkan dari yang terbesar ke yang terkecil untuk memaksimalkan nilai koin yang digunakan dan mengurangi jumlah koin yang diperlukan.

2. **Inisialisasi**: Sebuah dictionary `coin_count` digunakan untuk menyimpan jumlah setiap jenis koin yang digunakan.

3. **Iterasi Koin**: Untuk setiap koin, jika jumlah yang tersisa (`amount`) tidak sama dengan nol, fungsi menghitung berapa banyak koin dari nilai tersebut yang dapat digunakan. Ini dilakukan dengan pembagian integer (`amount // coin`).

4. **Pembaruan Jumlah**: Jika ada koin yang dapat digunakan, jumlah koin tersebut ditambahkan ke `coin_count`, dan `amount` diperbarui dengan mengurangkan nilai total koin yang digunakan.

5. **Cek Sisa Jumlah**: Jika setelah proses semua koin jumlah yang tersisa masih lebih dari nol, maka dicetak pesan bahwa jumlah tersebut tidak dapat dicapai dengan koin yang tersedia. Jika tidak, kombinasi koin yang diperlukan dicetak.

Fungsi ini efektif dalam memberikan solusi untuk masalah perubahan uang menggunakan metode greedy.

```Python
def main():
    # Meminta input jumlah uang dan daftar koin
    try:
        amount = int(input("Masukkan jumlah uang yang ingin dicapai: "))
        coins_input = input("Masukkan nilai koin yang tersedia (pisahkan dengan spasi): ")
        coins = list(map(int, coins_input.split()))

        if amount < 0:
            print("Jumlah uang tidak boleh negatif.")
            return
        
        if not coins:
            print("Daftar koin tidak boleh kosong.")
            return

        min_coin_change(amount, coins)
    
    except ValueError:
        print("Input tidak valid. Pastikan Anda memasukkan angka untuk jumlah uang dan nilai koin.")

# Menjalankan program
if __name__ == "__main__":
    main()
```
Penjelaan :

Fungsi `main()` bertanggung jawab untuk menjalankan program dan mengelola interaksi dengan pengguna. Berikut adalah penjelasan singkat mengenai fungsinya:

1. **Input Pengguna**: Program meminta pengguna untuk memasukkan jumlah uang yang ingin dicapai dan daftar nilai koin yang tersedia. Nilai koin dimasukkan dalam bentuk string yang dipisahkan dengan spasi.

2. **Validasi Input**:
   - Program memeriksa apakah jumlah uang yang dimasukkan negatif. Jika iya, akan mencetak pesan bahwa jumlah uang tidak boleh negatif dan keluar dari fungsi.
   - Program juga memeriksa apakah daftar koin kosong. Jika kosong, akan mencetak pesan bahwa daftar koin tidak boleh kosong dan keluar dari fungsi.

3. **Menggunakan Fungsi `min_coin_change`**: Jika semua input valid, fungsi `min_coin_change()` dipanggil dengan argumen `amount` dan `coins` untuk menghitung kombinasi minimum koin yang diperlukan.

4. **Penanganan Kesalahan**: Program menggunakan blok `try-except` untuk menangani kesalahan konversi input. Jika pengguna memasukkan nilai yang tidak valid (misalnya, huruf alih-alih angka), program akan mencetak pesan kesalahan yang sesuai.

Dengan menggunakan struktur ini, program dapat memastikan bahwa pengguna memberikan input yang valid sebelum melakukan perhitungan, sehingga meningkatkan pengalaman pengguna dan mencegah kesalahan runtime.

## Hasil output 
![Screenshot 2024-09-29 172738](https://github.com/user-attachments/assets/09309488-d473-4c80-91a0-49f72f0c3002)

Penjelasan :

Output dari program menunjukkan hasil dari fungsi `min_coin_change()` setelah pengguna memasukkan jumlah uang yang ingin dicapai dan nilai koin yang tersedia. Berikut adalah penjelasan singkat:

1. **Input**: Pengguna memasukkan `1000000` sebagai jumlah uang yang ingin dicapai dan koin dengan nilai `10` dan `000`. Namun, nilai koin `000` secara teknis dianggap sebagai `0`, tetapi saat diproses, koin `0` tidak mempengaruhi hasil.

2. **Proses**: 
   - Program mengurutkan koin dari yang terbesar ke terkecil, tetapi dalam kasus ini hanya `10` yang valid.
   - Menggunakan koin `10`, program menghitung berapa banyak koin yang dibutuhkan untuk mencapai jumlah `1000000`. 
   - Dengan melakukan perhitungan, didapatkan bahwa `100000` koin `10` dibutuhkan, karena \( 10 \times 100000 = 1000000 \).

3. **Output**: Program mencetak bahwa diperlukan `100000` buah koin `10` untuk mencapai jumlah uang `1000000`. 

Ini menunjukkan bahwa algoritme berhasil menghitung kombinasi minimum koin yang diperlukan berdasarkan input pengguna, meskipun koin `000` tidak memiliki efek dalam perhitungan.

## Unguided 8

### 8. [Kombinasi String dan Manipulasi List]
**Soal**: Buat sebuah program yang menerima string dari pengguna dan mengonversi string tersebut menjadi sebuah list berisi kata-kata terbalik. Misalnya

![Screenshot 2024-09-29 172801](https://github.com/user-attachments/assets/d0f369f5-ba35-4d40-b2b6-69e8fa6e8cb7)

```Python
def reverse_words(input_string):
    """Mengonversi string menjadi list berisi kata-kata yang terbalik."""
    # Memecah string menjadi kata-kata
    words = input_string.split()
    
    # Membalik setiap kata dan menyimpannya dalam list
    reversed_words = [word[::-1] for word in words]
    
    return reversed_words
```
Penjelasan :

Fungsi `reverse_words(input_string)` membalik setiap kata dalam string yang diberikan. Fungsi ini memecah string menjadi list kata-kata menggunakan metode `.split()`, kemudian membalik setiap kata dengan slicing `[::-1]`, dan akhirnya mengembalikan list yang berisi kata-kata yang telah dibalik. Contohnya, input `"Hello World"` akan menghasilkan output `['olleH', 'dlroW']`.

```Python
def main():
    # Meminta input dari pengguna
    user_input = input("Masukkan string: ")
    
    # Mengonversi dan menampilkan hasil
    result = reverse_words(user_input)
    print(result)

# Menjalankan program
if __name__ == "__main__":
    main()
```
Penjelasan :

Fungsi `main()` meminta input dari pengguna berupa string, kemudian menggunakan fungsi `reverse_words()` untuk membalik setiap kata dalam string tersebut. Setelah itu, hasilnya ditampilkan ke layar. Program ini berjalan dengan memeriksa apakah file dieksekusi sebagai program utama dan menjalankan fungsi `main()`. Misalnya, jika pengguna memasukkan string `"Halo Dunia"`, outputnya akan berupa `['olaH', 'ainuD']`.

## Hasil output 
![Screenshot 2024-09-29 172838](https://github.com/user-attachments/assets/fc7ac63b-1ee2-4b17-b1c0-5b609fbfbc8e)

Penjelasan :

Output `['uka', 'akus', 'haub']` menunjukkan bahwa setiap kata dalam string yang dimasukkan, yaitu "aku suka buah", telah dibalik. 

- Kata "aku" menjadi "uka".
- Kata "suka" menjadi "akus".
- Kata "buah" menjadi "haub".

Dengan demikian, fungsi `reverse_words()` berhasil mengonversi dan membalik setiap kata dalam string yang diberikan oleh pengguna.

## Unguided 9

### 9. Konsep Class dan Object-Oriented Programming]
**Soal**: Buat class bernama `Buku` yang memiliki atribut `judul`, `penulis`, dan `tahun_terbit`. Buat method dalam class untuk menampilkan informasi buku, serta method untuk menghitung usia buku berdasarkan tahun saat ini. Buatlah 3 objek dari class `Buku` dan tampilkan informasi serta usia masing-masing buku.

![Screenshot 2024-09-29 172937](https://github.com/user-attachments/assets/9454aa61-9892-4f87-bda5-e9f26a861317)
![Screenshot 2024-09-29 173009](https://github.com/user-attachments/assets/8d366dc9-24f8-4ad0-b82d-a29a6975a18b)

```Python
class Buku:
    def __init__(self, judul, penulis, tahun_terbit):
        """Inisialisasi atribut judul, penulis, dan tahun terbit."""
        self.judul = judul
        self.penulis = penulis
        self.tahun_terbit = tahun_terbit

    def tampilkan_informasi(self):
        """Menampilkan informasi buku."""
        print(f"Judul: {self.judul}")
        print(f"Penulis: {self.penulis}")
        print(f"Tahun Terbit: {self.tahun_terbit}")

    def hitung_usia_buku(self, tahun_sekarang):
        """Menghitung usia buku berdasarkan tahun saat ini."""
        return tahun_sekarang - self.tahun_terbit
```
Penjelasan :

Kelas `Buku` adalah representasi objek buku yang memiliki atribut untuk menyimpan informasi seperti judul, penulis, dan tahun terbit. 

1. **Inisialisasi**: Kelas ini menggunakan metode `__init__` untuk menginisialisasi tiga atribut: `judul`, `penulis`, dan `tahun_terbit`.

2. **Menampilkan Informasi**: Metode `tampilkan_informasi` mencetak detail buku ke layar, termasuk judul, penulis, dan tahun terbit.

3. **Menghitung Usia Buku**: Metode `hitung_usia_buku` menerima parameter `tahun_sekarang` dan mengembalikan selisih antara tahun saat ini dan tahun terbit buku, yang menunjukkan berapa lama buku tersebut sudah diterbitkan. 

Dengan menggunakan kelas ini, pengguna dapat dengan mudah membuat objek buku dan mengakses informasi serta menghitung usia buku tersebut.

```Python
def main():
    # Tahun saat ini
    tahun_sekarang = int(input("Masukkan tahun saat ini: "))

    # Memasukkan informasi buku melalui input
    jumlah_buku = int(input("Berapa buku yang ingin Anda masukkan? "))

    buku_list = []
    
    for i in range(jumlah_buku):
        print(f"\nMasukkan informasi buku ke-{i + 1}:")
        judul = input("Masukkan judul buku: ")
        penulis = input("Masukkan penulis buku: ")
        tahun_terbit = int(input("Masukkan tahun terbit buku: "))
        buku = Buku(judul, penulis, tahun_terbit)
        buku_list.append(buku)

    # Menampilkan informasi dan usia setiap buku
    for buku in buku_list:
        buku.tampilkan_informasi()
        usia = buku.hitung_usia_buku(tahun_sekarang)
        print(f"Usia Buku: {usia} tahun\n")

# Menjalankan program
if __name__ == "__main__":
    main()
```
Penjelasan :

Fungsi `main` dalam kode ini berfungsi untuk mengelola interaksi pengguna dalam memasukkan dan menampilkan informasi buku. Berikut adalah penjelasan singkat mengenai setiap bagian:

1. **Input Tahun Sekarang**: Program meminta pengguna untuk memasukkan tahun saat ini, yang akan digunakan untuk menghitung usia buku.

2. **Input Jumlah Buku**: Pengguna diminta untuk memasukkan jumlah buku yang ingin mereka daftarkan.

3. **Pengumpulan Data Buku**:
   - Program membuat list kosong `buku_list` untuk menyimpan objek buku.
   - Dalam loop, pengguna memasukkan informasi untuk setiap buku, termasuk judul, penulis, dan tahun terbit. Setiap informasi buku ini digunakan untuk membuat objek `Buku`, yang kemudian ditambahkan ke dalam `buku_list`.

4. **Menampilkan Informasi Buku**: Setelah semua informasi buku dimasukkan, program akan menampilkan detail setiap buku dengan memanggil metode `tampilkan_informasi()` dari objek buku. Program juga menghitung dan menampilkan usia buku menggunakan metode `hitung_usia_buku()`.

Dengan cara ini, program memungkinkan pengguna untuk dengan mudah memasukkan dan melihat informasi tentang beberapa buku serta menghitung berapa tahun buku tersebut telah diterbitkan.

## Hasil output 
![Screenshot 2024-09-29 173045](https://github.com/user-attachments/assets/cc84ca32-8893-43d7-ab15-ec9e7b305bc6)

Penjelasan :

Output di atas menunjukkan hasil dari program yang dijalankan, di mana pengguna berhasil memasukkan informasi untuk dua buku. Berikut adalah rincian proses dan hasilnya:

1. **Input Tahun Saat Ini**: Pengguna memasukkan tahun saat ini, yaitu **2024**.

2. **Input Jumlah Buku**: Pengguna memilih untuk memasukkan **2** buku.

3. **Informasi Buku Pertama**:
   - Judul: **3726 mdpl**
   - Penulis: **monn**
   - Tahun Terbit: **2012**
   - Program kemudian menghitung usia buku ini dengan mengurangkan tahun terbit dari tahun sekarang (2024 - 2012 = 12). Jadi, usia buku ini adalah **12 tahun**.

4. **Informasi Buku Kedua**:
   - Judul: **Art**
   - Penulis: **Aji**
   - Tahun Terbit: **2011**
   - Program menghitung usia buku ini dengan cara yang sama (2024 - 2011 = 13). Oleh karena itu, usia buku ini adalah **13 tahun**.

5. **Output Akhir**:
   - Program menampilkan informasi lengkap untuk kedua buku, termasuk judul, penulis, tahun terbit, dan usia masing-masing buku.

Program ini memberikan ringkasan yang jelas tentang buku-buku yang dimasukkan, serta menunjukkan kemampuan untuk menghitung usia buku berdasarkan tahun yang diberikan.

## Unguided 10

### 10. [Algoritma dengan Persyaratan Logika Khusus]
**Soal**: Buatlah program yang mengimplementasikan algoritma pencarian biner, namun dengan modifikasi: algoritma harus bisa mencari nilai di list yang hanya berisi angka genap, dan jika nilai yang dicari adalah angka ganjil, program harus menampilkan pesan bahwa nilai tersebut tidak bisa ditemukan.

![Screenshot 2024-09-29 173111](https://github.com/user-attachments/assets/21b9d1fd-8383-456e-bae7-2f69716f8850)

![Screenshot 2024-09-29 173146](https://github.com/user-attachments/assets/531733e5-3622-413f-bb68-655b87a14808)

```Python
def binary_search_even(arr, target):
    # Cek apakah target adalah angka ganjil
    if target % 2 != 0:
        print(f"Nilai {target} adalah angka ganjil, tidak dapat ditemukan dalam list genap.")
        return -1 

    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2
        # Cek apakah nilai tengah adalah target
        if arr[mid] == target:
            return mid
        # Jika target lebih kecil, abaikan setengah kanan
        elif arr[mid] > target:
            high = mid - 1
        # Jika target lebih besar, abaikan setengah kiri
        else:
            low = mid + 1

    # Jika nilai tidak ditemukan
    return -1
```
Penjelasan :

Fungsi `binary_search_even` melakukan pencarian biner untuk menemukan indeks dari angka genap dalam sebuah daftar. Pertama, ia memeriksa apakah `target` adalah angka ganjil; jika ya, fungsi mengembalikan -1. Kemudian, fungsi menggunakan pendekatan pencarian biner, membagi daftar menjadi dua bagian hingga menemukan `target` atau kehabisan elemen untuk dicari. Jika angka ditemukan, indeksnya dikembalikan; jika tidak, -1 dikembalikan sebagai tanda bahwa angka tidak ada dalam daftar. Pencarian ini efisien, dengan kompleksitas waktu O(log n).

```Python
def main():
    # Masukkan list genap (sorted) dari input pengguna
    list_genap = list(map(int, input("Masukkan angka genap yang dipisahkan oleh spasi: ").split()))
    
    # Validasi untuk memastikan hanya angka genap
    list_genap = [x for x in list_genap if x % 2 == 0]
    
    # Memasukkan target yang ingin dicari
    target = int(input("Masukkan angka yang ingin dicari: "))

    # Memanggil fungsi binary_search_even
    result = binary_search_even(list_genap, target)

    if result != -1:
        print(f"Nilai {target} ditemukan di indeks {result}.")
    else:
        print(f"Nilai {target} tidak ditemukan di dalam list.")

# Menjalankan program
if __name__ == "__main__":
    main()
```
Penjelasan :

Fungsi `main` mengatur interaksi pengguna untuk melakukan pencarian biner angka genap dalam sebuah daftar. Pertama, pengguna diminta untuk memasukkan daftar angka genap yang dipisahkan oleh spasi, yang kemudian diubah menjadi list dari tipe integer. Fungsi ini memvalidasi input dengan memastikan hanya angka genap yang disimpan dalam `list_genap`. Selanjutnya, pengguna diminta untuk memasukkan angka yang ingin dicari. Fungsi `binary_search_even` kemudian dipanggil untuk mencari angka tersebut dalam daftar. Hasil pencarian ditampilkan, dengan informasi tentang apakah angka ditemukan beserta indeksnya jika ada. Program ini efektif untuk mencari angka dalam daftar yang telah diurutkan dan berisi hanya angka genap.

## Hasil output 
![Screenshot 2024-09-29 173213](https://github.com/user-attachments/assets/dbd03ba7-e621-4ce2-aa6c-d52abbf4b452)

Penjelasan :

Dalam output tersebut, pengguna pertama kali memasukkan daftar angka genap `2 4 6 8 10`, yang diproses dan disimpan dalam list. Setelah itu, pengguna mencari angka `4`. Program kemudian menggunakan fungsi `binary_search_even` untuk mencari angka tersebut dalam list. Hasilnya menunjukkan bahwa angka `4` ditemukan di indeks `1`, yang berarti angka tersebut berada di posisi kedua dalam list (karena indeks dimulai dari 0). Ini mengindikasikan bahwa pencarian biner berfungsi dengan baik untuk menemukan angka dalam daftar yang telah diurutkan.

## Kesimpulan

Python merupakan bahasa pemrograman yang penting dalam sains data, menawarkan kemudahan penggunaan dan pustaka yang kuat[2]. Dalam memahami Python, penting untuk mengenal variabel dan tipe data dasar seperti `int`, `float`, `str`, dan `bool` yang digunakan untuk menyimpan informasi. Struktur data, termasuk `list`, `dictionary`, `tuple`, dan `set`, membantu dalam pengelompokan data. Kontrol alur menggunakan `if-else` dan looping seperti `for` dan `while` memungkinkan pengambilan keputusan dan iterasi. Fungsi di Python memungkinkan modularisasi kode, sehingga lebih terstruktur dan mudah dibaca. Pustaka-pustaka seperti NumPy, Pandas, dan Matplotlib mendukung komputasi numerik, analisis data, dan visualisasi[5]. Selain itu, kemampuan untuk membaca dan menulis data menggunakan Pandas, termasuk file CSV, sangat berguna. Jupyter Notebook menjadi alat interaktif yang ideal untuk eksplorasi, analisis, dan visualisasi data secara real-time. Dengan memahami konsep-konsep ini, individu dapat membangun fondasi yang kuat dalam sains data[4].

## Referensi

[1] Karimah Tauhid, Volume 2 Nomor 1 (2023), e-ISSN 2963-590X | Alfarizi et al.

[2] Romzi1, M. (2020). PEMBELAJARAN PEMROGRAMAN PYTHON DENGAN PENDEKATAN LOGIKA ALGORITMA. 37-44.

[3] Raihan Muhammad1*, S. Y. (2023). PENERAPAN PEMROGRAMAN PYTHON DALAM MENENTUKAN WAKTU OVERHOUL KONDENSOR TURBIN UAP. 49-57.

[4] Trie Maya Kadarina, M. H. (2019). PENGENALAN BAHASA PEMROGRAMAN PYTHON MENGGUNAKAN APLIKASI GAMES UNTUK SISWA/I DI WILAYAH KEMBANGAN UTARA. 11-16.

[5] Wilyani, F. (2024). Pengenalan Dasar Pemrograman Python Dengan Google Colaboratory . 08-14
