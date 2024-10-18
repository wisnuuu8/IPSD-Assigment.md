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
















