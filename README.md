# Proyek Pertama: Menyelesaikan Permasalahan Human Resources (Belajar Penerapan Data Science)

## Business Understanding

### Latar Belakang Bisnis
Jaya Jaya Maju adalah perusahaan multinasional yang telah berdiri sejak tahun 2000 dan memiliki lebih dari 1.000 karyawan yang tersebar di seluruh negeri. Walaupun telah berkembang pesat, perusahaan menghadapi tantangan signifikan dalam mengelola karyawan, terutama tingginya **attrition rate** atau tingkat keluar karyawan. Dengan angka attrition yang melebihi **10%**, perusahaan mulai merasakan dampak negatif seperti:
- **Biaya Rekrutmen Tinggi**: Berdasarkan karakteristik perusahaan yang memiliki lebih dari 1.000 karyawan, biaya yang dikeluarkan untuk proses rekrutmen dan pelatihan karyawan baru meningkat seiring tingginya angka pergantian karyawan. Hal ini mencakup biaya iklan lowongan kerja, seleksi, onboarding, dan pelatihan.
- **Penurunan Produktivitas**: Tingginya pergantian karyawan menyebabkan hilangnya pengalaman dan keterampilan yang dibutuhkan untuk mencapai target bisnis. Data dalam dataset seperti **YearsAtCompany** dan **YearsWithCurrManager** dapat membantu mengukur kontribusi pengalaman terhadap produktivitas.
- **Penurunan Kepuasan Karyawan**: Indikator kepuasan seperti **Job Satisfaction**, **Work-Life Balance**, dan **Environment Satisfaction** dalam dataset menunjukkan pentingnya mengidentifikasi ketidakpuasan lebih awal untuk mencegah gelombang keluar karyawan.

Manajemen HR di Jaya Jaya Maju menyadari pentingnya memahami faktor-faktor penyebab attrition agar dapat menyusun strategi yang tepat untuk **meningkatkan retensi karyawan** dan **mengurangi attrition rate** secara signifikan.

### Permasalahan Bisnis
Permasalahan bisnis yang akan diselesaikan melalui proyek ini adalah:

1. Faktor internal apa yang paling berpengaruh terhadap risiko karyawan keluar?
2. Seberapa akurat model prediksi dalam mengklasifikasikan karyawan yang akan resign?

### Cakupan Proyek
Proyek ini mencakup seluruh tahapan proses data science, antara lain:

- Mengumpulkan dan mengolah data karyawan Jaya Jaya Maju.
- Eksplorasi dan pemahaman data yang diberikan.
- Pra-pemrosesan data dan transformasi fitur.
- Pembuatan dan evaluasi model _machine learning_ (_Random Forest Classifier_).
- Analisis _feature importance_ dan korelasi.
- Pembuatan visualisasi data interaktif.
- Pengembangan _business dashboard_ menggunakan Looker Studio.
- Memberikan rekomendasi berdasarkan hasil analisis data.

### Persiapan

Sumber data: [Data Karyawan Jaya Jaya Maju](https://github.com/dicodingacademy/dicoding_dataset/blob/main/employee/employee_data.csv)

Setup environment:
- Proyek ini dapat dijalankan dengan mudah menggunakan Google Colabolatory (Colab), yang menyediakan *environment* siap pakai dengan sebagian besar dependensi yang sudah **terinstal**.
- Namun jika ingin menjalankan proyek ini secara local di komputer pribadi, disarankan untuk menggunakan virtual environment untuk mengelola dependensi proyek:

**1. Membuat Virtual Environment (opsional, untuk lokal)**:
Buka terminal atau command prompt, lalu navigasikan ke direktori proyek Anda. Jalankan perintah berikut:

```Bash
python -m venv venv
```

**2. Mengaktifkan Virtual Environment (opsional, untuk lokal)** :
- Windows:
```Bash
.\venv\Scripts\activate
```

- macOS / Linux:
```Bash
    source venv/bin/activate
```

**3. Instalasi Dependensi** :
- Baik di Google Colab maupun di _environment_ lokal (setelah mengaktifkan _virtual environment_), Anda mungkin perlu menginstal beberapa library tambahan yang tidak tersedia secara default. Pastikan Anda berada di direktori proyek dan jalankan perintah berikut:
```Bash
    pip install -r requirements.txt
```
- Catatan: Jika ada library yang perlu diinstal di Colab, Anda bisa menambahkannya di sel kode awal _notebook_ Colab Anda dengan:
```Bash
!pip install nama_library
```
- Catatan: Untuk menjalankan _prediction notebook_ dibutuhkan file yang ada di folder model.


## **Cara Menjalankan Proyek**
**Menggunakan Google Colaboratory (Direkomendasikan)**

1. **Buka _Notebook_** : Unggah atau buka file notebook .ipynb proyek ini di Google Colab.
2. **Jalankan Semua Sel** : Pastikan Anda menjalankan semua sel kode secara berurutan, dari atas ke bawah. Ini akan memproses data, melatih model (jika ada), dan menyiapkan dashboard.
3. **Akses Dashboard** : Untuk mengakses dashboard di Looker Studio, gunakan tautan yang disediakan di bagian "Business Dashboard" di bawah ini.


## **Menjalankan Secara Lokal (Opsional)**

Jika telah melakukan langkah-langkah Setup Environment di atas untuk menjalankan proyek secara lokal:
1. Pastikan Virtual Environment Aktif: Di terminal atau command prompt, pastikan Anda telah mengaktifkan virtual environment.
2. Jalankan Skrip Utama: Navigasikan ke direktori utama proyek Anda. Kemudian, jalankan _file Python_ utama proyek Anda. Jika _file_ utama Anda adalah main.py, app.py, atau dashboard.py (sesuaikan dengan nama file Anda):
```Bash
    python nama_file_utama_anda.py
```
3. Akses Dashboard: Setelah skrip berhasil dijalankan, jika dashboard Anda di-hosting secara lokal, alamat akses biasanya akan ditampilkan di terminal (misalnya, http://127.0.0.1:8050/ atau http://localhost:5000/). Namun, untuk dashboard Looker Studio, Anda cukup mengakses tautan  yang di [Employee Attrition Analysis - Jaya Jaya Maju](https://lookerstudio.google.com/reporting/6453f890-0c91-43ed-af4b-1df33392f0b3).


## Business Dashboard

*Business dashboard* yang dibuat menggunakan Looker Studio dirancang untuk memberikan visibilitas dan *insight* yang cepat kepaada Manajemen dan Departemen HR tentang faktor-faktor attriotion di Jaya Jaya Maju. Saat ini dashboard dapat diakses melalui [Employee Attrition Dasboard Jaya Jaya Maju](https://lookerstudio.google.com/reporting/6453f890-0c91-43ed-af4b-1df33392f0b3). _Dashboard_ ini menampilkan akan menampilkan fitur-fitur utama berikut:
1. _Total Employees_ – Menampilkan jumlah total karyawan yang dipekerjakan dalam perusahaan, yaitu 1,470.
2. _Actual Attrition by JobRole_ – Memvisualisasikan jumlah karyawan yang meninggalkan perusahaan berdasarkan peran pekerjaan mereka, termasuk _Sales Representative, Research Scientist, Sales Executive, Healthcare Representative, Human Resources, Manufacturing Director, Laboratory Technician, Manager_, dan _Research Director_.
3. _Internal Factors_ – Menyajikan faktor-faktor internal yang mempengaruhi tingkat attrisi, seperti _MonthlyIncome, Age, DailyRate, TotalWorkingYears, MonthlyRate, DistanceFromHome, HourlyRate, OverTime-Yes, YearsAtCompany,_ dan _NumCompaniesWorked_.
4. _Predicted Resign_ – Memprediksi jumlah karyawan yang akan meninggalkan perusahaan berdasarkan departemen dan frekuensi perjalanan mereka, mencakup _BusinessTravel, Research & Development, Sales,_ dan _Human Resources_ dengan kategori perjalanan seperti _Travel Frequently_ dan _Non Travel_.
5. _Department / Predicted Attrition_ – Menampilkan prediksi tingkat attrisi berdasarkan departemen dan frekuensi perjalanan, dengan kategori perjalanan seperti _Travel Rarely, Travel Frequently_,_ dan _Non Travel_.

![Employee Attrition Dasboard Jaya Jaya Maju]()


## Conclusion

Proyek ini telah berhasil menangani masalah tingkat attrisi di Jaya Jaya Maju melalui penerapan solusi data science yang menyeluruh. Hasil analisis data menunjukkan bahwa karyawan yang berpotensi mengalami attrisi memiliki pola karakteristik yang serupa, yaitu sebagai berikut:

- **Faktor Internal**: Karyawan dengan pendapatan bulanan lebih rendah, pengalaman kerja lebih singkat, atau jarak rumah ke kantor yang lebih jauh memiliki kecenderungan lebih tinggi untuk meninggalkan perusahaan.
- **Peran Pekerjaan**: Posisi tertentu seperti _Laboratory Technician, Sales Representative,_ dan _Research Scientist_ menunjukkan angka attrisi yang lebih tinggi dibandingkan peran lainnya.
- **Departemen & Frekuensi Perjalanan**: Karyawan di departemen _Sales_ dan _Research & Development_ dengan kategori perjalanan _Travel Frequently_ memiliki angka attrisi yang lebih tinggi.

- Konfirmasi ini secara langsung menjawab kebutuhan perusahaan akan identifikasi faktor pendorong utama dan karakteristik karyawan berisiko.

- Proyek ini juga membuktikan bahwa penerapan _machine learning_ sangat efektif dalam memperkirakan kemungkinan attrisi karyawan. Model yang dikembangkan memungkinkan deteksi dini terhadap individu berisiko tinggi, sebuah kemampuan penting untuk mengurangi biaya rekrutmen serta mempertahankan produktivitas. Semua artefak proyek telah dipersiapkan untuk diintegrasikan ke dalam _business dashboard_ mendatang, mendukung proses pengambilan keputusan yang berkelanjutan dan berbasis data.


### Rekomendasi Action Items (Optional)

Untuk mengatasi masalah _attrition rate_ dan mencapai target retensi karyawan, perusahaan dapat mengambil beberapa langkah strategis berikut:

1. **Optimasi Kebijakan Kompensasi dan Benefit**
Meninjau kembali struktur gaji dan tunjangan agar lebih kompetitif, serta memberikan insentif tambahan untuk meningkatkan kepuasan kerja.
2. **Peningkatan Kesejahteraan Karyawan**
Mengembangkan program kesejahteraan yang mencakup fleksibilitas kerja, dukungan kesehatan mental, dan kesempatan pertumbuhan karier.
3. **Analisis Mendalam terhadap Data _Attrition_**
Memanfaatkan model _machine learning_ secara berkelanjutan untuk mengidentifikasi pola perilaku karyawan yang berpotensi _resign_ dan melakukan intervensi tepat waktu.
4. **Peningkatan Budaya Perusahaan dan _Engagement__**
Menciptakan lingkungan kerja yang lebih positif dengan komunikasi terbuka, apresiasi terhadap kinerja, dan partisipasi aktif dalam pengambilan keputusan.
5. **Pengembangan Program Retensi Karyawan**
Membangun strategi khusus seperti _mentoring_, peluang karier yang jelas, dan _training_ berkala untuk meningkatkan loyalitas karyawan.
6. **Evaluasi Frekuensi Perjalanan dan _Work-Life Balance_**
Mengkaji dampak frekuensi perjalanan terhadap kepuasan kerja serta mempertimbangkan opsi kerja jarak jauh bagi posisi tertentu.

Langkah-langkah ini tidak hanya membantu mengurangi tingkat attrisi, tetapi juga meningkatkan produktivitas serta menciptakan lingkungan kerja yang lebih sehat dan berkelanjutan. 
