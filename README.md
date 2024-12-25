# EngiBot - Chatbot Informasi Akademik Fakultas Teknik Universitas Bengkulu
### Anggota Kelompok
| Nama                  | NPM             | 
| ------------------    |---------------- |
| Seprina Dwi Cahyani   | G1A021010       |
| Redo Hariyadi         | G1A021034       | 
| Afzal Alfaraz         | G1A021098       | 

Engibot adalah chatbot berbasis LSTM (Long Short-Term Memory) yang dikembangkan untuk memberikan informasi akademik terkait Fakultas Teknik Universitas Bengkulu. Engibot dibuat untuk mengatasi kendala yang sering dihadapi mahasiswa baru dalam menggunakan portal akademik. Portal akademik adalah sistem informasi penting yang digunakan mahasiswa untuk mengakses berbagai data terkait studi, seperti jadwal kuliah, KRS, nilai, dan kalender akademik. Namun, mahasiswa baru sering kesulitan memahami cara penggunaan portal ini, seperti pengisian KRS, pencarian jadwal kuliah, atau memahami prosedur administratif lainnya. Untuk itu, Engibot dikembangkan sebagai solusi berbasis chatbot yang dapat memberikan panduan dan informasi secara cepat melalui interaksi percakapan.

## Dataset
Dataset berasal dari [Portal Akademik](https://pak.unib.ac.id/) dan mencakup informasi akademik seperti jadwal kuliah dan pengisian KRS. Data yang diambil merupakan data yang berhubungan dengan informasi akademik, seperti jadwal kuliah, mata kuliah yang ditawarkan, kalender akademik, serta data terkait pengisian Kartu Rencana Studi (KRS) dan transkrip nilai mahasiswa. Dataset tersebut terdiri dari 144 classes dan disimpan dalam format JSON

Tahapan persiapan data meliputi:
+ **Data Cleaning**: Menghapus tanda baca dan mengubah teks ke huruf kecil.
+ **Lemmatisasi**: Menyederhanakan kata ke bentuk dasar.
+ **Tokenisasi**: Memecah teks menjadi kata individu.
+ **Padding**: Menyamakan panjang data.
+ **Encoding**: Mengubah teks menjadi format numerik.

## Model
Model EngiBot dirancang menggunakan arsitektur Long Short-Term Memory (LSTM). Berikut adalah rincian arsitektur yang digunakan:
| Layer (type)                         | Output Shape                |         Param # |
| -------------------------------------|-----------------------------|-----------------|
| input_layer_9 (InputLayer)           | (None, 13)                  |               0 |
| embedding_9 (Embedding)              | (None, 13, 20)              |           7,480 |
| lstm_9 (LSTM)                        | (None, 13, 32)              |           6,784 |
| dropout_8 (Dropout)                  | (None, 13, 32)              |               0 |
| flatten_9 (Flatten)                  | (None, 416)                 |               0 |
| dense_9 (Dense)                      | (None, 144)                 |          60,048 |

- Input Layer: Mengambil data dalam bentuk tokenized sequences dengan panjang yang sudah dipadatkan (padded).
- Embedding Layer: Menyandikan kata-kata menjadi representasi vektor dengan dimensi 20 untuk memahami hubungan antar kata.
- LSTM Layer: Sebuah lapisan LSTM dengan 32 unit yang dapat menangkap dependensi temporal dalam data percakapan.
- Dropout Layer: Dengan dropout sebesar 0.5 untuk mengurangi overfitting.
- Flatten Layer: Mengubah data dari bentuk multi-dimensi menjadi vektor satu dimensi untuk input ke lapisan berikutnya.
- Dense Layer: Lapisan fully connected dengan fungsi aktivasi softmax untuk menghasilkan probabilitas untuk masing-masing dari 144 kelas.

## Hasil dan Pembahasan
#### Grafik Akurasi dan Loss
![Grafik Evaluasi](https://github.com/seprinadwicahyani010/Engibot-ChatBot-Informasi-Akademik-Fakultas-Teknik-UNIB-/blob/0c150eb2790fb13c254b9dbd1387b497f5989088/Hasil%20Evaluasi/Matriks%20Akurasi%20dan%20Loss.png)
Evaluasi dilakukan dengan melihat perkembangan nilai loss dan akurasi model selama proses pelatihan. Dari grafik tersebut, terlihat bahwa seiring bertambahnya epoch, nilai loss cenderung menurun, yang menandakan bahwa model semakin baik dalam memprediksi data latih. Sebaliknya, nilai akurasi meningkat, menunjukkan bahwa model semakin akurat dalam klasifikasi. 

#### Output
![image](https://github.com/user-attachments/assets/b1befbdc-d627-45db-85d7-6048ae17e631)
Hasil Evaluasi menunjukkan bahwa model EngiBot memiliki rata-rata akurasi yang sangat tinggi, yaitu **99.8%** dengan nilai loss terakhir sebesar 0.1030 setelah melalui 150 epoch pelatihan. Hasil ini menunjukkan bahwa model belajar dengan baik dan tidak mengalami overfitting atau underfitting yang signifikan, karena kedua metrik tersebut stabil mendekati nilai optimal di akhir proses pelatihan.

## Kesimpulan
Chatbot ini berhasil menjawab pertanyaan-pertanyaan terkait informasi akademik, seperti pengisian KRS dan akses ke transkrip nilai, sesuai dengan kebutuhan pengguna. Pembuka dan penutup yang ramah semakin memperkuat kualitas interaksi, menciptakan pengalaman pengguna yang positif. Dengan demikian, chatbot ini diharapkan dapat menjadi solusi yang bermanfaat bagi mahasiswa dalam mengatasi berbagai kesulitan terkait urusan akademik, terutama dalam hal mendapatkan informasi secara cepat dan akurat melalui layanan chatbot otomatis.
