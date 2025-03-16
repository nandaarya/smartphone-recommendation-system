# Laporan Proyek Machine Learning: Sistem Rekomendasi Smartphone
Untuk memenuhi submission akhir kelas Machine Learning Terapan - Dicoding Academy

---

## Project Overview

### Latar Belakang
Dalam era digital saat ini, smartphone telah menjadi bagian penting dalam kehidupan sehari-hari. Dengan perkembangan teknologi yang pesat, setiap tahun berbagai merek meluncurkan model baru dengan spesifikasi yang semakin beragam. Hal ini membuat konsumen dihadapkan pada banyak pilihan, yang sering kali menyulitkan dalam menentukan perangkat yang paling sesuai dengan kebutuhan dan anggaran mereka. Dalam penelitian yang dilakukan oleh Adomavicius dan Tuzhilin (2005), sistem rekomendasi berbasis data telah terbukti membantu konsumen dalam pengambilan keputusan dengan menyaring informasi yang relevan dan menyajikan pilihan terbaik berdasarkan preferensi individu.

Setiap individu memiliki preferensi yang berbeda dalam memilih smartphone. Ada yang lebih mengutamakan performa tinggi untuk kebutuhan gaming, sementara yang lain lebih memperhatikan kualitas kamera untuk fotografi. Beberapa pengguna mungkin lebih mencari keseimbangan antara daya tahan baterai, desain yang ringan, dan harga yang terjangkau untuk penggunaan sehari-hari. Dengan semakin kompleksnya spesifikasi dan fitur yang ditawarkan, sistem rekomendasi menjadi alat yang sangat berguna untuk membantu pengguna dalam menyaring informasi yang relevan (Ricci et al., 2015).

Selain itu, penelitian dalam bidang Recommender Systems menunjukkan bahwa model berbasis data dapat meningkatkan pengalaman pengguna dalam memilih produk yang sesuai dengan preferensi mereka (Aggarwal, 2016). Dengan menganalisis pola perilaku pengguna dan spesifikasi produk, sistem rekomendasi dapat memberikan saran yang lebih akurat dibandingkan pencarian manual yang dilakukan oleh pengguna.

### Mengapa Masalah Ini Harus Diselesaikan?
Penyelesaian proyek ini memiliki dampak yang signifikan dalam membantu konsumen membuat keputusan yang lebih cepat dan tepat dalam memilih smartphone. Dengan adanya sistem yang dapat secara otomatis menyaring dan mengurutkan perangkat berdasarkan kebutuhan individu, pengguna dapat menghemat waktu dan menghindari kebingungan akibat terlalu banyaknya pilihan.

Beberapa manfaat utama dari sistem ini meliputi:

1. Meningkatkan pengalaman pengguna – Konsumen tidak perlu melakukan riset manual yang panjang untuk menemukan smartphone yang sesuai.
2. Menghemat waktu dan tenaga – Dengan pemfilteran dan pengurutan otomatis, pengguna bisa langsung mendapatkan daftar smartphone terbaik sesuai preferensi.
3. Membantu pengambilan keputusan yang lebih akurat – Rekomendasi didasarkan pada data objektif seperti spesifikasi, harga, dan tahun rilis, bukan hanya opini subjektif.
4. Mempermudah pencarian produk di platform e-commerce – Sistem ini dapat diterapkan di berbagai platform belanja online untuk meningkatkan kepuasan pelanggan.

### Referensi
- Adomavicius, G., & Tuzhilin, A. (2005). Toward the next generation of recommender systems: A survey of the state-of-the-art and possible extensions. IEEE Transactions on knowledge and data engineering, 17(6), 734-749 [Link](https://pages.stern.nyu.edu/~atuzhili/pdf/TKDE-Paper-as-Printed.pdf)
- Aggarwal, C. C. (2016). Recommender Systems: The Textbook. Springer. https://doi.org/10.1007/978-3-319-29659-3 [Link](https://pzs.dstu.dp.ua/DataMining/recom/bibl/1aggarwal_c_c_recommender_systems_the_textbook.pdf)
- Ricci, F., Rokach, L., & Shapira, B. (2015). Recommender Systems Handbook. Springer. https://doi.org/10.1007/978-1-4899-7637-6 [Link](https://pzs.dstu.dp.ua/DataMining/recom/bibl/recommendersystemshandbook.pdf)

---

## Business Understanding
### Problem Statement
Pasar smartphone saat ini sangat kompetitif dengan berbagai merek dan model yang menawarkan spesifikasi yang beragam. Konsumen seringkali kesulitan dalam memilih smartphone yang paling sesuai dengan kebutuhan dan preferensi mereka. Tanpa sistem rekomendasi yang efektif, konsumen dapat merasa kewalahan dengan banyaknya pilihan dan kesulitan dalam membandingkan spesifikasi yang relevan.

Dalam penelitian ini, beberapa pertanyaan utama yang akan dijawab adalah:

1. Bagaimana cara mengidentifikasi fitur-fitur spesifikasi smartphone yang paling relevan dengan preferensi pengguna?
2. Bagaimana cara membangun sistem rekomendasi yang efektif berdasarkan spesifikasi smartphone menggunakan pendekatan content-based filtering?
3. Model atau algoritma apa yang paling efektif dalam memberikan rekomendasi smartphone berdasarkan spesifikasi?

### Goals
Untuk mengatasi permasalahan di atas, penelitian ini bertujuan untuk:

1. Mengidentifikasi dan mengekstraksi fitur-fitur spesifikasi smartphone yang relevan dari dataset.
2. Membangun sistem rekomendasi smartphone menggunakan pendekatan content-based filtering yang dapat memberikan rekomendasi yang dipersonalisasi berdasarkan preferensi pengguna.
3. Mengevaluasi kinerja model rekomendasi menggunakan algoritma WSM (Weighted Sum Model) dan LTR (Learning to Rank) untuk menentukan model terbaik.

### Solution Statement
Untuk mencapai tujuan tersebut, penelitian ini mengusulkan beberapa solusi:

1. Eksplorasi dan Preprocessing Data
- Mengumpulkan dataset spesifikasi smartphone dari sumber terpercaya.
- Menganalisis fitur-fitur spesifikasi smartphone untuk memahami karakteristik dan relevansinya menggunakan EDA.
- Melakukan preprocessing data, termasuk penanganan missing values, normalisasi data numerik, dan encoding fitur kategorikal.
  
2. Pemodelan dengan Content-Based Filtering
- Menggunakan pendekatan content-based filtering untuk merekomendasikan smartphone berdasarkan kesamaan spesifikasi.
- Menerapkan algoritma WSM (Weighted Sum Model) untuk memberikan bobot pada fitur-fitur spesifikasi berdasarkan preferensi pengguna.
- Menerapkan algoritma LTR (Learning to Rank) untuk mengurutkan smartphone berdasarkan relevansi dengan preferensi pengguna.
  
3. Evaluasi Model
- Evaluasi dilakukan dengan menggunakan metrik **Precision**, yang mengukur sejauh mana rekomendasi yang diberikan oleh sistem sesuai dengan kriteria yang telah ditentukan. Precision mengukur proporsi rekomendasi yang benar-benar relevan dibandingkan dengan jumlah total rekomendasi yang diberikan. Tiap baris dianalisis untuk ditentukan apakah sesuai dengan kriteria apa tidak.

Formula perhitungan precision:

![image](https://github.com/user-attachments/assets/fcae75e3-eb7e-4443-8d54-134f47ffc93b)

- Membandingkan kinerja model WSM dan LTR untuk menentukan model terbaik.
  
Dengan pendekatan ini, sistem rekomendasi smartphone yang dikembangkan diharapkan dapat memberikan rekomendasi yang akurat dan relevan berdasarkan spesifikasi smartphone, membantu konsumen dalam membuat keputusan pembelian yang lebih baik.

## Data Understanding
### Deskripsi Data
Dataset yang digunakan dalam proyek ini berasal dari dua sumber utama:

1. Mobiles Dataset (2025).csv – Dataset utama yang berisi informasi spesifikasi smartphone dari berbagai merek. [Link](https://www.kaggle.com/datasets/abdulmalik1518/mobiles-dataset-2025)
2. Android_SoC.csv dan iOS_Performance.csv – Dataset tambahan yang berisi skor benchmark prosesor dari Antutu untuk menambahkan nilai performa perangkat. [Link](https://www.kaggle.com/datasets/ireddragonicy/antutu-benchmark)

Karena dataset utama hanya memiliki informasi nama prosesor tanpa data kinerja, maka dilakukan penggabungan dengan dataset skor prosesor menggunakan nama prosesor sebagai primary key. Kolom "Total Score" dari dataset skor prosesor digunakan sebagai representasi kemampuan perangkat karena sudah mencakup skor CPU dan GPU.

### Struktur Dataset
1. Dataset Utama (Mobiles Dataset)
Dataset ini memiliki 930 baris dan 15 kolom. Berikut adalah daftar fitur dalam dataset utama:

| No  | Nama Kolom                     | Deskripsi                                     | Tipe Data  | Jumlah Data Non-Null |
|-----|--------------------------------|---------------------------------|------------|---------------------|
| 1   | Company Name                   | Merek smartphone                 | object     | 937                 |
| 2   | Model Name                     | Model smartphone                 | object     | 937                 |
| 3   | Mobile Weight (g)              | Berat perangkat (gram)            | float64    | 937                 |
| 4   | RAM (GB)                       | Kapasitas RAM (GB)                | float64    | 937                 |
| 5   | Front Camera (MP)              | Resolusi kamera depan (MP)        | float64    | 937                 |
| 6   | Back Camera (MP)               | Resolusi kamera belakang (MP)     | float64    | 937                 |
| 7   | Processor                      | Nama prosesor perangkat           | object     | 937                 |
| 8   | Battery Capacity (mAh)         | Kapasitas baterai (mAh)           | float64    | 937                 |
| 9   | Screen Size (inches)           | Ukuran layar (inci)               | float64    | 937                 |
| 10  | Launched Price (Pakistan/PKR)  | Harga saat rilis di Pakistan (PKR)| float64    | 936                 |
| 11  | Launched Price (India/INR)     | Harga saat rilis di India (INR)   | float64    | 937                 |
| 12  | Launched Price (China/CNY)     | Harga saat rilis di China (CNY)   | float64    | 937                 |
| 13  | Launched Price (USA/USD)       | Harga saat rilis di USA (USD)     | float64    | 937                 |
| 14  | Launched Price (Dubai/AED)     | Harga saat rilis di Dubai (AED)   | float64    | 937                 |
| 15  | Launched Year                  | Tahun rilis perangkat             | int64      | 937                 |

2. Dataset Skor Prosesor (Android_SoC.csv & iOS_Performance.csv)
Dataset ini memiliki 210 baris dan 6 kolom, dengan rincian:

| No  | Nama Kolom    | Deskripsi                                  | Tipe Data | Jumlah Data Non-Null |
|-----|-------------|--------------------------------|-----------|---------------------|
| 1   | Platform    | Sistem operasi (Android/iOS)  | object    | 210                 |
| 2   | Category    | Kategori prosesor (Flagship/Mid-range/Entry) | object | 210                 |
| 3   | Device      | Nama prosesor                 | object    | 210                 |
| 4   | CPU Score   | Skor performa CPU            | int64     | 210                 |
| 5   | GPU Score   | Skor performa GPU            | int64     | 210                 |
| 6   | Total Score | Skor total Antutu (CPU + GPU) | int64     | 210                 |


3. Dataset Gabungan
Setelah proses penggabungan berdasarkan nama prosesor, dataset akhir memiliki 937 baris dan 16 kolom dengan tambahan kolom "Performance Score" dari "Total Score" dataset skor prosesor.

| No  | Nama Kolom                     | Deskripsi                                              | Tipe Data  | Jumlah Data Non-Null |
|-----|--------------------------------|------------------------------------------------------|------------|---------------------|
| 1   | Company Name                   | Merek smartphone                                     | object     | 937                 |
| 2   | Model Name                     | Model smartphone                                    | object     | 937                 |
| 3   | Mobile Weight (g)              | Berat perangkat dalam gram                          | float64    | 937                 |
| 4   | RAM (GB)                        | Kapasitas RAM dalam GB                              | float64    | 937                 |
| 5   | Front Camera (MP)               | Resolusi kamera depan dalam MP                     | float64    | 937                 |
| 6   | Back Camera (MP)                | Resolusi kamera belakang dalam MP                  | float64    | 937                 |
| 7   | Processor                       | Nama prosesor perangkat                            | object     | 937                 |
| 8   | Battery Capacity (mAh)          | Kapasitas baterai dalam mAh                        | float64    | 937                 |
| 9   | Screen Size (inches)            | Ukuran layar dalam inci                            | float64    | 937                 |
| 10  | Launched Price (Pakistan/PKR)   | Harga saat rilis di Pakistan dalam PKR            | float64    | 936                 |
| 11  | Launched Price (India/INR)      | Harga saat rilis di India dalam INR               | float64    | 937                 |
| 12  | Launched Price (China/CNY)      | Harga saat rilis di China dalam CNY               | float64    | 937                 |
| 13  | Launched Price (USA/USD)        | Harga saat rilis di USA dalam USD                 | float64    | 937                 |
| 14  | Launched Price (Dubai/AED)      | Harga saat rilis di Dubai dalam AED               | float64    | 937                 |
| 15  | Launched Year                   | Tahun rilis perangkat                              | int64      | 937                 |
| 16  | Performance Score               | Skor performa perangkat berdasarkan Antutu        | float64    | 802                 |

### Analisis Kondisi Data
1. Kelengkapan Data
- Semua kolom di dataset utama memiliki 930 nilai non-null.
- Dataset gabungan memiliki 937 data, tetapi "Performance Score" hanya terisi 802 nilai (ada data yang tidak cocok saat merging) 
- Beberapa harga perangkat ada yang bernilai kosong setelah konversi.

2. Tipe Data
- Sebagian besar fitur dalam dataset akhir bertipe numerik (float64 dan int64), yang sudah sesuai untuk analisis dan pemodelan.
- Terdapat tiga kolom bertipe objek (object) yaitu Company Name, Model Name, dan Processor, yang perlu dikonversi ke representasi numerik jika digunakan dalam pemodelan machine learning.
- Kolom harga (Launched Price) sudah bertipe numerik (float64), tetapi terdapat satu nilai kosong pada Launched Price (Pakistan/PKR) yang perlu ditangani.
- Kolom Performance Score memiliki tipe float64, tetapi masih terdapat 135 nilai kosong, yang kemungkinan terjadi karena tidak semua prosesor memiliki data benchmark di dataset tambahan.
- Kolom Launched Year bertipe int64, yang sudah sesuai karena merepresentasikan tahun rilis perangkat.

3. Perbaikan data yang diperlukan
- Data untuk kolom processor pada dataset utama dan kolom device pada dataset benchmark tidak memiliki format atau standar yang sama sehingga perlu diubah agar memiliki format yang sama dan kedua dataset bisa digabungkan.

4. Karakteristik Data
- Tahun Peluncuran (Launched Year): Rentang tahun berkisar antara 2014 hingga 2025.
- Harga Peluncuran (Launched Price):
  - Harga sangat bervariasi di berbagai negara.
  - Rentang harga mulai dari PKR 15,999 hingga PKR 604,999 dan USD 79 hingga USD 39,622.
- Rentang harga ini menunjukkan adanya perbedaan kelas perangkat, tetapi juga kemungkinan outlier yang perlu dianalisis lebih lanjut.
- Ukuran Layar (Screen Size): Berkisar antara 5.0 hingga 14.6 inci.
- Kapasitas Baterai (Battery Capacity):
  - Rentang antara 2000 hingga 11,200 mAh.
  - Variasi besar ini menunjukkan kemungkinan adanya perangkat dengan kapasitas ekstrem, seperti tablet atau rugged phone.
- RAM:
  - Berkisar antara 1 GB hingga 16 GB.
  - Ini mencerminkan berbagai kategori ponsel, dari entry-level hingga flagship.
- Kamera:
  - Kamera depan berkisar antara 2 MP hingga 60 MP.
  - Kamera belakang berkisar antara 5 MP hingga 200 MP.
- Bobot Perangkat (Mobile Weight):
  - Rata-rata bobot perangkat adalah 228 gram.
  - Nilai maksimum 732 gram jauh di atas rata-rata, kemungkinan berasal dari perangkat foldable atau rugged phone.
- Performance Score:
  - Nilai berkisar antara 25,673 hingga 1,709,461.
  - Ini menunjukkan perbedaan besar antara perangkat entry-level dan flagship terbaru.
- Missing Values:
  - Terdapat satu missing value pada harga peluncuran di Pakistan (Launched Price Pakistan/PKR).
  - Perlu dilakukan pemeriksaan lebih lanjut dan penanganan terhadap data yang hilang.

### Exploratory Data analysis (EDA)
Setelah mendapatkan dataset, proses selanjutnya adalah melakukan Exploratory Data analysis (EDA). EDA adalah proses analisis awal pada suatu dataset untuk memahami karakteristik, distribusi, pola, serta hubungan antar variabel sebelum dilakukan pemodelan. EDA bertujuan untuk menemukan missing values, outlier, distribusi data, serta korelasi antar fitur, sehingga dapat menentukan langkah preprocessing yang tepat.

Dalam EDA, teknik yang sering digunakan meliputi statistik deskriptif (mean, median, standar deviasi), visualisasi data (histogram, boxplot, scatter plot), serta analisis korelasi antar variabel. Dengan melakukan EDA, kita dapat mengidentifikasi potensi masalah dalam dataset dan melakukan penyesuaian yang diperlukan agar model machine learning dapat bekerja secara optimal.

#### Univariate Analysis
Selanjutnya adalah melakukan Univariate Analysis. Univariate Analysis adalah analisis statistik yang dilakukan pada satu fitur untuk memahami karakteristik dan distribusi datanya. Metodenya menggunakan visualisasi agar mudah mendeteksi pola data dan sebaran nilainya.

Fitur numerik dalam dataset meliputi **Mobile Weight (g), RAM (GB), Front Camera (MP), Back Camera (MP), Battery Capacity (mAh), Screen Size (inches), Launched Price (Pakistan/PKR), Launched Price (India/INR), Launched Price (China/CNY), Launched Price (USA/USD), Launched Price (Dubai/AED), dan Launched Year**, yang merepresentasikan nilai kontinu.

Sementara itu, fitur kategorikal terdiri dari Company Name, Model Name, dan Processor, yang berisi nilai dalam bentuk kategori atau label.

1. Fitur Kategori
   
   ![image](https://github.com/user-attachments/assets/8bea56ac-fc49-4e9a-ba4c-2a9b873b9436)
   ![image](https://github.com/user-attachments/assets/fbe88b23-d498-4b05-b46e-e87ac796c8eb)
   ![image](https://github.com/user-attachments/assets/8c984e72-51a1-4272-9fb6-d790afc06ba5)
   
   Dari visualisasi distribusi data fitur-fitur kategorikal di atas dapat disimpulkan bahwa:
   - Fitur Company Name: Oppo merupakan merek dengan jumlah ponsel terbanyak (13.9%), diikuti oleh Apple (10.4%) dan Honor (9.8%). Merek seperti iQOO (0.3%) dan Sony (1.0%) memiliki jumlah sampel paling sedikit.
   - Fitur Model Name: Dataset memiliki 908 model unik, dengan sebagian besar model hanya memiliki 1 atau 2 sampel. Hal ini menunjukkan bahwa dataset sangat bervariasi dalam hal model ponsel.
   - Fitur Processor: Snapdragon 8 Gen 2 (3.2%) adalah prosesor yang paling umum digunakan, diikuti oleh MediaTek Dimensity 810 (2.4%) dan Helio G99 (2.3%). Namun, ada 217 jenis prosesor berbeda, dengan banyak prosesor hanya memiliki 1 sampel, menunjukkan variasi yang luas dalam jenis chipset yang digunakan.
   - Distribusi Model & Processor: Banyak model dan prosesor memiliki jumlah sampel yang sangat sedikit, menunjukkan bahwa dataset mencakup berbagai varian ponsel dengan spesifikasi yang beragam.

2. Fitur Numerik
   
   ![image](https://github.com/user-attachments/assets/e0fc002a-ebff-4557-b57c-4f3863293af4)
   
   Dari visualisasi distribusi data fitur-fitur numerik diatas dapat disimpulkan bahwa:
   - Mobile Weight (g)
     - Sample terbanyak ada di value Mobile Weight sekitar 190g
     - Tidak ada pola khusus, tetapi sample terpusat di 190g, sisanya lebih dan kurang dari 190g.
     
   - RAM (GB)
     - Sample terbanyak ada di value RAM 8 GB.
     - Ram dengan sample terbanyak selanjutnya adalah 4, 6, 12 GB.
     
   - Front Camera (MP)
     - Sample terbanyak ada di value 8, 17, 32 MP.
     - Tidak ada pola khusus pada data.
     
   - Back Camera (MP)
     - Sample terbanyak ada di value 50 MP.
     - Tidak ada pola khusus pada data.
     
   - Batery Capacity (mAh)
     - Sample terbanyak ada di value 5000 mAh.
     - Lebih dari 50% sample memiliki value 5000 mAh dan dibawahnya.
     - Tidak ada pola khusus pada data.
     
   - Screen Sizes (Inches)
     - Tidak ada pola khusus dalam distribusi.
     - Data terpusat di sekitar value 6.8 inches.
     
   - Launched Price (Pakistan/PKR), Launched Price (India/INR), Launched Price (China/CNY), Launched Price (USA/USD), Launched Price (Dubai/AED)
     - Beberapa fitur diatas memiliki kesamaan pola dimana semakin tinggi harganya maka jumlah sample semakin sedikit.
     - Distribusi mileage miring ke kanan.
     
   - Launched Year
     - Jumlah sample terbanyak ada di value 2024.
     - Distribusi mileage miring ke kiri.
     
   - Performance Score
     - Tidak ada pola khusus yang terlihat
     - Lebih dari 50% sample memiliki skor kurang dari 0.5 x le6

#### Multivariate Analysis
Langkah selanjutnya adalah melakukan Multivariate Analysis. Multivariate Analysis adalah teknik analisis statistik yang digunakan untuk memahami hubungan antara dua atau lebih variabel dalam suatu dataset. Tujuan utama analisis ini adalah untuk mengidentifikasi pola, hubungan, atau korelasi antara fitur, sehingga dapat membantu dalam pemodelan prediktif dan pengambilan keputusan. Fitur Launched Price (China/CNY) dipilih sebagai target analisis korelasi karena China adalah produsen terbesar smartphone terbesar didunia.

1. Fitur Kagetori
   
   ![image](https://github.com/user-attachments/assets/53dac2ff-e1dd-4829-9320-f426017a5747)

   Dari catplot visualisasi hubungan antara fitur price dengan fitur-fitur kategorikal diatas dapat disimpulkan bahwa:
   - Pada fitur ‘Company Name’, ada perbedaan rata-rata harga. beberapa company name yaitu apple, huawei, sony, dan google memiliki rata-rata harga yang lebih tinggi daripada brand lainnya. Sehingga kemungkinan fitur company name memiliki pengaruh atau dampak yang cukup besar terhadap rata-rata harga.
   - Pada fitur ‘Model’, ada banyak kategori dan tidak banyak perbedaan rata-rata harga. Hanya ada beberapa model yang memiliki perbedaan harga yang signifikan. Sehingga kemungkinan fitur brand memiliki pengaruh atau dampak yang cukup kecil terhadap rata-rata harga.
   - Pada fitur ‘Processor’, ada banyak kategori dan tidak banyak perbedaan rata-rata harga. Hanya ada beberapa processor yang memiliki perbedaan harga yang signifikan. Sehingga kemungkinan fitur brand memiliki pengaruh atau dampak yang cukup kecil terhadap rata-rata harga.

2. Fitur Numerik
   
  ![image](https://github.com/user-attachments/assets/8d7a8db5-6261-439d-84d5-0115404f15cd)

  Dari grafik pairplot diatas, jika fokus pada sumbu "Launched Price (China/CNY)" dimana merupakan fitur target, dapat disimpulkan bahwa:
  * Fitur mobile weight (g), Battery Capacity, dan Screen Size memiliki korelasi positif dengan fitur Launched Price (China/CNY) walaupun tidak terlalu terlihat.
  * Fitur Performance Score memiliki korelasi positif dengan fitur Launched Price (China/CNY).
  * Fitur RAM, Front Camera, Back Camera, dan Launched Year memiliki pola yang cukup acak dengan fitur Launched Price (China/CNY).
  * Fitur yang tersisa, Launched Price (Pakistan/PKR), Launched Price (India/INR), Launched Price (USA/USD), dan Launched Price (Dubai/AED) tidak memiliki korelasi dengan fitur Launched Price (China/CNY) karena sebenarnya fitur-fitur tersebut sama-sama merepresentasikan harga, hanya dalam daerah atau mata uang yang berbeda.
    
  ![image](https://github.com/user-attachments/assets/e485d3d1-53f6-4f71-a062-9db93af4d023)
  
  Untuk lebih jelasnya, dapat diamati grafik korelasi diatas. Dapat disimpulkan bahwa:
  * Hanya fitur RAM yang memiliki korelasi yang cukup kuat (0.43) dengan Launched Price (China/CNY), Kecuali fitur Launched Price negara lain.
  * Fitur Mobile Weight memiliki korelasi yang sangat kuat (0.98) dengan Screen Size (Inches) dan korelasi kuat (0.85) dengan Battery Capacity.
  * Fitur Battery Capacity memiliki korelasi yang kuat (0.88) dengan Screen Size (Inches).
  * Fitur Performance score memiliki korelasi yang cukup kuat (0.67) dengan Launched Price (China/CNY) dan korelasi yang cukup kuat (0.7) dengan fitur RAM.

## Data Preparation
Setelah melakukan EDA dan sebelum membangun model machine learning, diperlukan tahapan data preparation untuk memastikan bahwa data memiliki kualitas yang baik dan dapat meningkatkan performa model. Tahapan ini mencakup pembersihan data, transformasi fitur, encoding variabel kategorikal, reduksi dimensi, serta standarisasi fitur.

1. Pembersihan data dengan menghapus kolom yang tidak diperlukan
   
   Dilakukan proses data preparation yang pertama, yaitu menghapus fitur yang dianggap tidak diperlukan dalam membuat sistem rekomendasi. Kolom yang dihapus:
   - Fitur "Launched Price (Pakistan/PKR)", "Launched Price (India/INR)", "Launched Price (USA/USD)", dan "Launched Price (Dubai/AED)" dihapus karena sudah ada fitur Launched Price (China/CNY) yang merepresentasikan harga berdasarkan negara atau mata uang China/CNY.
   - Fitur Processor sudah tidak diperlukan karena sudah ada fitur Performance Score yang merepresentasikan kemampuan processor smartphone.
     
2. Menangani Missing Values & Outliers
   
   ![image](https://github.com/user-attachments/assets/5e250bab-61cf-4dab-806b-0183dd295c3d)
   
   Kode diatas berfungsi untuk melihat apakah ada missing values pada dataset. Setelah dijalankan, ternyata pada kolom performance score terdapat 135. Hal ini mungkin dikarenakan kurang lengkapnya dataset kedua yang sebelumnya digabungkan, sehingga ada data yang kosong. Diputuskan untuk menghapus data dengan missing values dan tidak dilakukan imputasi demi menjaga relevansi dan validitas data kolom Performance Score karena sangat penting.
   - Metode yang digunakan untuk menangani outliers adalah Box-Cox Transformation.
     Box-Cox Transformation adalah teknik yang digunakan untuk menormalkan distribusi data dan mengurangi pengaruh outliers dengan menerapkan transformasi non-linear pada fitur numerik yang hanya memiliki nilai positif.
   - Alasan Pemilihan Box-Cox:
     - Mengatasi Outliers Tanpa Menghapus Data → Tidak ada informasi yang hilang, hanya ditransformasikan.
     - Membantu Menormalkan Data → Berguna untuk model berbasis regresi dan metode yang mengasumsikan distribusi normal.
     - Lebih Efektif Dibanding Log Transformation → Sebelumnya telah dicoba metode Log Transformation dan ternyata Box-Cox lebih baik karena secara dinamis menyesuaikan transformasi berdasarkan distribusi data.]
       
3. Encoding for Categorical Feature
   
   Langkah ketiga adalah encoding untuk fitur kategorikal.
  Teknik yang digunakan:
  * Target Encoding untuk fitur Company Name
  * Label Encoding untuk fitur Model Name
  
  Pada tahap ini, dilakukan encoding untuk fitur kategorikal agar dapat digunakan dalam model machine learning. Teknik yang digunakan adalah Target Encoding untuk fitur Company Name dan Label Encoding untuk fitur Model Name.
  
  * Encoding untuk fitur Company Name
      * Company Name dikonversi ke nilai numerik berdasarkan rata-rata Performance Score dari setiap perusahaan.
      * Teknik ini membantu mempertahankan hubungan antara kategori dengan target tanpa meningkatkan dimensi dataset.
  * Encoding untuk fitur Model Name
      * Model Name dikonversi ke nilai numerik menggunakan Label Encoding, di mana setiap model diberikan nilai unik berdasarkan indeksnya.
      * Metode ini digunakan karena jumlah kategori pada Model Name sangat banyak, sehingga One-Hot Encoding tidak efisien dan menyebabkan peningkatan dimensi dataset (curse of dimensionality).
  * Alasan Pemilihan Teknik Encoding
      * Target Encoding cocok untuk Company Name, karena dapat menangkap hubungan antara brand dan performa perangkat.
      * Label Encoding cocok untuk Model Name, karena lebih efisien dalam menyimpan informasi tanpa meningkatkan dimensi dataset secara signifikan
        
4. Standarisasi Fitur Numerik
   
   Langkah terakhir adalah melakukan Standarisasi. Standarisasi adalah proses transformasi data numerik agar memiliki skala yang seragam, biasanya dengan mean (rata-rata) = 0 dan standar deviasi = 1. Tujuannya adalah untuk memastikan bahwa setiap fitur memiliki kontribusi yang seimbang dalam model machine learning, terutama jika fitur memiliki skala atau unit yang berbeda. Teknik yang digunakan adalah Standar Scaler. Alasannya adalah untuk menghindari skala yang terlalu besar pada fitur tertentu, yang dapat memengaruhi performa model.

## Modelling
Setelah melakukan Data Preparation, selanjutnya adalah melakukan modelling machine learning. Modelling dalam sistem rekomendasi adalah proses membangun metode yang dapat memberikan rekomendasi berdasarkan preferensi dan kebutuhan pengguna. Dalam kasus ini, sistem rekomendasi yang dibuat menggunakan pendekatan Content-Based Filtering. Hal ini dikarenakan dataset yang digunakan hanya berisi fitur-fitur mengenai content/item yang berupa spesifikasi smartphone. Model atau algoritma yang digunakan adalah **Weighted Sum Model (WSM)** dan **Learning to Rank (LTR)**.

1. Weight Sum Model (WSM): Menggunakan metode pembobotan fitur untuk menghitung skor rekomendasi berdasarkan preferensi pengguna.
   Formula WSM:

   ![image](https://github.com/user-attachments/assets/5da3480c-677c-4d4b-866c-f41b7dba0534)

   Dimana:
   ![image](https://github.com/user-attachments/assets/de93e176-afcb-45d9-a926-e1f04a8536da)

2. Learning to Rank (LTR): Menggunakan pendekatan machine learning untuk menyusun peringkat smartphone.

### **Kelebihan dan Kekurangan WSM & LTR**

**1. Weight Sum Model (WSM)**

#### **Kelebihan WSM**
- **Mudah Dipahami & Diimplementasikan**: Perhitungan sederhana dengan menjumlahkan nilai berbobot.
- **Cepat dalam Komputasi**: Tidak memerlukan pelatihan model, hanya normalisasi dan perhitungan skor.
- **Dapat Dikustomisasi**: Bobot fitur bisa disesuaikan dengan preferensi pengguna (gaming, photography, normal usage).
- **Tidak Membutuhkan Data Latih**: Bisa digunakan langsung tanpa memerlukan dataset historis.

#### **Kekurangan WSM**
- **Bobot Statis**: Tidak dapat beradaptasi dengan pola data secara otomatis.
- **Tidak Menangkap Hubungan Kompleks Antar Fitur**: Hubungan non-linear antar fitur tidak dapat ditangkap dengan baik.
- **Sensitif terhadap Normalisasi**: Hasil bisa sangat dipengaruhi oleh metode normalisasi yang digunakan.
- **Tidak Belajar dari Feedback Pengguna**: Tidak bisa memperbaiki rekomendasi berdasarkan interaksi pengguna sebelumnya.

---

**2. Learning to Rank (LTR)**

#### **Kelebihan LTR**
- **Dapat Menangkap Hubungan Kompleks Antar Fitur**: Mampu memahami pola non-linear yang tidak bisa ditangkap oleh metode berbasis aturan seperti WSM.
- **Adaptif**: Model dapat belajar dari data historis dan menyesuaikan bobot fitur berdasarkan performa sebelumnya.
- **Meningkatkan Akurasi Rekomendasi**: Lebih efektif dalam memberikan urutan rekomendasi yang lebih relevan dibandingkan metode sederhana.
- **Mampu Menyesuaikan Diri dengan Preferensi Pengguna**: Bisa terus belajar dari umpan balik pengguna untuk meningkatkan rekomendasi di masa depan.

#### **Kekurangan LTR**
- **Membutuhkan Data Latih**: Harus memiliki dataset yang cukup besar untuk menghasilkan model yang akurat.
- **Lebih Kompleks & Butuh Sumber Daya Komputasi Lebih Besar**: Dibandingkan WSM, LTR memerlukan proses training yang lebih berat.
- **Sulit untuk Dijelaskan**: Model machine learning bisa menjadi black box dan sulit menjelaskan alasan di balik rekomendasi.

### **Pembobotan Fitur dalam Weight Sum Model (WSM) & Learning to Rank (LTR)**  

Dalam sistem rekomendasi smartphone ini, **pembobotan fitur** digunakan untuk dua pendekatan yang berbeda:  
1. **Weight Sum Model (WSM)** → Menggunakan pembobotan untuk menjumlahkan skor tiap fitur dan menghasilkan rekomendasi berbasis skor akhir.  
2. **Learning to Rank (LTR)** → Menggunakan pembobotan sebagai faktor dalam model pembelajaran mesin yang mempelajari hubungan antar fitur untuk melakukan pemeringkatan smartphone.  

### **Pembobotan untuk Setiap Preferensi Pengguna**  

**1. Gaming**  
- **Performance Score (60%)** → Faktor utama untuk gaming adalah performa prosesor dan GPU.  
- **RAM (20%)** → RAM besar membantu dalam multitasking dan menjalankan game berat.  
- **Battery Capacity (12%)** → Daya tahan baterai sangat penting untuk sesi gaming yang lama.  
- **Launched Year (8%)** → Ponsel yang lebih baru biasanya memiliki chipset dan teknologi yang lebih optimal untuk gaming.  
- **Screen Size (0.5%)** → Layar besar lebih nyaman untuk pengalaman gaming.  
- **Back Camera (0.2%) & Front Camera (0.1%)** → Kamera kurang penting untuk gaming tetapi tetap diperhitungkan sedikit.  
- **Mobile Weight (0.2%)** → Ponsel yang terlalu berat dapat mengurangi kenyamanan saat bermain game dalam waktu lama.  

**2. Photography**  
- **Back Camera (35%) & Front Camera (35%)** → Kamera belakang dan depan sangat penting untuk fotografi dan selfie.  
- **RAM (8%)** → Membantu dalam pemrosesan gambar dan video.  
- **Performance Score (8%)** → Performa tetap diperhitungkan karena mempengaruhi pemrosesan foto/video.  
- **Launched Year (10%)** → Model yang lebih baru sering memiliki teknologi kamera yang lebih baik.  
- **Screen Size (3%)** → Layar besar memudahkan dalam mengedit dan melihat foto.  
- **Battery Capacity (2%)** → Berguna untuk penggunaan kamera dalam waktu lama.  
- **Mobile Weight (1%)** → Ponsel yang ringan lebih nyaman untuk fotografi mobile.  

**3. Normal Usage**  
- **Battery Capacity (30%)** → Ketahanan baterai adalah faktor utama untuk penggunaan sehari-hari.  
- **Performance Score (28%)** → Performa tetap penting untuk kelancaran penggunaan aplikasi sehari-hari.  
- **RAM (15%)** → Menjamin multitasking yang lancar.  
- **Mobile Weight (10%)** → Ponsel yang terlalu berat bisa kurang nyaman untuk penggunaan jangka panjang.  
- **Launched Year (12%)** → Ponsel yang lebih baru sering memiliki optimasi daya dan fitur terbaru.  
- **Screen Size (3%)** → Layar cukup penting untuk kenyamanan penggunaan.  
- **Back Camera (1.5%) & Front Camera (0.5%)** → Kamera tetap dipertimbangkan tetapi bukan faktor utama.  

### **Peran Pembobotan dalam WSM & LTR**  
- **Dalam WSM** → Pembobotan digunakan untuk menghitung skor akhir dengan metode **penjumlahan berbobot** dari semua fitur.  
- **Dalam LTR** → Pembobotan digunakan sebagai **feature importance** dalam algoritma machine learning yang belajar dari data ranking dan menghasilkan pemeringkatan yang lebih optimal berdasarkan hubungan antar fitur.

### Result
Saat pemodelan sudah selesai dilakukan, model dicoba dengan memberikan rekomendasi untuk preferensi "Gaming" dengan harga maksimal "2500" dalam harga asli CNY. Hasilnya muncul Top-10 Recommendation dari masing-masing model sebagai berikut:

#### Model 1: Weight Sum Model (WSM)

| Model Name                  | Mobile Weight (g) | RAM (GB) | Front Camera (MP) | Back Camera (MP) | Battery Capacity (mAh) | Screen Size (inches) | Launched Price (China/CNY) | Launched Year | Performance Score | Score (Gaming) | Score (Photography) | Score (Normal Usage) | **WSM Score** |
|-----------------------------|-------------------|---------|------------------|-----------------|--------------------|-----------------|----------------------------|---------------|-----------------|----------------|-----------------|----------------|--------------|
| infinix Hot 50 Pro+         | 196.0             | 12.0    | 32.0             | 108.0           | 5300.0             | 6.90            | 2499.0                     | 2024          | 883658.0        | 1.253670       | 1.258590       | 5.726030       | **1.155704** |
| realme P2 Pro 5G 256GB      | 188.0             | 12.0    | 32.0             | 50.0            | 5500.0             | 6.78            | 2500.0                     | 2024          | 859609.0        | 1.145704       | 0.726996       | 0.525238       | **1.151382** |
| infinix Note 40 Pro 5G      | 195.0             | 12.0    | 32.0             | 108.0           | 5300.0             | 6.80            | 2499.0                     | 2024          | 655239.0        | 0.820797       | 1.223096       | -4.693683      | **0.928939** |
| realme P2 Pro 5G 128GB      | 195.0             | 8.0     | 16.0             | 50.0            | 5100.0             | 6.70            | 2500.0                     | 2024          | 883658.0        | 0.764250       | 0.162527       | -4.871083      | **0.872392** |
| infinix Zero 40 5G          | 195.0             | 12.0    | 50.0             | 108.0           | 5000.0             | 6.78            | 2299.0                     | 2024          | 513284.0        | 0.605866       | 1.705943       | -4.860368      | **0.714008** |
| infinix Zero 40             | 195.0             | 12.0    | 50.0             | 108.0           | 5000.0             | 6.78            | 2199.0                     | 2024          | 513284.0        | 0.605866       | 1.705943       | -4.860368      | **0.714008** |
| realme P1 Speed 5G 256GB    | 185.0             | 12.0    | 16.0             | 64.0            | 5100.0             | 6.70            | 1900.0                     | 2024          | 453448.0        | 0.625810       | 0.343095       | 0.285501       | **0.629236** |
| infinix Note 40 Pro         | 190.0             | 12.0    | 32.0             | 108.0           | 5000.0             | 6.78            | 2199.0                     | 2024          | 453448.0        | 0.613207       | 1.177878       | 0.057811       | **0.621577** |
| vivo Y200 GT 128GB         | 190.0             | 12.0    | 16.0             | 64.0            | 5000.0             | 6.58            | 2499.0                     | 2024          | 412258.0        | 0.538814       | 0.326941       | -0.008562      | **0.547185** |
| realme P1 Pro 5G 256GB      | 190.0             | 12.0    | 16.0             | 64.0            | 5200.0             | 6.70            | 2000.0                     | 2024          | 394463.0        | 0.532310       | 0.333954       | 0.044088       | **0.540680** |

#### Model 2: Learning to Rank (LTR)

| Company Name | Model Name                | **Predicted Ranking Score** | Launched Price (China/CNY) | Mobile Weight (g) | RAM (GB) | Front Camera (MP) | Back Camera (MP) | Battery Capacity (mAh) | Screen Size (inches) | Performance Score | Launched Year |
|-------------|---------------------------|----------------------------|----------------------------|-------------------|---------|------------------|-----------------|--------------------|-----------------|-----------------|---------------|
| realme      | P2 Pro 5G 256GB           | **1.169090**               | 2500.0                     | 188.0             | 12.0    | 32.0             | 50.0            | 5500.0             | 6.78            | 859609.0        | 2024          |
| infinix     | Hot 50 Pro+               | **0.946402**               | 2499.0                     | 196.0             | 12.0    | 32.0             | 108.0           | 5300.0             | 6.90            | 883658.0        | 2024          |
| infinix     | Note 40 Pro 5G            | **0.718931**               | 2499.0                     | 195.0             | 12.0    | 32.0             | 108.0           | 5300.0             | 6.80            | 655239.0        | 2024          |
| realme      | P1 Speed 5G 256GB         | **0.655203**               | 1900.0                     | 185.0             | 12.0    | 16.0             | 64.0            | 5100.0             | 6.70            | 453448.0        | 2024          |
| infinix     | Zero 40 5G                | **0.613936**               | 2299.0                     | 195.0             | 12.0    | 50.0             | 108.0           | 5000.0             | 6.78            | 513284.0        | 2024          |
| infinix     | Zero 40                   | **0.613936**               | 2199.0                     | 195.0             | 12.0    | 50.0             | 108.0           | 5000.0             | 6.78            | 513284.0        | 2024          |
| vivo        | Y200 GT 128GB             | **0.578339**               | 2499.0                     | 190.0             | 12.0    | 16.0             | 64.0            | 5000.0             | 6.58            | 412258.0        | 2024          |
| realme      | P1 Pro 5G 256GB           | **0.573573**               | 2000.0                     | 190.0             | 12.0    | 16.0             | 64.0            | 5200.0             | 6.70            | 394463.0        | 2024          |
| realme      | Neo 7 128GB               | **0.555282**               | 2400.0                     | 193.0             | 8.0     | 16.0             | 64.0            | 5000.0             | 6.70            | 513284.0        | 2024          |
| infinix     | Note 40 Pro               | **0.538993**               | 2199.0                     | 190.0             | 12.0    | 32.0             | 108.0           | 5000.0             | 6.78            | 453448.0        | 2024          |

## Evaluation
Setelah melakukan pemodelan, langkah selanjutnya adalah evaluasi untuk mengukur seberapa baik sistem dalam memberikan rekomendasi yang sesuai dengan preferensi pengguna.

Evaluasi dilakukan dengan menggunakan metrik Precision, yang mengukur sejauh mana rekomendasi yang diberikan oleh sistem sesuai dengan kriteria yang telah ditentukan. Precision mengukur proporsi rekomendasi yang benar-benar relevan dibandingkan dengan jumlah total rekomendasi yang diberikan. Tiap baris dianalisis untuk ditentukan apakah sesuai dengan kriteria apa tidak.

Formula perhitungan precision:

![image](https://github.com/user-attachments/assets/54300545-000f-4331-a47a-5208b44c9a1f)

Kriteria yang digunakan untuk menentukan apakah smartphone relevan untuk gaming:
- RAM lebih dari sama dengan 12 GB
- Performance Score lebih dari sama dengan 400.000

Berikut adalah hasil evaluasi berdasarkan percobaan sebelumnya untuk preferensi "gaming" dan harga maksimal "2500" CNY dari setiap model:

### Model 1: Weight Sum Model (WSM)

| Model Name                  | RAM (GB) | Performance Score | WSM Score  | Relevan (Gaming) |
|-----------------------------|---------|------------------|------------|------------------|
| infinix Hot 50 Pro+         | 12.0    | 883658.0         | 1.155704   | ✅               |
| realme P2 Pro 5G 256GB      | 12.0    | 859609.0         | 1.151382   | ✅               |
| infinix Note 40 Pro 5G      | 12.0    | 655239.0         | 0.928939   | ✅               |
| realme P2 Pro 5G 128GB      | 8.0     | 883658.0         | 0.872392   | ❌               |
| infinix Zero 40 5G          | 12.0    | 513284.0         | 0.714008   | ✅               |
| infinix Zero 40             | 12.0    | 513284.0         | 0.714008   | ✅               |
| realme P1 Speed 5G 256GB    | 12.0    | 453448.0         | 0.629236   | ✅               |
| infinix Note 40 Pro         | 12.0    | 453448.0         | 0.621577   | ✅               |
| vivo Y200 GT 128GB         | 12.0    | 412258.0         | 0.547185   | ✅               |
| realme P1 Pro 5G 256GB      | 12.0    | 394463.0         | 0.540680   | ❌               |

Jumlah rekomendasi yang relevan = 8
Jumlah total rekomendasi = 10
**Hasil precission model = 8/10 = 80%**

### Model 2: Learning to Rank (LTR)

| Model Name                  | RAM (GB) | Performance Score | Predicted Ranking Score | Relevan (Gaming) |
|-----------------------------|---------|------------------|-------------------------|------------------|
| realme P2 Pro 5G 256GB      | 12.0    | 859609.0         | 1.169090                | ✅               |
| infinix Hot 50 Pro+         | 12.0    | 883658.0         | 0.946402                | ✅               |
| infinix Note 40 Pro 5G      | 12.0    | 655239.0         | 0.718931                | ✅               |
| realme P1 Speed 5G 256GB    | 12.0    | 453448.0         | 0.655203                | ✅               |
| infinix Zero 40 5G          | 12.0    | 513284.0         | 0.613936                | ✅               |
| infinix Zero 40             | 12.0    | 513284.0         | 0.613936                | ✅               |
| vivo Y200 GT 128GB         | 12.0    | 412258.0         | 0.578339                | ✅               |
| realme P1 Pro 5G 256GB      | 12.0    | 394463.0         | 0.573573                | ❌               |
| realme Neo 7 128GB         | 8.0     | 513284.0         | 0.555282                | ❌               |
| infinix Note 40 Pro         | 12.0    | 453448.0         | 0.538993                | ✅               |

Jumlah rekomendasi yang relevan = 8
Jumlah total rekomendasi = 10
**Hasil precission model = 8/10 = 80%**

### Kesimpulan Evaluasi
- Kedua model sama-sama memiliki precision 80% berdasarkan kriteria yang diberikan. Dengan Precision sebesar 80%, berarti 8 dari 10 rekomendasi yang diberikan sistem benar-benar sesuai dengan kriteria gaming. Meskipun masih ada 2 item yang kurang sesuai, hal ini menunjukkan bahwa model sudah cukup efektif dalam menyaring smartphone yang cocok berdasarkan spesifikasi yang diberikan.
- Kedua model memberikan Top-10 Recommendation yang mirip dengan permintaan yang sama (gaming dan 2500 CNY), tetapi masih ada beberapa item yang berbeda.
- 2 item yang tidak memenuhi kriteria sebenarnya juga masih cukup dekat dengan kriteria sehingga masih cukup relevan sebagai rekomendasi

## Conclusion
Berdasarkan evaluasi menggunakan metrik Precision, kedua model, Weighted Sum Model (WSM) dan Learning to Rank (LTR), mencapai nilai Precision sebesar 80%, menunjukkan bahwa sistem rekomendasi mampu memberikan rekomendasi yang cukup relevan dengan preferensi pengguna. WSM memberikan pendekatan berbasis bobot fitur, sedangkan LTR mampu mengurutkan rekomendasi secara lebih optimal berdasarkan relevansi preferensi.

Dari perspektif Business Understanding, model yang dikembangkan telah menjawab semua problem statement dengan baik:
1. Identifikasi fitur utama yang berpengaruh terhadap pemilihan smartphone berhasil dilakukan, dengan RAM dan skor performa sebagai faktor utama untuk preferensi gaming.
2. Pengolahan dan normalisasi data, termasuk encoding fitur kategorikal, telah meningkatkan kualitas dataset dalam pemodelan rekomendasi.
3. Pembangunan sistem rekomendasi berbasis spesifikasi smartphone berhasil dilakukan menggunakan pendekatan Content-Based Filtering.

Penelitian ini juga berhasil mencapai setiap goals yang ditetapkan:
1. Fitur-fitur relevan telah diidentifikasi dan diekstraksi untuk meningkatkan kualitas rekomendasi.
2. Implementasi model WSM dan LTR berhasil memberikan rekomendasi yang akurat, sesuai dengan preferensi pengguna.
3. Evaluasi dengan Precision menunjukkan bahwa sistem dapat memberikan rekomendasi yang relevan dengan tingkat keakuratan yang baik.

Dampak dari solution statement yang dirancang juga terlihat jelas dalam penelitian ini:
1. Eksplorasi dan preprocessing data berhasil meningkatkan akurasi rekomendasi dengan membersihkan dan menyusun data secara optimal.
2. Pemilihan metode WSM dan LTR membantu dalam perancangan sistem rekomendasi yang mampu menangkap preferensi pengguna secara lebih personal.
3. Evaluasi menggunakan metrik Precision memastikan bahwa sistem tidak hanya memberikan rekomendasi sembarang, tetapi benar-benar relevan dengan kebutuhan pengguna.

Dengan hasil ini, sistem rekomendasi smartphone yang dikembangkan dapat membantu konsumen dalam menemukan smartphone yang sesuai dengan preferensi mereka dengan lebih cepat dan akurat, sehingga mempermudah pengambilan keputusan dalam pembelian.
