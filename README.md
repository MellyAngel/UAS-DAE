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
<img width="1097" height="307" alt="Bar Chart 4" src="https://github.com/user-attachments/assets/a79785fb-f37d-4575-9296-aed176ab0884" />

Bar Chart di bawah ini menampilkan data perbandingan rata-rata durasi internnet sehari-hari(dalam menit) setiap provinsi
<img width="1097" height="307" alt="Bar Chart 3" src="https://github.com/user-attachments/assets/f854df2e-f6a1-4f04-a8c2-5c70e994511c" />

Bar Chart di bawah ini menampilkan data perbandingan rata-rata frekuensi membaca per minggu setiap provinsi
<img width="1097" height="307" alt="Bar Chart" src="https://github.com/user-attachments/assets/90512bb0-a517-4d51-959e-47d2f5ac759c" />

Bar Chart di bawah ini menampilkan data perbandingan rata-rata durasi membaca sehari-hari(dalam menit) setiap provinsi
<img width="1097" height="307" alt="Bar Chart 1" src="https://github.com/user-attachments/assets/d3293ad7-8e63-4f0d-840f-519ea76fb9ff" />

Bar Chart di bawah ini menampilkan data perbandingan rata-rata tingkat kegemaran membaca setiap provinsi
<img width="1097" height="307" alt="Bar Chart 2" src="https://github.com/user-attachments/assets/1ac77f78-0d90-4f22-930c-416450b497e4" />

Pie CHart di bawah ini menampilkan perbandingan seberapa tinggi akses ke internet dalam seminggu di semua provinsi
<img width="1097" height="307" alt="Pie Chart 4" src="https://github.com/user-attachments/assets/59bc1c1f-04c2-4f9f-ae2b-427a9ffcae65" />

Pie Chart di bawah ini menampilkan perbandingan seberapa sering penggunaan internet sehari-hari di semua provinsi
<img width="1097" height="307" alt="Pie Chart 3" src="https://github.com/user-attachments/assets/62b96743-7002-49f0-a807-d2524993c7f9" />

Pie Chart di bawah ini menampilkan perbandingan seberapa sering tingkat membaca dalam seminggu di semua provinsi
<img width="1097" height="307" alt="Pie Chart 2" src="https://github.com/user-attachments/assets/64297ef9-13aa-47bc-8059-78b136553553" />

Pie Chart di bawah ini menampilkan perbandingan seberapa sering tingkat membaca sehari-hari di semua provinsi
<img width="1097" height="307" alt="Pie Chart 1" src="https://github.com/user-attachments/assets/8ee70e36-d82f-4530-bae1-d8fb9ed12cdb" />

Pie Chart di bawah ini menampilkan perbandingan tingkat kegemaran membaca di semua provinsi
<img width="1097" height="307" alt="Pie Chart" src="https://github.com/user-attachments/assets/a7900b7e-8414-46de-a26c-71de365962e6" />

Scatter Plot di bawah ini menampilkan hubungan antara durasi internet sehari-hari dengan durasi membaca sehari-hari
<img width="1097" height="307" alt="Scatter Plot" src="https://github.com/user-attachments/assets/fd3fe116-1338-48ea-8798-88ce1f2528b7" />
