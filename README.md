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

1. Meningkatkan pengalaman pengguna – Konsumen tidak perlu melakukan riset manual yang panjang untuk menemukan smartphone yang sesuai (Ricci et al., 2015).
2. Menghemat waktu dan tenaga – Dengan pemfilteran dan pengurutan otomatis, pengguna bisa langsung mendapatkan daftar smartphone terbaik sesuai preferensi (Aggarwal, 2016).
3. Membantu pengambilan keputusan yang lebih akurat – Rekomendasi didasarkan pada data objektif seperti spesifikasi, harga, dan tahun rilis, bukan hanya opini subjektif (Adomavicius & Tuzhilin, 2005).
4. Mempermudah pencarian produk di platform e-commerce – Sistem ini dapat diterapkan di berbagai platform belanja online untuk meningkatkan kepuasan pelanggan (Ricci et al., 2015).

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
![image.png](attachment:e22b619e-6479-44cb-9298-efd2266cba3c.png)
- Membandingkan kinerja model WSM dan LTR untuk menentukan model terbaik.
  
Dengan pendekatan ini, sistem rekomendasi smartphone yang dikembangkan diharapkan dapat memberikan rekomendasi yang akurat dan relevan berdasarkan spesifikasi smartphone, membantu konsumen dalam membuat keputusan pembelian yang lebih baik.
