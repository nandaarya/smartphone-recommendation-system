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
| No  | Nama Kolom                  | Deskripsi |
|-----|-----------------------------|-----------|
| 1   | `Company Name`              | Merek smartphone |
| 2   | `Model Name`                | Model smartphone |
| 3   | `Mobile Weight`             | Berat perangkat (gram) |
| 4   | `RAM`                       | Kapasitas RAM (GB) |
| 5   | `Front Camera`              | Resolusi kamera depan (MP) |
| 6   | `Back Camera`               | Resolusi kamera belakang (MP) |
| 7   | `Processor`                 | Nama prosesor perangkat |
| 8   | `Battery Capacity`          | Kapasitas baterai (mAh) |
| 9   | `Screen Size`               | Ukuran layar (inci) |
| 10  | `Launched Price (Pakistan)` | Harga saat rilis di Pakistan (PKR) |
| 11  | `Launched Price (India)`    | Harga saat rilis di India (INR) |
| 12  | `Launched Price (China)`    | Harga saat rilis di China (CNY) |
| 13  | `Launched Price (USA)`      | Harga saat rilis di USA (USD) |
| 14  | `Launched Price (Dubai)`    | Harga saat rilis di Dubai (AED) |
| 15  | `Launched Year`             | Tahun rilis perangkat |

2. Dataset Skor Prosesor (Android_SoC.csv & iOS_Performance.csv)
Dataset ini memiliki 210 baris dan 6 kolom, dengan rincian:
| No  | Nama Kolom   | Deskripsi |
|-----|-------------|-----------|
| 1   | `Platform`  | Sistem operasi (Android/iOS) |
| 2   | `Category`  | Kategori prosesor (Flagship/Mid-range/Entry) |
| 3   | `Device`    | Nama prosesor |
| 4   | `CPU Score` | Skor performa CPU |
| 5   | `GPU Score` | Skor performa GPU |
| 6   | `Total Score` | Skor total Antutu (CPU + GPU) |

3. Dataset Gabungan
Setelah proses penggabungan berdasarkan nama prosesor, dataset akhir memiliki 937 baris dan 16 kolom dengan tambahan kolom "Performance Score" dari "Total Score" dataset skor prosesor.
| No  | Nama Kolom                 | Deskripsi |
|-----|----------------------------|-----------|
| 1   | `Company Name`             | Merek smartphone |
| 2   | `Model Name`               | Model smartphone |
| 3   | `Mobile Weight (g)`        | Berat perangkat (gram) |
| 4   | `RAM (GB)`                 | Kapasitas RAM (GB) |
| 5   | `Front Camera (MP)`        | Resolusi kamera depan (MP) |
| 6   | `Back Camera (MP)`         | Resolusi kamera belakang (MP) |
| 7   | `Processor`                | Nama prosesor perangkat |
| 8   | `Battery Capacity (mAh)`   | Kapasitas baterai (mAh) |
| 9   | `Screen Size (inches)`     | Ukuran layar (inci) |
| 10  | `Launched Price (Pakistan/PKR)` | Harga saat rilis di Pakistan (PKR) |
| 11  | `Launched Price (India/INR)`    | Harga saat rilis di India (INR) |
| 12  | `Launched Price (China/CNY)`    | Harga saat rilis di China (CNY) |
| 13  | `Launched Price (USA/USD)`      | Harga saat rilis di USA (USD) |
| 14  | `Launched Price (Dubai/AED)`    | Harga saat rilis di Dubai (AED) |
| 15  | `Launched Year`                 | Tahun rilis perangkat |
| 16  | `Performance Score`              | Skor performa perangkat berdasarkan Antutu |

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

## Data Preparation
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
