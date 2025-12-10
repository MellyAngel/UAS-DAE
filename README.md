## 1. Pendahuluan
Proyek ini dibuat untuk mencari tahu insight serta interpretasi dari dataset Indonesia Reading Interest yang memiliki berbagai macam data tentang kegemaran membaca masyarakat Indonesia, seperti :
1. Provinsi
2. Tahun
3. Frekuensi Akses ke Internet per minggu
4. Durasi Internet sehari-hari (dalam menit)
5. Kategori
6. Frekuensi Membaca per minggu
7. Jumlah bacaan per kuartal
8. Durasi Membaca sehari-hari (dalam menit)
9. Tingkat Kegemaran membaca

## 2. Data Preparation
Tahap ini dilakukan untuk menyiapkan data agar data siap di process untuk nantinya menghasilkan output berupa visualisasi yang diinginkan.
Pada tahap ini, node yang saya gunakan adalah :
- **CSV Reader** : ini berupa input awal yang digunakan untuk membaca dataset yang diinginkan
- **Column Renamer** : bagian ini mungkin kurang penting, tetapi ini dapat digunakan untuk mengganti nama kolom. Pada workflow saya, saya gunakan karena terdapat simbol aneh pada nama kolom sehingga saya ganti agar simbolnya hilang
- **Row Filter** : ini dapat digunakan untuk menghilangkan baris tertentu sesuai dengan yang kita inginkan. Disini saya gunakan untuk menghapus semua data dengan nama provinsi "Indonesia" karena Indonesia merupakan negara, bukan provinsi
- **String to Number** : bagian ini digunakan untuk mengubah data yang bertipe string/huruf menjadi numerik. Pada workflow saya terlihat bahwa data Frekuensi Akses ke Internet per minggu dan Durasi Internet sehari-hari (dalam menit) masih berupa string, sehingga saya ubah menjadi numerik
- **Missing Value** : bagian ini digunakan untuk mengisi data yang masih kosong. Disini daya menggunakan rounded mean untuk mengisi data kosong.

## 3. Data Process
Tahap ini memproses data yang sudah di proses agar menghasilkan kualitas data yang bagus untuk visualisasi.
Pada tahap ini, node yang saya gunakan adlaah : 
- **Normalizer** : bagian ini digunakan agar data-data yang ada memiliki skala pembanding yang sama
- **Column Filter** : bagian ini digunakan untuk mengambil data-data yang diperlukan untuk nantinya divisualisasikan

## Klasifikasi 
- **Rule Engine** : ini digunakan untuk mengklasifikasikan data-data yang ada sesuai dengan ketentuan yang telah kita buat. Disini saya gunakan untuk melihat seberapa tinggi akses ke internet per minggu, seberapa sering penggunaan internet sehari-hari, dll
- **Statistics view** : node ini saya gunakan untuk melihat Q1 dan Q3 untuk menentukan klasifikasi pada rule engine

## 4. Visualisasi
Tahap ini menghasilkan visualisasi dari data-data yang sudah di proses.
Pada tahap ini, node yang saya gunakan adalah :
- **Pie Chart** : Visualisasi ini menampilkan data dalam bentuk seperti pie. Disini saya gunakan untuk melihat perbandingan dari klasifikasi yang sudah saya buat menggunakan rule engine
- **Bar Chart** : Visualisasi ini menampilkan data dalam bentuk bar. Disini saya gunakan untuk membandingkan setiap data dari berbagai provinsi yang berbeda

## Insight dan Interpretasi 
Dari proyek ini, terlihat bahwa akses ke internet berpengaruh pada frekuensi membaca. Hal ini dimungkinkan karena dengan tingginya akses ke internet maka semakin memadai fasilitas untuk membaca serta lebih mudah untuk mencari bahan bacaan. Selain itu juga terlihat bahwa akses ke internet serta frekuensi membaca pada provinsi-provinsi yang ada masih belum merata. Pada klasifikasi yang telah dilakukan terlihat bahwa masih banyak orang yang frekuensi membacanya sedang masihlah sangat banyak sehingga masih bisa ditingkatkan agar penduduk-penduduk di Indonesia bisa lebih gemar membaca.

Bar Chart di bawah ini menampilkan data perbandingan rata-rata frekuensi akses ke internet per minggu setiap provinsi
<img width="1238" height="590" alt="image" src="https://github.com/user-attachments/assets/b3f6c0c7-46c4-4627-a1f5-61a7718b472e" />

Bar Chart di bawah ini menampilkan data perbandingan rata-rata durasi internnet sehari-hari(dalam menit) setiap provinsi
<img width="1262" height="580" alt="image" src="https://github.com/user-attachments/assets/847d3dd9-bcb0-464e-8ee8-732d95c6d694" />

Bar Chart di bawah ini menampilkan data perbandingan rata-rata frekuensi membaca per minggu setiap provinsi
<img width="1260" height="560" alt="image" src="https://github.com/user-attachments/assets/4ec780a4-7684-4aae-adc9-32778c1f4d55" />

Bar Chart di bawah ini menampilkan data perbandingan rata-rata durasi membaca sehari-hari(dalam menit) setiap provinsi
<img width="1259" height="527" alt="image" src="https://github.com/user-attachments/assets/78b95387-a0f2-4681-b8fe-d89cce4ff8ff" />

Bar Chart di bawah ini menampilkan data perbandingan rata-rata tingkat kegemaran membaca setiap provinsi
<img width="1256" height="559" alt="image" src="https://github.com/user-attachments/assets/4acfd404-57c8-4aa9-afdd-2bcbf590fa54" />

Pie Chart di bawah ini menampilkan perbandingan seberapa tinggi akses ke internet dalam seminggu di semua provinsi
<img width="1031" height="755" alt="image" src="https://github.com/user-attachments/assets/613a8038-6508-4eb6-8d0a-fbc103260e16" />

Pie Chart di bawah ini menampilkan perbandingan seberapa sering penggunaan internet sehari-hari di semua provinsi
<img width="1057" height="728" alt="image" src="https://github.com/user-attachments/assets/c0fb823f-d392-4424-8226-f30ddb90780a" />

Pie Chart di bawah ini menampilkan perbandingan seberapa sering tingkat membaca dalam seminggu di semua provinsi
<img width="1103" height="728" alt="image" src="https://github.com/user-attachments/assets/13bd64da-3f0d-4391-9f7b-73a5aa9bfd99" />

Pie Chart di bawah ini menampilkan perbandingan seberapa sering tingkat membaca sehari-hari di semua provinsi
<img width="1116" height="747" alt="image" src="https://github.com/user-attachments/assets/827cb579-224f-4faa-a474-90c9d59744ad" />

Pie Chart di bawah ini menampilkan perbandingan tingkat kegemaran membaca di semua provinsi
<img width="1074" height="727" alt="image" src="https://github.com/user-attachments/assets/3e7d12da-9c82-431d-ade8-7231f1dd7ba8" />

Scatter Plot di bawah ini menampilkan hubungan antara durasi internet sehari-hari dengan durasi membaca sehari-hari
<img width="1112" height="595" alt="image" src="https://github.com/user-attachments/assets/57b357da-e3a9-4b4b-8493-6ebc2e98f5ea" />

