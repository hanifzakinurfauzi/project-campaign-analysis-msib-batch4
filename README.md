# Project Campaign Analysis
Repository ini merupakan salah satu proses dari program Studi Independen Kampus Merdeka bermitra dengan Narasiodata dan disusun oleh:

Hanif Zaki Nur Fauzi

Data source: Internal Company

## Introduction
PT ABC (nama samaran) adalah sebuah perusahaan asal Indonesia yang bergerak di bidang retail. Perusahaan saat ini berencana untuk meningkatkan performa penjualan dengan menentukan metode pemasaran yang diberikan kepada pelanggan dengan berbagai kebutuhan, karakteristik atau perilaku yang berbeda. Perusahaan memiliki dataset dari setiap transaksi di retail ini. kita sebagai Data science di perusahaan ABC memiliki peran untuk memberikan insight serta rekomendasi dari dataset tersebut, sehingga perusahaan dapat terus berkembang. Perusahaan ABC akan melakukan campaign terhadap produk yang mereka sediakan, sehingga perusahaan ingin menganalisis segmen pelanggan mana yang paling mungkin membeli produk dan kemudian memasarkan produk hanya pada segmen tertentu. Oleh karena itu langkah-langkah yang perlu kami lakukan pertama adalah business understanding, data cleaning dan preparation, data overview, EDA dan insight, model dan evaluasi, business insight dan rekomendasi.

## Business Understanding
Pada Langkah business understanding kami ingin memahami permasalahan business yang dimiliki oleh perusahaan dan menentukan tujuan dari hasil analysis ini. Untuk memahami permasalahan bisnis nya, kami melakukan cohort analysis yaitu metode yang digunakan untuk menganalisis serta mengevaluasi perubahan perilaku sekelompok orang tertentu, yang melibatkan fitur demografis umum dalam kurun waktu tertentu. Dari hasil cohort analysisnya bisa kita lihat bahwa sekelompok customer pada 10 bulan terakhir penjualan di perusahaan ABC mengalami penurunan jumlah pembelian barang rata-rata hingga 8%. Dari 63.331 jumlah barang yang dibeli oleh customer pada bulan Oktober 2013 terus menurun hingga 33.153 pada bulan Juni 2014. 

![Cohort Analysis](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/974857f6-d738-46cb-b2f2-23a38b1b647b)

## Goals and Strategy
Setelah mengetahui permasalahan business nya, kita bisa menargetkan tujuan kita yaitu:
1. Meningkatkan repurchasing dengan melakukan Customer profiling untuk merencanakan strategi campaign.
2. Melakukan customer segmentasi menggunakan K-means clustering dan membuat model clustering untuk memprediksi cluster yang di targetkan.
3. Memberikan insight dan rekomendasi yang dapat membantu tim bisnis dan tim pemasaran untuk meningkatkan repurchasing.

## Data Overview
Data Marketing di PT ABC yang kami analysis ini berasal dari Kaggle, data ini terdiri dari 1 data set utama. Setelah kita lakukan proses understanding dengan data set terdapat 14 kolom dan 2.240 baris.

![data overview 1](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/5990d670-ebdf-4530-9262-f8375b9903f1)
![data overview 2](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/5352a18d-d925-4b60-92b6-d98fb656dbf1)

## Data Pre-Processing dan Cleaning
Sekarang kita masuk kedalam process data cleaning dan data preprocessing, pada tahap ini kami akan membersihkan data, memilih kolom yang digunakan dan mempersiapkan data untuk keperluan clustering. Berikut merupakan process cleaning dan preprocessing yang dilakukan:
1. Handling missing values pada kolom pendapatan -> Isi dengan menggunakan nilai mean dari data, alasanya karena kami membutuhkan data tersebut untuk analysis sehingga kami handling dengan nilai mean dari kolom tersebut. Selain itu pada kolom pendapatan tidak ditemui nilai outlier sehingga kami handling dengan nilai mean.
2. Check & remove Duplicate -> Tidak terdapat nilai duplikat pada dataset 
3. Handling outliers -> Tidak ditemui nilai outlier pada dataset
4. Penyesuain Data pada kolom pendidikan dan status pernikahan -> Handling dengan menggunakan kata yang sesuai


## Exploratory Data Analysis
Setelah melewati proses cleaning data kami siap digunakan,di tahap EDA dan Insight ini kami akan menjabarkan hasil dari analyisis yang sudah kami lakukan.

![Heatmap](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/c24a94f9-61fb-4035-9809-aa51b2193169)

Kolom Pendapatan dan Income Group memiliki korelasi postif yang kuat dengan kolom Spent Wine, Spent Daging, Spent Ikan, Spent Buah, dan Spent Emas. Namun kolom Jumlah Tanggungan memiliki korelasi negatif dengan kolom Spent Wine, Spent Daging, Spent Ikan, Spent Buah, dan Spent Emas. Sehingga target campaign PT ABC merupakan customer dengan pendapatan yang menengah keatas atau customer dengan high income. Selain itu customer dengan jumlah tanggungan yang sedikit memiliki korelasi kuat dengan banyaknya total spending.

![Segmentation](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/13b8d726-2a93-4875-ba0e-a80d6bebb53f)

Jumlah customer pada kelompok segemnt 0 adalah 1397 <br>
Jumlah customer pada kelompok segemnt 1 adalah 843

![Generasi Based on Segment](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/bc68f613-df17-4060-8b11-bf78bb46a637)
![Jumlah Tanggungan Based on Segment](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/f0a9fc13-74ec-4603-8a38-047ab4c0a9b5)
![Income Group Based on Segment](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/5810b4b3-e303-4e4c-b0d3-58e5a253e398)
![Income Based on Segment](https://github.com/hanifzakinurfauzi/project-campaign-analysis-msib-batch4/assets/110440805/8e8af333-23b8-424e-b1f5-893fe076dcd1)

## Conclusion
1. Target campaign memiliki jumlah customer yang lebih sedikit yaitu 843 customer
2. Target campaign merupakan customer yang memiliki pendapatan lebih tinggi dari pada customer yang tidak ditarget dengan rata-rata sebesar 72,228
3. Target campaign meruapakan generasi millennials dan Gen X
4. Target campaign merupakan customer dengan jumlah tanggungan yang lebih sedikit
5. 63% target campaign merupakan customer yang telah menikah
6. Karateristik dari tiap-tiap produk memiliki kesamaan profile customer
   
## Results and Recommendation
1. Target campaign merupakan customer yang memiliki pendapatan tinggi sehingga tidak mengapa apabila campaign dilakukan dengan sistem promosi yang tinggi pula
2. Target campaign merupakan customer dari generasi millennials dan Gen X, sehingga perlu mempertimbangkan sistem promosi menggunakan social media branding
3. Target customer memiliki karakteristik yang sama pada tiap-tiap product market, sehingga campaign tidak harus dibatasi satu product saja, namun campaign bisa dilakukan bebrapa product sekaligus.
