Rani Puspita Sari 
122450030
Resume VDI 1

THE VLDB JOURNAL " MAKING DATA VISUALIZATION MORE EFFICIENT AND EFFECTIVE : A SURVEY "

Visualisasi data mengubah data abstrak menjadi bentuk visual, hal ini membuat
visualisasi data sangat cocok untuk memberikan gambaran umum data besar dan
memudahkan interpretasi hasil analitik data. Artikel ini meninjau teknik - teknik yang membuat
visualisasi data lebih efisien dan efektif, saat ini permintaan pemrosesan data
terkait dengan volume, kecepatan, dan kebenaran data, muncul kebutuhan mendesak bagi
ahli basis data untuk membantu visualisasi data yang efisien dan efektif. 

Visualisasi data umumnya terdiri dari beberapa tahap, yaitu;
1. Impor data : Mengambil data dari sumber yang diinginkan
2. Persiapan data : Mempersiapkan data yang diimpor untuk visualisa dengan normalisasi nilai, koreksi entri yang salah, dan interpolasi nilai yang hilang
3. Manipulasi data : Memilih data yang akan divisualisasikan, termasuk operasi seperti penggabungan dan pengelompokkan
4. Pemetaan : Memetakan data ke primitif geometris seperti titik dan garis, bersama dengan atributnya
5. Rendering : Mengubah data geometris menjadi representasi visual.

Berdasarkan tahap tahap di atas, telah diidentifikasi arahan yang membuat visualisasi data menjadi lebih efisien dan efektif serta relevan .
1. Spesifikasi visualisasi : menyediakan berbagai cara bagi pengguna untuk menentukan apa ang mereka inginkan. Ini termasuk mendesain bahasa spesifikasi visualisasi untuk "Pemetaan" dan "Manipulasi Data".
2. Pendekatan efisien untuk visualisasi data : Untuk melibatkan pengguna dalam pipeline iteratif secara efektif, proses visualisasi harus efisien dan skalabel. Banyak penelitian telah mencoba menghubungkan dengan mesin pemrosesan data yang kuat dan menyesuaikan sistem yang ada untuk tugas visualisasi data.
3. Rekomendasi Visualisasi Data: Menentukan visualisasi secara tepat sulit bahkan bagi ahli. Oleh karena itu, penting bahwa sistem visualisasi dapat membimbing pengguna dengan memberikan rekomendasi. Beberapa sistem memungkinkan pengguna memberikan spesifikasi ambigu dan sistem akan melengkapi visualisasi secara otomatis atau memberikan rekomendasi.

Survei Terkait:
Survei yang ada sering fokus pada topik spesifik seperti visualisasi grafik, data terhubung, atau data berdimensi tinggi. Kami mengkaji teknik dari perspektif yang berbeda.
Untuk spesifikasi visualisasi, Mei et al. menilai klasifikasi dan bahasa visualisasi, sedangkan kami menyoroti penggunaan praktis bahasa-bahasa ini.
Untuk pendekatan efisien, Keim et al. membahas integrasi database, visualisasi, dan analisis data tanpa membahas efisiensi secara mendalam, sementara Idreos et al. membahas teknik untuk meningkatkan efisiensi dalam siklus eksplorasi data, tetapi fokus kami adalah pada cara membangun visualisasi secara efisien.

Spesifikasi visualisasi.
1. Spesifikasi Visualisasi Data
secara umum, bahasa visualisasi data terdiri dari tiga bagian.
- Data : -Records : Data yang perlu divisualisasikan.
          -Transformasi : Operasi pengelompokan, binning, filler dan penyortiran yang digunakan untuk mengubah data yang ditentukan.
- Marks atau petunjuk visual: Tipe, ukuran, legenda dan properti lain.
- Pemetaan: Memetakan data ke tanda yanng sesuai.
Operasi visual berbasis GUI biasanya diterjemahkan ke dalam bahasa visualisassi data.
2. Kategori Bahasa Visualisasi Data
- Strategi Umum: Kategorisasi bahasa visualisasi data sering kali didasarkan pada daya ungkapnya. Semakin rendah level bahasa, semakin ekspresif bahasa tersebut.
- Bahasa tingkat rendah: 
  Merujuk pada bahasa yang memerlukan pengguna untuk menentukan semua elemen pemetaan.
  Contoh:
  - Prefuse dan Flare: Perpustakaan visualisasi berbasis Java yang membungkus item visual sebagai kelas Java dengan banyak atribut visual, dan bahasa ini memetakan data ke atribut visual ini melalui fungsi yang telah ditentukan sebelumnya.
  - Protovis: Toolkit grafis berbasis JavaScript deklaratif yang menggunakan tanda grafis sederhana (batang, area, garis, dll.) dengan atribut visual yang ditentukan.
  - D3: Pengembangan dari Protovis yang lebih efektif dalam menangani interaksi pengguna (misalnya, brushing dan linking).
  - Vega dan Reactive Vega: Mirip dengan Protovis dan D3, tetapi menyediakan tata bahasa interaksi deklaratif yang dapat dikomposisikan.

Bahasa Visualisasi Tingkat Tinggi dan Alat Berbasis GUI
1. Bahasa Visualisasi Tingkat Tinggi:
   - Bahasa tingkat tinggi [2,3,16,18,36,70–73] menyederhanakan detail konstruksi visualisasi, seperti fungsi pemetaan dan beberapa properti untuk tanda visual seperti ukuran kanvas, legenda, dan lainnya.
   - ggplot2: Dibangun di atas karya Wilkinson dari tahun 2005, "The Grammar of Graphics", dan merupakan tata bahasa grafis berlapis yang tertanam dalam bahasa R.
   - Vega-Lite: Pengembangan dari Vega dan Reactive Vega yang mendukung desain interaksi yang dapat dikomposisikan dengan tata bahasa yang ringkas. Baru-baru ini, Altair membuat Vega-Lite tersedia untuk komunitas Python.
   - Echarts: Bahasa visualisasi deklaratif terbaru yang dirancang untuk mendukung pembuatan visualisasi cepat bagi non-programmer.
   - VizQL: Bahasa spesifikasi visualisasi dari sistem Polaris dan digunakan dalam Tableau
   - ZQL: Digunakan dalam Zenvisage dan menggunakan struktur tabular di mana setiap baris adalah spesifikasi visualisasi.
Dalam bahasa tingkat rendah, pengguna harus menentukan fungsi pemetaan, sedangkan dalam bahasa tingkat tinggi, pengguna hanya perlu menentukan tipe tanda (misalnya, batang) tanpa menentukan fungsi pemetaan.

2. Alat Visualisasi Berbasis GUI:
   - Alat berbasis GUI menawarkan cara yang lebih ramah pengguna untuk memberikan spesifikasi visualisasi dengan mengikuti prinsip "manipulasi langsung".
   - Beberapa alat GUI mutakhir termasuk Tableau, Qlik, Excel, Google Sheets, Amazon Quicksight, Microsoft Power BI, Google Fusion Tables, iVisDesigner, Lyra, Keshif, dan Data Illustrator. Gambar 4 menunjukkan contoh spesifikasi visual dalam Tableau menggunakan data keterlambatan penerbangan.

Pendekatan efisien visualisasi data.
Pada bagian ini, kita akan membahas pendekatan yang efisien untuk visualisasi data; ini penting karena siklus hidup visualisasi data selalu iteratif, dengan manusia sebagai bagian dari loop.
Terdapat tiga pendekatan utama, yaitu:
1. Visusalisasi Data Eksak
2. Visualisasi Data Approximate
3. Visualisasi Data Progresif
Secara keseluruhan, metode ini membantu dalam mengelola siklus visualisasi data yang iteratif, dengan fokus pada kecepatan, akurasi, dan refinemen bertahap dari visualisasi.

Mengintegrasikan Sistem Visualisasi dengan DBMS:
1. Masalah Integrasi Sistem: Menggunakan terjemahan query sering kali menimbulkan masalah karena banyak fungsionalitas yang berulang, yang mengarah pada teknik optimasi yang tidak terintegrasi antara sisi server (database) dan sisi klien (visualisasi). Misalnya, baik mesin database maupun alat visualisasi mungkin sama-sama mendukung operasi filter, sehingga sulit memilih tempat yang tepat untuk melakukan pemfilteran—di database atau di alat visualisasi.
2. Pendekatan Terintegrasi: - Ermac: Merupakan sistem manajemen visualisasi data (DVMS) yang mengintegrasikan pengambilan data dan rendering untuk mempercepat pembuatan visualisasi. Ermac mendukung dua hubungan: data (rekaman data yang akan divisualisasikan) dan skala (pemetaan dari rentang data ke rentang encoding visual). Visualisasi di Ermac diwakili oleh Rencana Visualisasi Logis (LVP) yang dikompilasi menjadi query mirip SQL, yang kemudian dapat dioptimalkan dengan teknik optimasi database tradisional.
                            - DeVIL: Pengembangan lebih lanjut dari Ermac yang menyediakan bahasa mirip SQL untuk mewakili visualisasi statis dan interaktif. DeVIL menggunakan relasi Marks dan Pixels untuk menyatakan visualisasi dalam query mirip SQL dan memungkinkan visualisasi interaktif dengan mengeksekusi query dalam visualisasi yang digabungkan dan relasi event secara iteratif. Ini membuat desain visualisasi lebih terstandarisasi dan kode lebih skalabel.
3. Pendekatan Pengelolaan Data: - Column Stores: Untuk aplikasi OLAP, tata letak data seperti baris dan kolom dapat mempengaruhi kinerja secara signifikan. 
                                - Indexes: Digunakan untuk meningkatkan kinerja pencarian dengan mengurangi jumlah rekaman yang harus diperiksa. Indeks memainkan peran penting dalam meningkatkan kinerja visualisasi data. Beberapa teknik termasuk: FlashView, imMens dan Nanocubes, Hashedcubes dan Gaussian Cubes.

Pendekatan Efisien untuk Visualisasi Data
1. Falcon: Falcon menggunakan teknik pengindeksan untuk mengurangi waktu interaksi saat melakukan brushing dan linking dalam visualisasi. Dalam sistem ini, visualisasi aktif adalah yang sedang berinteraksi dengan pengguna, sementara visualisasi lainnya bersifat pasif.
2. Komputasi Pararel: Komputasi paralel digunakan secara luas dalam pemrosesan query pada sistem visualisasi data.
3. Prediksi dan Prefetching: Prediksi dan prefetching adalah langkah penting dalam eksplorasi data, di mana pengguna sering kali terinspirasi untuk mengeksplorasi visualisasi berikutnya dari visualisasi sebelumnya. Dua jenis teknologi prefetching adalah visualisassi yang sedang dueksplorasi dan data historis.
Teknik-teknik ini berfokus pada peningkatan kecepatan eksplorasi dan efisiensi sistem visualisasi dengan memanfaatkan berbagai metode seperti pengindeksan, komputasi paralel, dan strategi prefetching berdasarkan data saat ini atau historis.

Pendekatan Pembelajaran Mesin: ForeCache
ForeCache adalah sistem yang menggunakan pembelajaran mesin untuk memprediksi fase eksplorasi pengguna dan merekomendasikan data berdasarkan jejak eksplorasi pengguna. Sistem ini terdiri dari dua tahap:
1. Prediksi Fase Analisis: Menggunakan model Support Vector Machine (SVM) untuk memprediksi fase eksplorasi pengguna berdasarkan posisi, pergeseran, dan informasi zoom.
2. Prediksi Data Tiles: Menggunakan strategi berbasis tindakan (Markov chain) dan strategi berbasis tanda tangan untuk merekomendasikan data yang telah di-pra-fetch. ForeCache mencapai akurasi prediksi 25% lebih tinggi dibandingkan strategi prediksi di XmdvTool.

-STUDI KASUS: Kyrix dan Tableau
Kyrix:
Kyrix menyediakan antarmuka spesifikasi visualisasi deklaratif di front-end dan pemrosesan visualisasi skala besar yang efektif di back-end. Ada dua aspek utama di Kyrix:
1.Spesifikasi Visualisasi di Front-end: Menggunakan konsep "canvas" dan "jump" untuk mendefinisikan visualisasi statis dan transisi antar visualisasi.
2. Pendekatan Efisien di Back-end: Menggunakan granularitas fetching dan strategi pengindeksan untuk mengelola data besar.

Tableau(TDE):
Tableau menggunakan mesin data yang dioptimalkan (TDE) untuk meningkatkan efisiensi visualisasi data. Beberapa optimasi meliputi:
1. Penyimpanan Kolom dan Kompresi: Menggunakan teknik penyimpanan dan kompresi berbasis kolom untuk mengurangi biaya I/O.
2. Reordering Operator: Menyusun ulang operator dalam rencana query SQL untuk meningkatkan efisiensi.
3. Reduksi Kardinalitas: Mengubah kolom dengan kardinalitas tinggi menjadi hierarki yang lebih tinggi untuk mengoptimalkan eksekusi query.
4. Dukungan Visualisasi Lainnya: Menyediakan informasi domain dan mendukung pelaporan progresif serta kontrol penghentian query.
Mesin data terbaru di Tableau 10 adalah Hyper, yang dirancang untuk sistem memori utama yang efisien dan digunakan dalam berbagai versi Tableau.

1. Pendekatan AQP (Approximate Query Processing):
- AQP adalah teknik untuk menghasilkan visualisasi perkiraan dalam waktu interaktif dengan menggunakan subset representatif dari data, yang mengorbankan sedikit kualitas untuk kecepatan.
- Sample+Seek: Sistem AQP yang menjawab query agregasi dengan kecepatan interaktif dan memberikan hasil visualisasi dalam batas kesalahan yang ditentukan pengguna. Sample+Seek menggunakan teknik pengambilan sampel seragam untuk query COUNT dan teknik measure-biased sampling untuk query SUM. Sistem ini juga memperkenalkan dua teknik pengindeksan untuk mempercepat pengambilan sampel.
- Pangloss: Sistem berbasis web yang menggunakan teknik dari Sample+Seek untuk menyediakan visualisasi perkiraan dengan cepat, sambil tetap menghitung hasil yang akurat di latar belakang. Pengguna dapat memverifikasi hasil perkiraan dengan hasil yang tepat melalui fitur "remember".

2. Pendekatan Berbasis Pengambilan Sampel Bertahap (Incremental Sampling-based):
- Pendekatan ini menghubungkan teknik query data bertahap dengan visualisasi data. Sistem menghasilkan visualisasi perkiraan berdasarkan sampel representatif dan secara bertahap meningkatkan ukuran sampel untuk meningkatkan kualitas visualisasi.
- - SampleAction: Alat untuk memvisualisasikan query agregasi pada dataset yang sangat besar. Visualisasi awal dibuat cepat dengan hasil agregasi parsial, dan seiring waktu, batas kesalahan semakin sempit dengan peningkatan ukuran sampel. Namun, terdapat fluktuasi signifikan antar visualisasi perkiraan bertahap.
- IncVisAge: Sistem berbasis web yang memperbaiki masalah fluktuasi pada SampleAction dengan algoritma ISplit. IncVisAge mendukung visualisasi garis tren dan peta panas dengan pembaruan visualisasi yang stabil. Algoritma ISplit membagi segmen tren untuk menghasilkan visualisasi yang lebih halus dan bermakna.

3. Pendekatan Berbasis Persepsi Manusia:
- Pendekatan ini memperhitungkan keterbatasan kognitif manusia dalam memahami visualisasi data. Teknik ini membantu menghasilkan visualisasi yang lebih efektif dengan mempertimbangkan bagaimana manusia memproses informasi visual.

Rekomendasi visualisasi
1. Tujuan: Sistem rekomendasi visualisasi bertujuan untuk mengurangi beban ini dengan merekomendasikan visualisasi yang baik secara otomatis.
2. Cara kerja: Sistem ini bekerja dengan menjelajahi semua kemungkinan visualisasi dan kemudian merekomendasikan visualisasi yang memiliki peringkat tertinggi. Namun, ruang pencarian untuk semua visualisasi ini sangat besar dan harus mempertimbangkan berbagai faktor, seperti pemilihan kolom yang akan divisualisasikan, transformasi data (misalnya, pengelompokan atau pembagian), pemilihan jenis tanda (mark types) seperti batang, garis, atau titik, dan jenis pengkodean untuk setiap tanda.

Sistem rekomendasi visualisasi menggunakan berbagai sinyal atau batasan untuk memangkas visualisasi yang "buruk" atau tidak relevan. Batasan ini bisa berasal dari pengguna atau pengetahuan yang sudah ada, seperti:
- Batasan yang Ditentukan Pengguna: Pengguna dapat menentukan elemen visualisasi yang diinginkan, seperti kolom atau data yang akan divisualisasikan.
- Batasan dari Pakar: Kombinasi variabel, transformasi, dan pengkodean visual tertentu mungkin tidak menghasilkan visualisasi yang valid. Contoh: Tipe tanda "pie" tidak bisa digabungkan dengan tipe pengkodean "height".
- Batasan Keras dan Lunak: Sistem seperti Draco memiliki batasan keras (harus dipenuhi, misalnya pengkodean "shape" tidak berlaku untuk nilai numerik) dan batasan lunak (digunakan untuk memberi peringkat visualisasi, misalnya lebih baik menggunakan sumbu X untuk nilai temporal).
Setelah memangkas ruang pencarian untuk visualisasi yang tidak relevan, sistem rekomendasi visualisasi akan mengenali visualisasi yang bermakna berdasarkan metrik atau aturan yang telah ditentukan. Beberapa sistem juga dapat memberi peringkat visualisasi menarik atau merekomendasikan top-k visualisasi kepada pengguna. 

1. Persiapan Data untuk Visualisasi Data: Data dunia nyata sering kali "kotor" dan visualisasi data yang kotor dapat menyesatkan pengguna. Masalah ini dikenal sebagai visualisasi yang bias dalam komunitas visualisasi data. Data yang diintegrasikan dari berbagai sumber bisa mengandung duplikasi. Oleh karena itu, data yang akan divisualisasikan harus dibersihkan melalui langkah-langkah seperti normalisasi nilai, deduplikasi, imputasi nilai yang hilang, dan deteksi outlier.
2. Studi: 
-Analisis What-if untuk Outlier (Scorpion): Sistem ini memungkinkan pengguna untuk mengidentifikasi outlier secara manual dari hasil query agregasi dan kemudian menghapus predikat yang menyebabkan outlier tersebut tanpa mempengaruhi data lainnya.
- Evaluasi Visualisasi dengan Data Hilang: Studi crowdsourcing yang mengukur faktor-faktor yang mempengaruhi akurasi respons, kualitas data, dan kepercayaan dalam interpretasi data deret waktu dengan nilai yang hilang. Studi ini mencoba berbagai metode imputasi (zero-filling, marginal mean, dan linear interpolation) dan cara menampilkan nilai yang diimputasi (highlight, downplay, annotation, dan information removal). Hasil evaluasi menunjukkan bahwa kualitas data yang dirasakan dan akurasi respons menurun seiring meningkatnya jumlah data yang hilang.
3. Peluang: 
- Mendeteksi Visualisasi yang Bias: Visualisasi yang terlihat baik mungkin sebenarnya bias, sehingga diperlukan deteksi otomatis untuk mengidentifikasi visualisasi seperti itu. Banyak penelitian mendekati masalah ini dari perspektif statistik, tetapi penting juga untuk mempelajari masalah ini dari sudut pandang data yang kotor.
- Pembersihan Data yang Berorientasi Tugas: Membersihkan dataset menjadi lebih mudah jika tugas yang ditargetkan sudah diketahui. Misalnya, hanya sebagian kecil data yang perlu dibersihkan, yang lebih hemat biaya daripada membersihkan seluruh dataset secara konvensional.

Kesimpulan
Visualisasi data adalah bidang yang berkembang pesat dengan banyak hasil 
penelitian baru dan sistem inovatif yang telah dikembangkan baru-baru ini. 
Penelitian dan praktisi dari berbagai bidang telah berkontribusi pada kesuksesan 
luar biasa dari visualisasi data, yang didorong oleh sebagian besar (jika tidak semua) domain dan aplikasi. 
Artikel ini terutama mengulas karya-karya terbaru dalam visualisasi data dari perspektif manajemen data. Secara khusus, kami telah secara komprehensif menjelaskan tentang spesifikasi visualisasi, metode efisien untuk visualisasi data, dan rekomendasi visualisasi. 
Seperti yang disebutkan sebelumnya, sebagian besar sistem visualisasi data komersial unggul dalam hal kemudahan penggunaan terkait spesifikasi visualisasi data. 
Namun, banyak praktisi masih menghadapi masalah efisiensi dan rekomendasi dalam sistem-sistem ini.
Oleh karena itu, kami juga membahas beberapa masalah terbuka di mana peneliti basis data dapat memberikan kontribusi signifikan untuk memajukan bidang visualisasi data.
