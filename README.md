# MiniProject4 - Predict Clicked Ads Customer Classification by using Machine Learning
Rheza Paleva Uyanto - Rakamin Academy Data Science Batch 24

## Pendahuluan :
“Sebuah perusahaan di Indonesia ingin mengetahui efektifitas sebuah iklan yang mereka tayangkan, hal ini penting bagi perusahaan agar dapat mengetahui seberapa besar ketercapainnya iklan yang dipasarkan sehingga dapat menarik customers untuk melihat iklan. Dengan mengolah data historical advertisement serta menemukan insight serta pola yang terjadi, maka dapat membantu perusahaan dalam menentukan target marketing, fokus case ini adalah membuat model machine learning classification yang berfungsi menentukan target customers yang tepat ”

## Pertanyaan Riset :
'Bagaimana karakteristik customer yang tepat yang cocok dengan target marketing perusahaan ?'

## Tujuan :
Untuk mengetahui karakteristik customer yang tepat.

## Exploratory Data Analysis :
- Dataset : Clicked Ads Dataset
- Terdiri dari 1000 baris data dan 11 kolom data
- Terdiri dari 5 data numerical, dan 6 data kategorikal
- Ada beberapa data yang memiliki null value

### Analisis Univariate :
<img width="700" alt="image" src="https://user-images.githubusercontent.com/114345988/207798060-afd6c839-40bf-4295-b866-8e968f0a4ee2.png">

### Analisis Bivariate :
<img width="679" alt="image" src="https://user-images.githubusercontent.com/114345988/207798181-713026bb-a9da-4f10-b6aa-0680b83d569a.png">
<img width="528" alt="image" src="https://user-images.githubusercontent.com/114345988/207798232-16d56675-5b70-444d-8bbd-11b211622309.png">

### Analisis Multivariate  
<img width="450" alt="image" src="https://user-images.githubusercontent.com/114345988/207798344-33ab76f4-6c31-465c-823d-bf77a57a71e6.png">

## Data Preprocessing:

### Handle Null Value :
- Daily Time Spent on Site – diisi dengan nilai median
- Area Income – diisi dengan nilai median
- Daily Internet Usage – diisi dengan nilai median
- Male – diisi dengan modus (karena data kategorik, paling banyak adalah Laki-laki)

### Nilai Duplikat :
- Tidak ada nilai duplikat

### Ekstrak Waktu :
- dengan menggunakan library Date Time, dan mengekstrak menjadi tahun, bulan, minggu, dan hari

### Feature Encoding:
- One Hot Encoding untuk fitur: Male, City, Province, dan Category
- Fitur Transformation : Clicked on Ad diubah menjadi 0 untuk No, 1 untuk Yes
- Setelah dilakukan Label Encoding, dilakukan Dropping Fitur : Unnamed: 0, Male, Timestamp, City, Province, Clicked on Ad, Category, date

### Split Data Training dan Data Testing
- Data X dan y displit, X merupakan fitur selain Clicked on Ad, sedangkan y hanya fitur Clicked on Ad
- Data X dan y dipslit dengan perbandingan 70% Data Training dan 30% data Testing

## Data Modelling
- Menggunakan 7 model: Decision Tree, Logistic Regression, XGBoost, AdaBoost Classifier, Random Forest, Gradient Boosting Classifier, dan K-Nearest Neighboors Classifier
- Mencari nilai accuracy, presisi, dan recall
- Mencari fitur importance

### Hasil :
- Nilai Precision paling tinggi ditunjukkan oleh Pemodelan Gradient Boosting Classifier
- Nilai precision : 0,97
- Feature Importance tertinggi: Daily Internet Usage, Daily Time Spent on Site dan Area Income

<img width="350" alt="image" src="https://user-images.githubusercontent.com/114345988/207802846-2bab9ae9-eec7-4e25-99fa-e82e74a309fe.png">

## Rekomendasi :
- Setiap hari, orang akan menghabiskan minimal 30 menit untuk berselancar dalam sebuah website dan menggunakan internet minimal selama 100 menit.
- Iklan yang ditayangkan haruslah berhubungan dengan minat user.
- Iklan harus menarik perhatian, ditayangkan 15-30 menit pertama saat user datang dalam website tersebut.
- Kota dan Provinsi tidak menjadi fitur prioritas, sehingga iklan dapat ditayangkan tanpa melihat area.
- Hari penayangan juga tidak menjadi fitur prioritas, sehingga iklan dapat ditayangkan di seluruh hari. 
<img width="450" alt="image" src="https://user-images.githubusercontent.com/114345988/207803165-7c128b0a-b080-46cc-9df7-5b97d832034d.png">

## Simulasi Bisnis :
### Simulasi Bisnis sebelum menggunakan Machine Learning
- Jika Biaya Per klik, sumber literatur disini , adalah Rp 3.000,-, dengan target peserta adalah 300 orang.
- Cost : 300 orang x Rp. 3.000,- = Rp. 900.000,-
- Revenue, Peserta yang mengklik Iklan sebanyak 150 orang, dan melakukan transaksi sebanyak minimal Rp 100.000,- maka
- Revenue : 150 orang x Rp 100.000,- = Rp. 150.000,-
- Profit, dengan memperhitungkan Cost dan Revenue yang didapatkan
- Profit = Revenue – Cost 
- Profit = Rp 150.000,- - Rp 900.000 = (- Rp 450.000,-) Rugi sebanyak 450.000,-

### Simulasi Bisnis sesudah menggunakan Machine Learning
- Jika Biaya Per klik, sumber literatur disini , adalah Rp 3.000,-, dengan target peserta difokuskan pada peserta yang berselancar di website minimal 15 menit. Dengan Machine Learning, sebanyak 150 orang diberikan Iklan
- Cost : 150 orang x Rp. 3.000,- = Rp. 450.000,-
- Revenue, Dari Machine Learning, Peserta yang mengklik Iklan sebanyak 141 orang dari 150 orang, dan jika 141 orang tersebut melakukan transaksi sebanyak minimal Rp 100.000,- maka
- Revenue : 141 orang x Rp 100.000,- = Rp. 14.100.000,-
- Profit, dengan memperhitungkan Cost dan Revenue yang didapatkan
- Profit = Revenue – Cost 
- Profit = Rp 14.100.000,- - Rp 450.000,- = Rp 13.650.000,- 

<img width="350" alt="image" src="https://user-images.githubusercontent.com/114345988/207805877-a9c56971-8b0f-4dc5-984a-13289908f9f1.png">

## Kesimpulan :
- Penentuan model machine learning dalam pemodelan saat diperlukan
- Feature Importance juga mempengaruhi dalam pengambilan keputusan dalam bisnis, terutama dalam fokus dalam faktor tertentu yang mempengaruhi dalam proses bisnis.
- Dalam proses diatas, dengan menggunakan model machine learning dapat meningkatkan profit sampai lebih dari 100 % dengan memilih user yang berselancar di website minimal 15 menit. 

