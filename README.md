# Telco-Customer-Churn_Machine-Learning

Konteks
Dalam industri telekomunikasi, customer memiliki kebebasan untuk memilih di antara sejumlah penyedia layanan yang berbeda untuk memenuhi kebutuhan mereka. Sebuah perusahaan telekomunikasi Telco tertarik untuk mengidentifikasi customer yang mungkin akan berhenti berlangganan (churn). Perusahaan berupaya merancang strategi yang efektif guna mempertahankan customer yang telah berlangganan, sehingga meminimalkan tingkat churn dan meningkatkan retensi customer. Peningkatan retensi customer itu penting karena proses memperoleh customer baru membutuhkan biaya lima hingga tujuh kali lebih mahal daripada mempertahankan customer lama (sumber: Forbes). Statistik menunjukkan peningkatkan tingkat retensi customer sebesar 5% meningkatkan keuntungan sebesar 25% hingga 95% (sumber: Harvard Business School).

Pernyataan Masalah
Selama ini tim pemasaran memberikan promo diskon secara merata kepada semua customer yang ada untuk mempertahankan mereka agar tidak berhenti menggunakan jasa layanan telekomunikasi. Dengan cara tersebut, tim pemasaran mengeluarkan anggaran cukup besar yang membuat biaya promo diskon menjadi membengkak dan melebihi budget. Oleh karena itu, tim pemasaran ingin mengetahui faktor apa saja yang mempengaruhi customer yang berhenti berlangganan atau churn berdasarkan data historis. Selanjutnya, tim pemasaran ingin mengetahui bagaimana cara untuk memprediksi pelanggan yang ada apakah akan churn atau tidak. Dengan mengetahui hal-hal tersebut tim pemasaran dapat membuat promosi yang prioritasnya hanya kepada customer yang akan churn, sehingga dapat meminimumkan anggaran promosi yang dikeluarkan.

Tujuan
Tim pemasaran dapat mengetahui faktor-faktor apa saja yang mempengaruhi customer untuk berhenti berlangganan / churn.
Perusahaan dapat membuat sebuah model machine learning untuk memprediksi customer yang akan berhenti berlangganan atau tidak. Dengan demikian, tim pemasaran dapat membuat promosi yang prioritasnya hanya kepada customer yang akan churn sehingga dapat meminimumkan anggaran promosi yang dikeluarkan.
Pendekatan Analitis
A. Analisis Data

Perusahaan bertujuan memahami perilaku customer yang berhenti berlangganan (churn) dan yang tidak. Untuk memahami customer, analisis akan dibagi ke dalam 3 kategori:

Demografi Customer: Meliputi faktor-faktor seperti jenis kelamin (gender), status senior (SeniorCitizen), status pernikahan (partner), dan jumlah tanggungan (dependents).
Jenis Layanan yang Dimiliki oleh Customer: Meliputi layanan-layanan seperti layanan telepon (phoneService), multiple lines, layanan internet (InternetService), keamanan online (OnlineSecurity), cadangan daring (OnlineBackup), dukungan teknis (TechSupport), layanan Streaming TV, dan Streaming Movies.
Informasi Customer: Menyertakan informasi mengenai jenis kontrak (Contract), tagihan tanpa kertas (paperlessBilling), metode pembayaran (PaymentMethod), biaya bulanan (MonthlyCharges), dan total biaya (TotalCharges).
B. Machine Learning

Dikarenakan dataset yang digunakan memiliki target kelas dan target kelas tersebut merupakan data kategorikal, maka kami akan membangun model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas seorang customer akan churn atau tidak berdasarkan riwayat data sebelumnya.

Evaluasi Metrik
Target (Churn) :

0 (No) : Customer lanjut berlangganan (Retained)

1 (Yes) : Customer berhenti berlangganan (Churned)

Gambar

TP : Jumlah customer yang memang benar berhenti berlangganan (Churned)
TN : Jumlah customer yang memang benar lanjut berlangganan (Retained)
Type of Error:

Type 1 erorr (FP) : False Positive ( Customer diprediksi akan churn, padahal aktualnya mereka tidak churn )
Konsekuensi: Dana promosi yang dikeluarkan kepada customer tersebut, seharusnya dapat digunakan untuk biaya operasional lain

Type 2 error (FN) : False Negative ( Customer diprediksi tidak churn, padahal aktualnya mereka churn)
Konsekuensi: Perusahaan perlu mengeluarkan dana yang lebih besar untuk mengakusisi kembali customer tersebut atau menambah customer baru.

Berdasarkan konsekuensinya, maka sebisa mungkin yang akan kita lakukan adalah membuat model yang harus mempertimbangkan untuk mengurangi Type Error 1 (False Positive) dan Type Error 2 (False Negative). Namun, lebih memfokuskan kepada FN karena mengeluarkan biaya yang lebih besar. Jadi nanti metrik utama yang akan kita gunakan adalah F2 (F2 Score).

Kesimpulan
Pada bagian demografi jumlah pelanggan terbanyak yang churn adalah mereka yang tidak mempunyai dependents. Akan tetapi Jika kita melihat dari tingkat churn nya, justru pelanggan yang berumur 65 tahun ke atas (senior citizen) memiliki tingkat churn yang lebih tinggi dibandingkan dengan yang lain.
Pada bagian layanan yang diberikan oleh perusahaan, kita bisa melihat kepuasaan pelanggan terhadap layanan yang mereka pilih. Contohnya, walaupun fiber optic memiliki total jumlah pelanggan terbanyak dibandingkan dengan pilihan lainnya, ia juga yang memiliki tingkat churn yang paling tinggi. Kita dapat melihat adanya kebutuhan internet menggunakan fiber optik yang tinggi akan tetapi layanan tersebut tidak dapat memenuhi kebutuhan pelanggannya. Hal ini dapat kita tindak lanjuti kepada tim terkait untuk memeriksa kembali layanan tersebut.
Berdasarkan informasi akun pelanggan, kita bisa lihat bahwa semakin lama nya pelanggan berlangganan dapat menaikan tingkat loyalitas mereka terhadap perusahaan. Lalu kita juga bisa menyimpulkan adanya sensitivitas pelanggan terhadap jumlah yang mereka harus bayarkan. Beberapa pelanggan ada yang membayar lebih dibandingkan oleh pelanggan yang memiliki total jumlah layanan yang sama. Ini dapat disebabkan oleh penyebaran promosi yang kurang baik.
Secara kesuluruhan, model yang dibangun memiliki kemampuan klasifikasi cukup baik dalam memprediksi dengan benar baik customer yang akan churn maupun yang tidak dengan melihat F2 Score 71.72% dan nilai ROC_AUC sebesar 75.15%. Model dapat mengetahui 69 % customer yang tidak churn dan 81% customer yang akan churn (berdasarkan recall). Namun, model cukup berjuang dalam memprediksi dengan jumlah yang tepat customer yang akan churn sebesar 49% (berdasarkan precision) dikarenakan dataset imbalanced.
Berdasarkan contoh hitungan pada business overview, terlihat bahwa dengan menggunakan model, perusahaan dapat meminimumkan biaya promosi/retensi sebesar 30% dibandingkan skenario tidak menggunakan model.
Rekomendasi
Untuk Perusahaan

Karena adanya pengaruh lamanya pelanggan berlangganan terhadap loyalitas, tim marketing dapat berfokus kepada orang orang yang memiliki tenure rendah terlebih dahulu
Banyaknya layanan yang akan digunakan oleh pelanggan tentu saja akan sesuai dengan kebutuhan mereka, oleh karna itu tim marketing selain memberikan promosi perlu juga mengedukasi pelanggan agar mereka mengetahui keuntungan apa yang mereka dapatkan jika menggunakan layanan tersebut.
Memberikan promosi paket layanan bermulai dari gabungan 3 jenis layanan, yang setidaknya didalam paket tersebut ada layanan phone dan internet serive, dikarenakan ke dua paket tersebut merupakan dasar dasar dari layanan yang lainnya.
Terkait Data

Menambahkan kolom tanggal bermulainya berlangganan, hal ini dapat berpengaruh terhadap efisiensi pemakaian machine learning, sehingga tidak perlu memeriksa pelanggan yang memang belum akan habis masa berlanggannya di bulan berikutnya.
Pada kolom usia akan lebih baik jika di isi oleh tanggal lahir atau umur pelanggan, sehingga kita dapat mendapatkan insight yang lebih banyak
Pada kolom dependents, seharusnya di isi oleh berapa jumlah dependents mereka. Dikarenakan ada kemungkinan perbedaan sifat pelanggan yang tidak memiliki, sedikit, atau banyak dependets.
Menambahkan kolom bekerja atau tidaknya dan juga berapa lama mereka telah bekerja, hal ini dapat membantu kita lebih memami buying power pelanggan.
Terkait Model

Penambahan data historis yang lebih lama, terutama customer yang churn agar mengurangi imbalance data yang signifikan
Model dapat ditingkatkan dengan melakukan tuning hyperparameter dengan nilai yang sudah didapat sebagai referensi dan menambahkan parameter lain
Pemilihan teknik resampling lain yang belum digunakan seperti ADASYN (Adaptive Synthetic)
Secara rutin pantau kinerja model dan perbarui dengan data untuk menjaga akurasi prediktifnya. Industri telekomunikasi dinamis, dan perilaku pelanggan dapat berubah seiring waktu, memengaruhi faktor-faktor yang mempengaruhi kemungkinan perpindahan.
Meskipun regresi logistik telah terbukti menjadi model terbaik sejauh ini, terus eksperimen dengan berbagai algoritma untuk melihat apakah model lain dapat menawarkan kinerja yang lebih baik.
