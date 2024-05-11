# Laporan Praktikum UTS_PCD
# A. Tahapan cara menyelesaikan proyek
Nama : Kevin Nugraha Santika Permana

NIM  : 202231017

1. Deteksi warna pada citra. 
Menganalisis yang terjadi pada citra
Deteksi warna pada citra menggunakan pendekatan pemrosesan citra digital untuk mengidentifikasi dan menyoroti piksel-piksel dengan warna tertentu dalam gambar. Pertama-tama, gambar 'kevinnn.jpg' diimpor dan divisualisasikan menggunakan library seperti OpenCV, NumPy, dan Matplotlib. Setelah itu, gambar dibagi menjadi saluran warna merah, hijau, dan biru, memungkinkan kita untuk melihat kontribusi masing-masing warna terhadap gambar asli. Ini membantu dalam memahami distribusi warna dalam gambar dan bagaimana warna-warna tersebut berinteraksi.

Kemudian, dilakukan identifikasi rentang warna yang ingin dideteksi dengan menentukan nilai ambang batas (threshold) untuk setiap saluran warna yang diinginkan. Contohnya, kita dapat menetapkan ambang batas untuk warna biru, yang memungkinkan kita untuk mengidentifikasi piksel-piksel dengan intensitas warna biru dalam rentang tertentu. Proses ini melibatkan konversi citra ke format HSV (Hue, Saturation, Value) untuk pemrosesan warna yang lebih tepat.

Setelah ambang batas ditentukan, kita menggunakan mask untuk menangkap piksel-piksel yang memenuhi ambang batas tersebut, menciptakan citra biner yang menunjukkan area-area dengan warna yang sesuai dengan kriteria yang telah ditetapkan. Ini memungkinkan kita untuk mengisolasi area-area tertentu dalam gambar yang memiliki warna yang ingin kita soroti, seperti misalnya hanya menampilkan warna biru dalam gambar.

Hasil dari deteksi warna kemudian divisualisasikan kembali dengan menerapkan mask pada gambar asli. Piksel-piksel yang tidak memenuhi ambang batas akan diubah menjadi warna hitam atau putih, sementara piksel yang memenuhi ambang batas akan tetap terlihat seperti gambar aslinya. Proses ini membantu kita dalam analisis dan pemrosesan lanjutan, seperti pengenalan objek berdasarkan warna atau pengolahan informasi tertentu dalam gambar yang relevan dengan deteksi warna yang dilakukan.

2. Membuat dan Menganalisis Histrogram
Histogram adalah representasi visual dari distribusi intensitas piksel dalam sebuah gambar. Pada codingan histogram yang disajikan, dilakukan pembuatan histogram untuk masing-masing saluran warna (merah, hijau, biru) dalam gambar 'kevinnn.jpg'. Hal ini memungkinkan kita untuk melihat sebaran intensitas warna pada setiap saluran warna, yang dapat memberikan informasi penting tentang karakteristik gambar.

Pertama-tama, histogram asli dari gambar dihasilkan, menunjukkan sebaran intensitas keseluruhan piksel dalam citra. Ini memberikan gambaran umum tentang distribusi warna dalam gambar tersebut, apakah gambar tersebut lebih cenderung memiliki intensitas warna tertentu yang mendominasi, ataukah distribusinya lebih merata di seluruh rentang warna.

Selanjutnya, histogram untuk masing-masing saluran warna (merah, hijau, biru) dibuat, memungkinkan kita untuk memahami kontribusi masing-masing warna terhadap gambar secara terpisah. Misalnya, histogram merah menunjukkan seberapa banyak piksel dalam gambar yang memiliki intensitas warna merah, histogram hijau menunjukkan seberapa banyak piksel dengan intensitas warna hijau, dan demikian pula dengan histogram biru.

Analisis histogram dapat memberikan wawasan tentang karakteristik gambar yang lebih mendalam. Misalnya, jika histogram merah menunjukkan puncak yang tinggi, itu mungkin menandakan adanya banyak area merah dalam gambar. Begitu juga dengan hijau dan biru. Informasi ini penting dalam pengolahan gambar lebih lanjut, seperti segmentasi berbasis warna atau analisis lanjutan yang membutuhkan informasi intensitas warna.

Histogram juga membantu dalam pemrosesan gambar dan manipulasi warna. Misalnya, dengan memahami distribusi intensitas warna, kita dapat menerapkan teknik-teknik seperti equalization untuk meningkatkan kontras atau menyesuaikan kecerahan gambar secara lebih presisi. Analisis histogram memberikan dasar yang kuat untuk pemrosesan gambar yang lebih lanjut dan pemahaman yang lebih baik tentang komposisi warna dalam gambar.

3. Mencari dan mengurutkan ambang batas terkecil sampai dengan terbesar. 
- Warna Biru:
Rentang nilai hue (H) dari 100 hingga 130 sesuai dengan rentang warna biru yang umum terjadi dalam gambar. Nilai hue dalam format HSV mengukur spektrum warna, di mana nilai antara 100 hingga 130 cenderung mewakili warna biru yang diinginkan.
Rentang nilai saturasi (S) dari 50 hingga 255 dan nilai intensitas (V) dari 50 hingga 255 dipilih agar deteksi warna biru tetap efektif pada berbagai tingkat kecerahan dan saturasi warna biru.

- Warna Merah:
Nilai ambang untuk warna merah diatur berdasarkan sifat lingkaran nilai hue dalam format HSV. Nilai ambang yang diberikan (0-10 dan 170-180) mengatasi batasan perubahan nilai hue dari 180 kembali ke 0, sehingga mencakup rentang warna merah yang melintasi titik tersebut.
Rentang nilai saturasi (S) dari 50 hingga 255 dan nilai intensitas (V) dari 50 hingga 255 dipilih agar deteksi warna merah tetap efektif pada berbagai tingkat kecerahan dan saturasi warna merah.

- Warna Hijau:
Rentang nilai hue (H) dari 50 hingga 80 dipilih karena rentang ini mewakili warna hijau yang umum terjadi dalam gambar. Nilai hue yang rendah mencerminkan warna hijau yang lebih gelap, sedangkan nilai hue yang tinggi mencerminkan warna hijau yang lebih terang.
Rentang nilai saturasi (S) dari 50 hingga 255 dan nilai intensitas (V) dari 50 hingga 255 dipilih agar deteksi warna hijau tetap efektif pada berbagai tingkat kecerahan dan saturasi warna hijau.

- Warna "None" (Selain Biru, Merah, dan Hijau):
Nilai-nilai untuk warna "None" diambil dari seluruh rentang warna yang tidak termasuk dalam rentang biru, merah, dan hijau yang telah ditentukan sebelumnya.
Dalam ruang warna HSV, nilai hue (H) dari 0 hingga 180 mencakup seluruh spektrum warna. Oleh karena itu, nilai-nilai yang tidak termasuk dalam rentang warna biru, merah, dan hijau dapat didefinisikan sebagai nilai yang berada di luar ambang batas yang telah ditentukan untuk warna-warna tersebut.
Rentang nilai saturasi (S) dari 0 hingga 255 dan nilai intensitas (V) dari 0 hingga 255 digunakan untuk mencakup seluruh tingkat kecerahan dan saturasi warna "None" yang mungkin ada dalam gambar.

# B. Teori yang mendukung mengenai projek
Tentu, mari kita jabarkan lebih mendalam setiap poin dalam penjelasan teoritis mengenai projek terkait:

- Pemrosesan Citra Digital
Pemrosesan citra digital melibatkan serangkaian operasi untuk memanipulasi citra digital secara komputasional. Ini mencakup transformasi seperti perubahan skala, rotasi, dan pergeseran; filtrasi seperti deteksi tepi dan pengaburan; segmentasi untuk membagi citra menjadi area-area yang berbeda; dan analisis statistik untuk mengekstrak informasi seperti distribusi piksel, kecerahan, dan tekstur.

- Model Warna
Model warna adalah cara untuk merepresentasikan warna dalam citra. Model RGB (Red, Green, Blue) adalah model yang paling umum digunakan di mana setiap warna ditentukan oleh campuran intensitas dari ketiga warna primer tersebut. Model lain seperti HSV (Hue, Saturation, Value) memberikan representasi yang lebih intuitif untuk mengontrol warna.

- Deteksi Warna
Deteksi warna adalah proses mengidentifikasi dan mengisolasi area-area tertentu dalam citra berdasarkan nilai warnanya. Pengaturan ambang batas (thresholding) adalah teknik dasar di mana nilai piksel di atas ambang batas dianggap sebagai area yang diminati, sedangkan yang di bawah ambang batas dianggap sebagai latar belakang.

- Histogram Warna
Histogram warna adalah representasi grafis dari distribusi frekuensi nilai-nilai warna dalam citra. Histogram ini membantu memahami sebaran intensitas warna, termasuk informasi tentang warna dominan, kontras, dan kejenuhan.

- NumPy dan Matplotlib
NumPy adalah pustaka Python yang kuat untuk komputasi numerik, yang digunakan dalam operasi matematika dan manipulasi data dalam citra seperti perhitungan histogram. Matplotlib adalah pustaka visualisasi yang digunakan untuk membuat grafik dan plot, termasuk menampilkan citra dan histogram secara visual.

- OpenCV
OpenCV (Open Source Computer Vision Library) adalah pustaka yang sangat populer untuk pemrosesan citra dan visi komputer. OpenCV menyediakan berbagai fungsi dan algoritma yang digunakan untuk operasi dasar seperti deteksi tepi, segmentasi, ekstraksi fitur, dan lainnya.

- Visi Komputer
Visi komputer adalah bidang studi yang berkaitan dengan analisis dan interpretasi informasi visual dari dunia nyata oleh komputer. Ini melibatkan pengenalan pola, pemahaman konteks, dan pengambilan keputusan berbasis visual seperti pengenalan objek dan deteksi pola warna.

- Algoritma Segmentasi
Algoritma segmentasi digunakan untuk membagi citra menjadi bagian-bagian yang berbeda berdasarkan karakteristik tertentu seperti warna, tekstur, atau intensitas. Algoritma seperti segmentasi berbasis ambang batas, segmentasi berbasis objek, dan segmentasi berbasis wilayah digunakan tergantung pada kompleksitas citra dan tujuan analisisnya.

- Ekstraksi Fitur Warna
Ekstraksi fitur warna adalah proses mengidentifikasi dan mengekstrak informasi penting dari distribusi warna dalam citra. Fitur-fitur seperti histogram warna, tekstur, kecerahan, dan kejenuhan digunakan untuk mewakili informasi warna yang relevan untuk analisis lebih lanjut.

- Penerapan dalam Aplikasi
Konsep-konsep dan teknik-teknik yang dibahas di atas diterapkan dalam berbagai aplikasi praktis seperti pengenalan wajah, deteksi objek, pengolahan citra medis, pemantauan visual, dan bahkan pengembangan sistem kecerdasan buatan. Integrasi yang cermat dari konsep-konsep ini dalam aplikasi praktis menghasilkan solusi yang efektif dan efisien dalam menangani tantangan dalam analisis dan manipulasi citra digital.




