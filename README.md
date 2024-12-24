# EngiBot - Chatbot Informasi Akademik Fakultas Teknik Universitas Bengkulu
Engibot adalah chatbot berbasis LSTM (Long Short-Term Memory) yang dikembangkan untuk memberikan informasi akademik terkait Fakultas Teknik Universitas Bengkulu. 

## Anggota Kelompok
| Nama                  | NPM             | 
| ------------------    |---------------- |
| Seprina Dwi Cahyani   | G1A021010       |
| Redo Hariyadi         | G1A021034       | 
| Afzal Alfaraz         | G1A021098       | 

## Dataset
Dataset berasal dari [Portal Akademik](https://pak.unib.ac.id/) dan mencakup informasi akademik seperti jadwal kuliah dan pengisian KRS. Data yang diambil merupakan data yang berhubungan dengan informasi akademik, seperti jadwal kuliah, mata kuliah yang ditawarkan, kalender akademik, serta data terkait pengisian Kartu Rencana Studi (KRS) dan transkrip nilai mahasiswa. Dataset tersebut terdiri dari 144 classes dan disimpan dalam format JSON

Tahapan persiapan data meliputi:
+ **Data Cleaning**: Menghapus tanda baca dan mengubah teks ke huruf kecil.
+ **Lemmatisasi**: Menyederhanakan kata ke bentuk dasar.
+ **Tokenisasi**: Memecah teks menjadi kata individu.
+ **Padding**: Menyamakan panjang data.
+ **Encoding**: Mengubah teks menjadi format numerik.

## Hasil dan Pembahasan
![Grafik Evaluasi](https://github.com/seprinadwicahyani010/Engibot-ChatBot-Informasi-Akademik-Fakultas-Teknik-UNIB-/blob/0c150eb2790fb13c254b9dbd1387b497f5989088/Hasil%20Evaluasi/Matriks%20Akurasi%20dan%20Loss.png)
![image](https://github.com/user-attachments/assets/b1befbdc-d627-45db-85d7-6048ae17e631)

Hasil Evaluasi menunjukkan bahwa model EngiBot memiliki rata-rata akurasi yang sangat tinggi, yaitu **99.8%** dengan nilai loss terakhir sebesar 0.1030 setelah melalui 150 epoch pelatihan, serta mampu merespons dalam waktu kurang dari 1 detik pada sebagian besar kasus. 
