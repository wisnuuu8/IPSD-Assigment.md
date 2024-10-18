# <h1 align="center">Laporan Praktikum Modul exploratory data analysis</h1>
<p align="center">Wisnu Aji Sanjaya</p>

## Dasar Teori
 
**Exploratory Data Analysis (EDA)** adalah metode statistik yang digunakan untuk menganalisis data dengan tujuan memahami struktur, pola, dan karakteristik utamanya sebelum melanjutkan ke pemodelan yang lebih kompleks. Tujuan utama EDA adalah mengeksplorasi data untuk mendeteksi pola, mengidentifikasi anomali, menguji asumsi, dan memvalidasi hipotesis yang relevan. Dalam EDA, salah satu langkah awal adalah memahami struktur data, termasuk tipe-tipe variabel, seperti numerik atau kategorikal, dan bagaimana distribusi data tersebut, apakah mengikuti distribusi normal atau tidak.

Statistik deskriptif sering digunakan dalam EDA untuk merangkum informasi dasar dari data, misalnya ukuran pemusatan seperti mean, median, dan mode, serta ukuran dispersi seperti standar deviasi dan variansi. Selain itu, visualisasi data memegang peranan penting dalam EDA karena membantu mempermudah pemahaman data. Grafik seperti histogram, boxplot, dan scatterplot digunakan untuk menggambarkan distribusi, mendeteksi outlier, dan mengidentifikasi hubungan antara variabel. Outlier, atau nilai yang menyimpang secara signifikan dari data lain, sering terdeteksi melalui visualisasi ini dan menjadi bahan analisis lebih lanjut apakah harus dipertahankan, dihapus, atau disesuaikan.

Selain itu, EDA juga memfokuskan diri pada analisis korelasi untuk menemukan hubungan antara variabel, seperti menggunakan korelasi Pearson untuk data numerik yang berdistribusi normal dan korelasi Spearman untuk data ordinal. EDA juga mencakup penanganan data yang hilang (missing data) yang dapat diatasi dengan cara menghapus data yang tidak lengkap atau mengisi nilai yang hilang dengan metode tertentu. Pada akhirnya, tujuan utama EDA adalah memberikan pemahaman awal yang mendalam tentang data sehingga dapat digunakan untuk membangun model, menguji hipotesis, atau menjawab pertanyaan penelitian dengan lebih tepat dan akurat.

## GUIDED

## Bagian 1
```Python
!pip install wordcloud
!pip install imblearn
!pip install matplotlib
!pip install seaborm
```
## HASIL OUTPUT 
![image](https://github.com/user-attachments/assets/b21bc4ed-d7b5-4d81-b6d3-a2332999599c)

## Bagian 2
```Python
import pandas as pd
import numpy as np 
import matplotlib.pyplot as plt 
import seaborn as sns 

from sklearn.impute import KNNImputer 
from sklearn.preprocessing import StandardScaler 
from imblearn.over_sampling import SMOTE
from wordcloud import WordCloud
```

## Bagian 3
```Python
df = pd.read_csv('diabetes.csv')
df.head(10)
```
## Hasil output 
![image](https://github.com/user-attachments/assets/3a1fbe15-b2b1-465c-bb07-41f4899e6e24)

## Bagian 4
```Python
df.info()
```
## Hasil output 
![image](https://github.com/user-attachments/assets/472b758e-3bfa-4ffa-bd70-b1fce2d5e18e)

## Bagian 5
```Python
(df.isnull().sum()/len(df))*100
```
## Hasil output
![image](https://github.com/user-attachments/assets/5b3b74da-4e1f-47c2-ac76-0cbee139e30c)

## Bagian 6
```Python
# Function to count outliers using IQR
def count_outliers_iqr(data):
    Q1 = data.quantile(0.25)
    Q3 = data.quantile(0.75)
    IQR = Q3 - Q1
    lower_bound = Q1 - 1.5 * IQR 
    upper_bound = Q3 + 1.5 * IQR 
    return ((data < lower_bound) | (data > upper_bound)).sum()

# Count outliers in each numerical column
outlier_counts = {}
for col in df.select_dtypes(include=['int64', 'float64']).columns:
    outlier_counts[col] = count_outliers_iqr(df[col])

# Convert the outlier counts dictionary to a DataFrame
outlier_counts_df = pd.DataFrame(list(outlier_counts.items()),
                                columns=['column', 'outlier_count'])

# Display the outlier counts DataFrame
outlier_counts_df
```
## Hasil output
![image](https://github.com/user-attachments/assets/6e625ac8-b742-404b-b161-9b46b3f1a78b)

## Bagian 7
```Python
df['Outcome'].value_counts()
```
## Hasil output
![image](https://github.com/user-attachments/assets/3ef8f97e-3119-4023-aca7-602a264e5c3c)

## Bagiann 8
```Python
sns.countplot(data=df, y='Outcome')
```
## Hasil output
![image](https://github.com/user-attachments/assets/b4e15eda-1e5f-4dc2-bcf1-1dd2a6922f35)

## Bagian 9
```Python
df.hist(bins=20, figsize=(15, 10), layout=(3, 3), 
        color='purple')
plt.suptitle('Histogram of Pima Indian Diabetes Dataset Features', 
             fontsize=16)
plt.show()
```
## Hasil output 
![image](https://github.com/user-attachments/assets/4e26ca32-771e-4393-a901-164fe9c188e7)
![image](https://github.com/user-attachments/assets/1b4ea5a8-e179-4bc5-99b0-c73da35f717c)

## Bagian 10
```Python
def plot_boxplots(data):
    plt.figure(figsize=(15, 10))  # Correct the typo in figsize
    for i, column in enumerate(data.columns[:-1]):  # Iterate through columns except the last one
        plt.subplot(3, 3, i + 1)  # Create subplots in a 3x3 grid
        sns.boxplot(x='Outcome', y=column, data=data)  # Plot boxplot for each feature
        plt.title(f'Box Plot of {column} by Diabetes Outcome')  # Add title for each plot
    plt.tight_layout()
    plt.show()

plot_boxplots(df)
```
## Hasil output
![image](https://github.com/user-attachments/assets/c8918ae0-e4e9-45d5-b6f1-c538cb73d911)
![image](https://github.com/user-attachments/assets/1f63cbba-e944-4fdd-8209-2a5e47e58377)

## Bagian 11
```Python
sns.heatmap(df.corr(), annot=True, cmap='coolwarm' ,
            square=True, cbar_kws = {"shrink": .8})
```
## Hasil output
![image](https://github.com/user-attachments/assets/86591bb2-80a0-4a2b-9522-90557c62992e)

## Bagian 12
```Python
df_text = pd.read_excel('foodreviews.xlsx')
df_text.head(3)
```
## Hasil output
![image](https://github.com/user-attachments/assets/a602fe38-86b2-4d75-b407-1a8e9be5636a)

## Bagian 13
```Python
text = " ".join(review for review in df_text.Text)

def plot_wordcloud(text):
    wordcloud = WordCloud(width=800, height=400, 
                          background_color='yellow', 
                          colormap='viridis').generate(text)  # Close parentheses here
    
    plt.figure(figsize=(10, 5))  # Correct figsize
    plt.imshow(wordcloud, interpolation='bilinear')
    plt.axis('off')  # Hide axis
    plt.title('Word Cloud of Reviews', fontsize=16)
    plt.show()

plot_wordcloud(text)
```
## Hasil output
![image](https://github.com/user-attachments/assets/6ba42909-10f1-49ed-9d41-bad5b628deb0)

## Bagian 14
```Python
imputer = KNNImputer(n_neighbors=5)
df = pd.DataFrame(imputer.fit_transform(df), columns=df.columns)
```
```Python
x=df.drop('Outcome', axis=1)
y=df['Outcome']
```
```Python
smote = SMOTE(random_state=24)
x_resample, y_resample = smote.fit_resample(x, y)
```

## Bagian 15
```Python
sns.countplot(data=x_resample, y=y_resample)
```
## Hasil output
![image](https://github.com/user-attachments/assets/6fa649a6-4f86-4b92-b235-8294188c139d)

## Bagian 14
```Python
df.head(3)
```
## Hasil output
![image](https://github.com/user-attachments/assets/bd33d637-d07a-40cf-af99-541364eabecb)

## Bagian 15
```Python
scaler = StandardScaler()
df = x_resampled.copy()
df[df.columns.difference(['Outcome'])] = scaler.fit_transform(df[df.columns.difference(['Outcome'])])
```

## Bagian 16
```Python
df.head(3)
```
## Hasil output
![image](https://github.com/user-attachments/assets/74cf9a98-4eae-41c2-86d7-854dde7f6b71)


## UNGUIDED 

## 1. Imputasi missing value dengan mean, median, dan modus
```Python
# Nomor 1
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

file_path = 'diabetes.csv'  
diabetes_data = pd.read_csv(file_path)

print("Dataset Info:")
diabetes_data.info()
print("\nFirst few rows:")
print(diabetes_data.head())

def impute_missing_values(data):
    data_mean_imputed = data.copy()
    data_mean_imputed.fillna(data.mean(), inplace=True)
    
    data_median_imputed = data.copy()
    data_median_imputed.fillna(data.median(), inplace=True)
    
    data_mode_imputed = data.copy()
    for column in data_mode_imputed.columns:
        data_mode_imputed[column].fillna(data_mode_imputed[column].mode()[0], inplace=True)
    
    return data_mean_imputed, data_median_imputed, data_mode_imputed

mean_imputed, median_imputed, mode_imputed = impute_missing_values(diabetes_data)

print("\nMean Imputed Data:")
print(mean_imputed.head())
print("\nMedian Imputed Data:")
print(median_imputed.head())
print("\nMode Imputed Data:")
print(mode_imputed.head())

# Visualizations

plt.figure(figsize=(10,8))
sns.heatmap(mean_imputed.corr(), annot=True, cmap="coolwarm")
plt.title('Correlation Matrix (Mean Imputed Data)')
plt.show()

plt.figure(figsize=(15,10))
for i, column in enumerate(diabetes_data.columns[:-1], 1):  # Exclude 'Outcome'
    plt.subplot(3, 3, i)
    sns.histplot(diabetes_data[column], color='blue', label='Original', kde=True, alpha=0.5)
    sns.histplot(mean_imputed[column], color='red', label='Mean Imputed', kde=True, alpha=0.5)
    plt.title(column)
    plt.legend()

plt.tight_layout()
plt.show()
```
Penjelasan :

Berikut penjelasan singkat kode program di atas:

1. **Membaca Data**: 
   - `diabetes_data = pd.read_csv(file_path)` membaca dataset "diabetes.csv" ke dalam dataframe `diabetes_data`.

2. **Menampilkan Info Dataset**: 
   - `diabetes_data.info()` menampilkan informasi mengenai jumlah data, kolom, dan tipe data.
   - `diabetes_data.head()` menampilkan beberapa baris pertama dari dataset.

3. **Imputasi Nilai Hilang**:
   - Fungsi `impute_missing_values(data)` membuat tiga salinan dataset dengan metode imputasi berbeda:
     - **Mean Imputation**: Mengisi nilai hilang dengan rata-rata setiap kolom.
     - **Median Imputation**: Mengisi nilai hilang dengan median setiap kolom.
     - **Mode Imputation**: Mengisi nilai hilang dengan nilai yang paling sering muncul (mode) pada tiap kolom.
   - Hasilnya adalah tiga dataset: `mean_imputed`, `median_imputed`, dan `mode_imputed`.

4. **Visualisasi Korelasi**:
   - Matriks korelasi dari dataset yang telah diimputasi dengan mean divisualisasikan menggunakan heatmap (`sns.heatmap`).

5. **Visualisasi Histogram**:
   - Dibuat histogram untuk setiap kolom numerik (kecuali kolom terakhir) menggunakan `sns.histplot`, yang membandingkan distribusi data asli (warna biru) dengan data yang diimputasi mean (warna merah).

## Hasil output
![image](https://github.com/user-attachments/assets/a2cb9331-6dd9-490a-9f9f-6d505fab2219)
![image](https://github.com/user-attachments/assets/51d4669a-786f-4997-8c90-b67f83b96d78)
![image](https://github.com/user-attachments/assets/afbbf9fa-d355-4e39-b46b-40e24dbb7b0d)
![image](https://github.com/user-attachments/assets/b5c3e733-c097-4244-b002-5f9570c40517)
![image](https://github.com/user-attachments/assets/be0b7905-b061-46b2-ad71-6aa2c36b1cad)
![image](https://github.com/user-attachments/assets/0ca42535-ad8f-43f1-9bf1-2bbb96041c67)
![image](https://github.com/user-attachments/assets/935aa70c-fe75-48fe-80e3-19c57d0b6e4d)
![image](https://github.com/user-attachments/assets/2f37b601-6eba-4191-9bd7-60c6810e04cc)


Penjelasan :

Output program ini memberikan beberapa informasi penting terkait dataset dan dampak dari metode imputasi nilai yang hilang. Pertama, **informasi dataset** menampilkan jumlah baris, kolom, tipe data, dan apakah ada nilai yang hilang dalam dataset. Hal ini berguna untuk memahami struktur data awal dan mengidentifikasi jika ada nilai yang perlu diimputasi. Selain itu, beberapa baris pertama dataset ditampilkan untuk melihat data secara lebih rinci, termasuk pola data yang mungkin ada.

Selanjutnya, **hasil imputasi** menampilkan tiga versi dataset setelah dilakukan pengisian nilai yang hilang menggunakan metode rata-rata (mean), median, dan mode. Data yang sudah diimputasi ini menampilkan bagaimana setiap metode imputasi mengisi nilai yang hilang dengan cara yang berbeda. Imputasi mean mengisi dengan rata-rata setiap kolom, imputasi median menggunakan nilai tengah, dan imputasi mode menggunakan nilai yang paling sering muncul. Ini memberikan pandangan awal tentang bagaimana masing-masing metode dapat memengaruhi dataset.

Pada bagian **matriks korelasi** dari data yang telah diimputasi dengan mean, hubungan antara variabel-variabel dalam dataset divisualisasikan. Korelasi yang tinggi (baik positif maupun negatif) menunjukkan adanya hubungan yang kuat antara variabel-variabel tersebut. Informasi ini penting untuk menentukan variabel-variabel mana yang saling berhubungan, yang bisa berguna dalam pemodelan atau analisis lebih lanjut.

Terakhir, **histogram perbandingan** menampilkan distribusi data asli dan data yang telah diimputasi menggunakan mean. Warna biru menunjukkan distribusi asli, sedangkan warna merah menunjukkan distribusi setelah imputasi. Dari perbandingan ini, kita dapat melihat bagaimana metode imputasi mean mempengaruhi distribusi setiap kolom. Jika distribusi setelah imputasi sangat berbeda dari data asli, ini bisa menandakan bahwa metode mean mungkin tidak ideal untuk kolom tersebut, terutama jika data aslinya memiliki outlier atau distribusi yang miring. Namun, jika distribusinya tidak banyak berubah, metode imputasi mean mungkin dapat dianggap memadai.

## 2. Cek korelasi antar variabel dengan heatmap
```Python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

file_path = 'diabetes.csv'  
diabetes_data = pd.read_csv(file_path)

diabetes_data.fillna(diabetes_data.mean(), inplace=True)

correlation_matrix = diabetes_data.corr()

print("Correlation Matrix:")
print(correlation_matrix)

plt.figure(figsize=(10, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', linewidths=0.5)
plt.title('Correlation Heatmap of Diabetes Dataset')
plt.show()
```
Penjelasan :

Kode program ini membaca dataset "diabetes.csv" menggunakan `pandas` dan mengisi nilai-nilai yang hilang dengan rata-rata (mean) dari tiap kolom untuk memastikan semua data lengkap dan dapat diproses. Setelah itu, program menghitung matriks korelasi antar variabel numerik menggunakan `data.corr()`, yang menampilkan kekuatan dan arah hubungan linear antar variabel, dengan nilai berkisar antara -1 hingga 1. Matriks korelasi ini kemudian dicetak untuk dianalisis lebih lanjut. Selanjutnya, program menggunakan `seaborn` untuk membuat visualisasi heatmap dari matriks korelasi, di mana warna-warna dalam heatmap menunjukkan kekuatan korelasi, dan anotasi di dalam setiap sel menunjukkan nilai korelasinya. Dengan heatmap ini, kita dapat dengan mudah mengidentifikasi variabel-variabel yang memiliki hubungan signifikan.

## Hasil output
![image](https://github.com/user-attachments/assets/216bf63b-d6ea-4f4a-8850-accb569cf6bc)
![image](https://github.com/user-attachments/assets/f18edc71-4aa0-4f7b-855b-617298e65403)
![image](https://github.com/user-attachments/assets/852884ee-3a5b-4e1c-a76f-d8dc5543f45a)
![image](https://github.com/user-attachments/assets/851f2b92-74c5-4e5e-ba07-76bcc32ed92f)

Penjelasan :

Output dari program ini terdiri dari dua bagian utama: **matriks korelasi** yang dicetak ke layar dan **visualisasi heatmap korelasi**. Matriks korelasi berisi angka-angka yang menunjukkan kekuatan dan arah hubungan linear antara pasangan variabel, dengan nilai berkisar antara -1 hingga 1. Nilai **1** menunjukkan korelasi positif sempurna, artinya kedua variabel naik bersama, sementara **-1** menunjukkan korelasi negatif sempurna, di mana ketika satu variabel naik, yang lainnya turun. Nilai **0** menandakan tidak ada korelasi linear antara dua variabel. Informasi ini sangat penting untuk memahami bagaimana satu variabel berhubungan dengan variabel lainnya; misalnya, dua variabel dengan korelasi mendekati 1 atau -1 menunjukkan hubungan yang kuat, yang dapat berguna dalam analisis lebih lanjut, seperti pemodelan prediktif. Selanjutnya, heatmap memberikan representasi visual dari matriks korelasi, di mana warna menunjukkan kekuatan hubungan: warna merah terang menunjukkan korelasi positif yang kuat, sedangkan biru terang menunjukkan korelasi negatif yang kuat. Anotasi dalam setiap kotak menampilkan nilai korelasi numerik, sehingga kita dapat dengan mudah melihat hubungan spesifik antara variabel-variabel tersebut. Dengan demikian, output ini memberikan gambaran yang jelas tentang hubungan antar variabel dalam dataset, yang membantu dalam pemahaman data dan pengambilan keputusan untuk langkah analisis berikutnya.

## 3. Lakukan imbalance handling dengan undersampling
```Python
import pandas as pd
from sklearn.utils import resample
import seaborn as sns
import matplotlib.pyplot as plt

file_path = 'diabetes.csv'  
diabetes_data = pd.read_csv(file_path)

diabetes_data.fillna(diabetes_data.mean(), inplace=True)

print("Class distribution before undersampling:")
print(diabetes_data['Outcome'].value_counts())

majority_class = diabetes_data[diabetes_data['Outcome'] == 0]
minority_class = diabetes_data[diabetes_data['Outcome'] == 1]

majority_class_undersampled = resample(majority_class, 
                                       replace=False,  
                                       n_samples=len(minority_class),  
                                       random_state=42)

balanced_data = pd.concat([majority_class_undersampled, minority_class])

balanced_data = balanced_data.sample(frac=1, random_state=42).reset_index(drop=True)

print("\nClass distribution after undersampling:")
print(balanced_data['Outcome'].value_counts())

plt.figure(figsize=(10,5))

plt.subplot(1, 2, 1)
sns.countplot(x='Outcome', data=diabetes_data)
plt.title("Before Undersampling")

plt.subplot(1, 2, 2)
sns.countplot(x='Outcome', data=balanced_data)
plt.title("After Undersampling")

plt.tight_layout()
plt.show()
```
Penjelasan :

Kode program ini menganalisis distribusi kelas pada dataset diabetes dan menerapkan teknik **undersampling** untuk menyeimbangkan kelas yang tidak seimbang dalam kolom `Outcome`. Pertama, dataset **"diabetes.csv"** dibaca menggunakan `pandas`, dan nilai yang hilang diisi dengan rata-rata (mean) dari setiap kolom untuk memastikan semua data lengkap sebelum analisis lebih lanjut. Setelah itu, distribusi kelas dicetak untuk menunjukkan jumlah instance dari masing-masing kelas (0 untuk tidak diabetes dan 1 untuk diabetes) sebelum penerapan undersampling. Data kemudian dipisahkan menjadi dua kelas: kelas mayoritas (tidak diabetes) dan kelas minoritas (diabetes). Proses undersampling dilakukan pada kelas mayoritas dengan memilih sejumlah instance yang sama dengan jumlah kelas minoritas, sehingga kedua kelas menjadi seimbang. Setelah itu, kelas mayoritas yang telah diubah digabungkan dengan kelas minoritas untuk membentuk dataset yang seimbang, dan urutan data diacak untuk menghilangkan pola yang mungkin ada. Distribusi kelas setelah penerapan undersampling juga dicetak, yang menunjukkan jumlah instance yang sama untuk kedua kelas. Terakhir, program memvisualisasikan distribusi kelas sebelum dan sesudah undersampling dengan menggunakan plot kolom (`countplot`), sehingga perbandingan antara distribusi kelas dapat dilihat secara jelas. Dengan demikian, program ini berhasil mengatasi masalah ketidakseimbangan kelas yang sering mempengaruhi hasil analisis dan model prediksi.

## Hasil output
![image](https://github.com/user-attachments/assets/95ee2a29-128a-4798-87ae-545778d615cd)
![image](https://github.com/user-attachments/assets/b0f5c2fb-b4eb-4e94-be72-1c3a2a818af9)
Penjelasan :

1. **Distribusi Kelas**:
   - Sebelum undersampling, output mencetak jumlah instance untuk masing-masing kelas dalam kolom `Outcome`. Ini menunjukkan bahwa kelas mayoritas (0 untuk tidak diabetes) memiliki lebih banyak instance dibandingkan kelas minoritas (1 untuk diabetes).
   - Setelah proses undersampling, distribusi kelas dicetak kembali untuk menunjukkan bahwa jumlah instance untuk kedua kelas kini seimbang, yaitu memiliki jumlah yang sama.

2. **Visualisasi Distribusi Kelas**:
   - Visualisasi yang dihasilkan terdiri dari dua subplot. Subplot pertama menampilkan **distribusi kelas sebelum undersampling**, di mana kelas mayoritas terlihat jauh lebih dominan.
   - Subplot kedua menunjukkan **distribusi kelas setelah undersampling**, di mana kedua kelas kini terlihat seimbang dengan jumlah instance yang sama. 

## 4. Lakukan scaling dengan robust scaler dan minmax
```Python
# Nomor 4
import pandas as pd
from sklearn.preprocessing import RobustScaler, MinMaxScaler
import matplotlib.pyplot as plt
import seaborn as sns

file_path = 'diabetes.csv'  # Adjust the file path as needed
diabetes_data = pd.read_csv(file_path)

diabetes_data.fillna(diabetes_data.mean(), inplace=True)

features = diabetes_data.drop(columns=['Outcome'])
target = diabetes_data['Outcome']

robust_scaler = RobustScaler()
features_robust_scaled = robust_scaler.fit_transform(features)

minmax_scaler = MinMaxScaler()
features_minmax_scaled = minmax_scaler.fit_transform(features)

features_robust_scaled_df = pd.DataFrame(features_robust_scaled, columns=features.columns)
features_minmax_scaled_df = pd.DataFrame(features_minmax_scaled, columns=features.columns)

plt.figure(figsize=(15,10))

plt.subplot(3, 1, 1)
sns.histplot(diabetes_data['Pregnancies'], kde=True, color='blue')
plt.title('Original Data Distribution (Pregnancies)')

plt.subplot(3, 1, 2)
sns.histplot(features_robust_scaled_df['Pregnancies'], kde=True, color='green')
plt.title('RobustScaler Transformed Distribution (Pregnancies)')

plt.subplot(3, 1, 3)
sns.histplot(features_minmax_scaled_df['Pregnancies'], kde=True, color='red')
plt.title('MinMaxScaler Transformed Distribution (Pregnancies)')

plt.tight_layout()
plt.show()
```
Penjelasan :

Kode program di atas melakukan normalisasi pada dataset diabetes dengan menggunakan dua teknik skala: **RobustScaler** dan **MinMaxScaler**. Pertama, dataset dibaca dan nilai yang hilang diisi dengan rata-rata kolom. Data fitur dipisahkan dari label target. Kemudian, **RobustScaler** diterapkan untuk mengubah data sehingga median menjadi 0 dan interkuartil range menjadi 1, yang mengurangi pengaruh outlier. Selanjutnya, **MinMaxScaler** diterapkan untuk mengubah nilai menjadi skala antara 0 dan 1. Hasil normalisasi dikonversi kembali menjadi DataFrame untuk analisis lebih lanjut. Program ini juga memvisualisasikan distribusi kolom `Pregnancies` sebelum dan setelah normalisasi dengan menggunakan histogram dan kurva KDE, sehingga perbandingan antara distribusi data asli, serta yang dinormalisasi dengan kedua teknik, dapat dilihat secara jelas.

## Hasil output 
![image](https://github.com/user-attachments/assets/d088f52f-7366-4ad9-90c0-eb03302947f3)
![image](https://github.com/user-attachments/assets/c2e4a49e-31e1-469a-90c6-85b93d58ed78)
Penjelasan :

Output dari kode ini terdiri dari tiga histogram yang menggambarkan distribusi kolom `Pregnancies` dalam dataset diabetes. Histogram pertama menunjukkan distribusi nilai `Pregnancies` sebelum normalisasi, di mana pola distribusi data asli terlihat, dengan kemungkinan adanya outlier atau distribusi yang tidak seimbang. Histogram kedua menampilkan distribusi nilai `Pregnancies` setelah diterapkan **RobustScaler**, yang mengurangi dampak outlier sehingga distribusi menjadi lebih terpusat di sekitar median dengan rentang nilai yang lebih kompak. Sementara itu, histogram ketiga menunjukkan distribusi nilai `Pregnancies` setelah penerapan **MinMaxScaler**, di mana semua nilai berada dalam rentang 0 hingga 1, memberikan skala yang konsisten, meskipun masih mungkin terpengaruh oleh outlier jika ada. Secara keseluruhan, output ini menggambarkan bagaimana kedua teknik normalisasi mempengaruhi distribusi data, yang memungkinkan analisis yang lebih baik pada model pembelajaran mesin yang akan digunakan selanjutnya.


## Kesimpulan

**Exploratory Data Analysis (EDA)** adalah langkah penting dalam analisis data yang bertujuan untuk memahami struktur, pola, dan karakteristik data sebelum pemodelan lebih lanjut. Melalui statistik deskriptif dan visualisasi, EDA membantu mendeteksi pola, anomali, dan outlier, serta menganalisis hubungan antar variabel. EDA juga menangani data yang hilang, sehingga memberikan pemahaman yang mendalam tentang data, yang esensial untuk pengambilan keputusan dan pengembangan model yang akurat.


## REFERENSI














