# Proyek Data Scientist Transaction Behavior Segmentation for Fraud Risk Analysis

## Business Understanding

<img width="1440" height="816" alt="image" src="https://github.com/user-attachments/assets/b1ea3626-66bc-4ab5-a3d6-f62fc0de5501" />

### Latar Belakang 

#### Latar Belakang

## Latar Belakang

Perkembangan layanan perbankan digital telah meningkatkan volume dan kompleksitas transaksi keuangan yang terjadi setiap hari. Seiring dengan meningkatnya aktivitas transaksi melalui berbagai kanal seperti online banking, ATM, dan kantor cabang, risiko terjadinya penipuan (fraud) juga semakin tinggi. Fraud dalam sektor keuangan dapat menyebabkan kerugian finansial yang signifikan bagi institusi maupun nasabah, sehingga diperlukan mekanisme analisis yang mampu mengidentifikasi pola transaksi yang berpotensi mencurigakan secara lebih efektif.

Salah satu tantangan utama dalam mendeteksi fraud adalah keberagaman perilaku transaksi setiap nasabah. Tidak semua transaksi dengan nilai besar atau frekuensi tinggi dapat dikategorikan sebagai aktivitas mencurigakan. Oleh karena itu, diperlukan pendekatan yang mampu mengelompokkan transaksi berdasarkan karakteristik dan pola perilakunya terlebih dahulu sebelum dilakukan proses klasifikasi atau deteksi fraud secara lebih spesifik.

Proyek **Transaction Behavior Segmentation for Fraud Risk Analysis** bertujuan untuk melakukan segmentasi perilaku transaksi menggunakan teknik *clustering* pada dataset yang terdiri dari **2.512 data transaksi**. Dataset ini mencakup berbagai atribut penting seperti nilai transaksi (*TransactionAmount*), jenis transaksi (*TransactionType*), saldo rekening (*AccountBalance*), durasi transaksi (*TransactionDuration*), jumlah percobaan login (*LoginAttempts*), kanal transaksi (*Channel*), serta karakteristik demografis pengguna seperti usia dan pekerjaan. Kombinasi atribut tersebut memberikan gambaran yang komprehensif mengenai perilaku transaksi setiap nasabah.

Melalui proses clustering, transaksi akan dikelompokkan ke dalam beberapa segmen berdasarkan kemiripan pola aktivitas keuangan. Hasil segmentasi ini dapat membantu mengidentifikasi kelompok transaksi dengan karakteristik normal, kelompok berisiko menengah, hingga kelompok yang menunjukkan indikasi perilaku tidak biasa atau berpotensi fraud. Selain memberikan pemahaman yang lebih mendalam terhadap pola transaksi pelanggan, hasil clustering juga dapat digunakan sebagai dasar dalam pengembangan model klasifikasi pada tahap selanjutnya.

Dengan memanfaatkan pendekatan segmentasi perilaku transaksi, institusi keuangan dapat meningkatkan kemampuan pemantauan risiko, mengoptimalkan proses investigasi transaksi mencurigakan, serta mendukung pengambilan keputusan yang lebih cepat dan akurat dalam upaya pencegahan fraud. Oleh karena itu, proyek ini diharapkan mampu menghasilkan segmentasi yang representatif terhadap perilaku transaksi nasabah dan menjadi fondasi yang kuat untuk pengembangan sistem analisis risiko fraud yang lebih cerdas dan efektif.


------------------------------

### Permasalahan Bisnis

#### Permasalahan Bisnis yang Akan Diselesaikan

1. **Perusahaan belum memiliki segmentasi pelanggan berdasarkan perilaku transaksi**, sehingga sulit memahami karakteristik masing-masing kelompok pelanggan.

2. **Sulit mengidentifikasi pelanggan dengan pola transaksi yang berpotensi berisiko**, karena seluruh pelanggan diperlakukan sebagai satu kelompok yang sama.

3. **Belum diketahui kelompok pelanggan mana yang memiliki aktivitas transaksi tinggi, saldo besar, atau pola transaksi yang tidak biasa**, sehingga proses monitoring menjadi kurang efektif.

4. **Kurangnya informasi mengenai perbedaan perilaku transaksi antar pelanggan**, yang dapat menghambat pengambilan keputusan terkait manajemen risiko dan strategi bisnis.

5. **Perusahaan membutuhkan pengelompokan pelanggan yang objektif dan berbasis data** untuk mendukung analisis risiko serta memahami pola transaksi pelanggan secara lebih mendalam.

6. **Belum tersedia label segmentasi pelanggan** yang dapat digunakan sebagai dasar pengembangan model klasifikasi pada tahap selanjutnya untuk mengotomatisasi identifikasi kelompok pelanggan baru.


------------------------------

### Cakupan Proyek

#### Cakupan Proyek

1. Menggunakan dataset transaksi perbankan yang berisi **2.512 data transaksi** dengan atribut transaksi, informasi akun, dan profil pelanggan.

2. Melakukan **data understanding** untuk memahami karakteristik, tipe data, dan distribusi setiap fitur dalam dataset.

3. Melakukan **data preprocessing** yang meliputi pembersihan data, penanganan missing value (jika ada), encoding fitur kategorikal, dan normalisasi/standardisasi fitur numerik.

4. Melakukan **Exploratory Data Analysis (EDA)** untuk mengidentifikasi pola, distribusi data, dan hubungan antar variabel yang relevan terhadap perilaku transaksi pelanggan.

5. Membangun model **K-Means Clustering** untuk mengelompokkan pelanggan berdasarkan karakteristik dan perilaku transaksinya.

6. Menentukan jumlah cluster optimal menggunakan metode evaluasi clustering seperti **Elbow Method** dan **Silhouette Score**.

7. Menganalisis karakteristik setiap cluster untuk memperoleh insight mengenai segmentasi perilaku transaksi pelanggan.

8. Memberikan interpretasi bisnis terhadap hasil segmentasi yang dihasilkan, termasuk identifikasi kelompok pelanggan yang memiliki karakteristik transaksi berbeda.

9. Menghasilkan label cluster yang dapat digunakan sebagai dasar pengembangan model klasifikasi atau sistem analisis risiko pada tahap selanjutnya.

### Di luar cakupan proyek

* Pembuatan model fraud detection secara langsung.
* Prediksi transaksi fraud secara real-time.
* Implementasi sistem ke lingkungan produksi (*deployment*).
* Integrasi dengan sistem perbankan atau database operasional.


------------------------------

### Dataset

**Data source:** https://docs.google.com/spreadsheets/d/e/2PACX-1vTbg5WVW6W3c8SPNUGc3A3AL-AG32TPEQGpdzARfNICMsLFI0LQj0jporhsLCeVhkN5AoRsTkn08AYl/pub?output=csv

----------------------------------

## Insight Hasil Clustering Transaksi

Berdasarkan evaluasi menggunakan K-Means Clustering, jumlah cluster optimal diperoleh pada:

k=5

yang menunjukkan bahwa data transaksi terbagi menjadi lima kelompok utama dengan karakteristik perilaku transaksi yang berbeda.

## Ringkasan Karakteristik Cluster

| Cluster   | Karakteristik Utama                                | Interpretasi                                            |
| --------- | -------------------------------------------------- | ------------------------------------------------------- |
| Cluster 0 | Nilai transaksi tertinggi                          | High transaction customers dengan potensi risiko tinggi |
| Cluster 1 | Saldo rekening tertinggi                           | Wealthy stable customers dengan risiko rendah           |
| Cluster 2 | Durasi transaksi paling lama                       | Potensi aktivitas anomali atau transaksi kompleks       |
| Cluster 3 | Customer muda dengan saldo rendah                  | Low transaction activity customers                      |
| Cluster 4 | Customer berusia lebih tua dengan transaksi stabil | Conservative customers dengan risiko rendah             |

## Insight Utama

Hasil clustering menunjukkan bahwa perilaku transaksi pelanggan memiliki pola yang beragam. Cluster 0 dan Cluster 2 menjadi kelompok yang paling menarik untuk analisis fraud karena memiliki karakteristik transaksi yang tidak normal, seperti nominal transaksi yang sangat tinggi dan durasi transaksi yang lebih lama dibanding cluster lainnya.

Sementara itu, Cluster 1, Cluster 3, dan Cluster 4 menunjukkan pola transaksi yang relatif stabil dan cenderung memiliki risiko lebih rendah.

## Kesimpulan

Metode clustering berhasil mengidentifikasi segmentasi perilaku transaksi pelanggan dan membantu menemukan kelompok transaksi yang berpotensi memiliki risiko fraud atau aktivitas anomali. Hasil ini dapat digunakan sebagai dasar dalam pengembangan sistem fraud monitoring dan risk analysis.

