### Bagian ini masih dalam tahap pengembangan
---
# Validasi Data
Proyek ini hanyalah sebuah validasi data tanpa tindakan lebih lanjut. Validasi Data adalah proses pengecekan dan verifikasi data untuk memastikan apakah data tersebut akurat, konsisten, dan sesuai dengan format atau aturan yang telah ditentukan sebelum digunakan lebih lanjut. Hasil dari proyek ini adalah informasi tentang kesalahan pada dataset ini yang harus ditindak lebih lanjut.

### Tentang dataset
Proyek ini menggunakan dataset 'vgsales' yang merupakan dataset penjualan video games. dataset ini diambil dari platform Kaggle. [Klik untuk mengunjungi Kaggle](https://www.kaggle.com/datasets/kedokedokedo/vgsales).

![Dataframe](Gambar/dataframe.png) <br>

Features pada dataset:
- Rank: Ranking penjualan
- Name: Nama video games
- Platform: Dimana game ini dimainkan/dijual
- Year: Tahun berapa game ini dipublikasikan
- Genre: Genre dari game yang dijual
- Publisher: Publisher game
- Sales features:
  - NA_Sales
  - EU_Sales
  - JP_Sales
  - Other_Sales
  - Global_Sales

### Apa Saja Yang Divalidasi Pada Proyek Ini?
 - Struktur data: apakah tipe datanya sudah sesuai?
 - Missing values: apakah ada data yang value-nya kosong (NaN)?
 - Distribusi data: setelah tipe datanya sesuai, apakah isi datanya juga sudah sesuai? (contoh, gender harusnya hanya ada laki-laki/perempuan. Tidak ada yang lain)
 - Duplikasi data: Memastikan tidak ada data yang 100% sama dengan data lainnya
---

## Struktur Data
![Struktur Data](Gambar/Struktur%20data.png) <br>
Pada bagian struktur data, saya menggunakan fungsi info() untuk melihat struktur secara keseluruhan. Hasil dari inspeksi struktur data ini ditemukan bahwa ada kesalahan pada tipe data kolom 'Year', yang dimana akan lebih cocok jika menggunakan tipe data Integer dibanding Float
___

## Missing Values
![Missing values heatmap](Gambar/Missing%20values%20heatmap.png) <br>
![Missing values sum](Gambar/missing%20values%20sum.png)

Pada bagian missing values, saya mengecek secara singkat menggunakan heatmap untuk melihat gambaran semua missing values yang ada di dataframe. Setalah saya cek kembali menggunakan metode isnull().sum() ditemukan missing values di kolom 'Year' (271 data) dan 'Publisher' (58 data). Berikut ini adalah tampilan sampel data yang terdapat missing values di salah dua kolomnya:

![Missing values data](Gambar/missing%20values%20data.png) <br>
___

## Distribusi Data
Proses pengecekan distribusi data bertujuan untuk melihat apakah ada keanehan pada data di suatu kolom. Pada proses pengecekan distribusi data, saya membagi data menjadi 2 jenis: numerik dan kategorial.

### Kolom Numerik
Pada proses pengecekan kolom numerik saya mengecek distribusi data dan outlayer menggunakan boxplot dan bar chart, berikut ini adalah hasilnya: 

![Distribusi data numeri](Gambar/Distribusi%20data%20(numerik).png) <br>
![Distribusi data numerik boxplot](Gambar/Outlayer%20numerik.png) <br>

Pada saat kita melihat grafik bar chart, tidak akan ada yang tampak aneh. Tetapi jika kita melihat pada grafik boxplot, terdapat beberapa titik yang terpisah dari titik lainnya, biasanya hal ini akan dianggap sebagai outlayer. tetapi pada saat saya cek menggunakan metode IQR (Interquartile Range), hal ini sangat lumrah karena memang dalam dunia video games akan ada game yang sangat hebat penjualannya (hukum tidak tertulis = 20% game menyumbang 80% penjualan), hal tersebut bisa dilihat pada hasil IQR berikut ini:

![IQR](Gambar/IQR%20numerik.png) <br>

## Duplikasi Data
