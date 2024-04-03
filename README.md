
# Effeciency-Energy-Analysis

## Latar belakang
Efisiensi energi merupakan topik yang terus dibahas di era modern. Meningkatnya konsumsi energi membuat sumber energi semakin berkurang. Dengan permasalahan itu, diperlukan solusi untuk mengatasi keterbatasan sumber energi. Salah satu cara untuk mengatasi hal tersebut adalah dengan menghemat energi dari skala terkecil. Efisiensi energi Efisiensi energi bukan hanya tentang penghematan energi, tetapi juga tentang penggunaan energi yang lebih cerdas dan bertanggung jawab. Hal ini dapat dicapai dengan berbagai cara, seperti mengubah perilaku, menggunakan teknologi yang lebih efisien, dan meningkatkan kesadaran.

## Problem Statements
* Menganalisis Faktor-Faktor yang Mempengaruhi Beban Pemanasan dan Pendinginan
* 

  

## Data Understanding
* Relative Compactness: This is the relative compactness of the building, which is defined as the ratio of the building's volume to the volume of an equivalent cuboid that encloses the building. This variable ranges from 0.62 to 0.98.
* Surface Area - m²: This is the total surface area of the building, including walls, roof, and windows. 
* Wall Area - m²: This is the total area of the building's walls. 
* Roof Area - m²: This is the total area of the building's roof.
* Overall Height - m: This is the height of the building. 
* Orientation = 2:North
                3:East
                4:South
                5:West
  This is the orientation of the building. The values 2, 3, 4, and 5 represent North, East, South, and West orientations, respectively.
* Glazing Area - 0%, 10%, 25%, 40% (of floor area): This is the total glazing area of the building, expressed as a percentage of the floor area. 
* Glazing Area Distribution (Variance) - 1:Uniform, 2:North, 3:East, 4:South, 5:West: This is the distribution of glazing area across the building. The values 1, 2, 3, 4, and 5 represent a uniform distribution and North, East, South, and West distributions, respectively.
* Heating Load - kWh/m²: This is the heating load of the building, expressed in kilowatt-hours per square meter. 
* Cooling Load - kWh/m²: This is the cooling load of the building, expressed in kilowatt-hours per square meter.

## Exploratory Data Analysis (EDA)
Untuk memahami data lebih lanjut, dilakukan Analisis Univariat, Analisis Bivariate dan Analisis Multivariat, serta Visualisasi Data melalui EDA. EDA/Exploratory Data Analysis adalah proses analisis data yang digunakan untuk menjelajahi, memahami, dan meringkas karakteristik dasar dari dataset secara visual dan deskriptif. Tujuan utama dari EDA adalah untuk memahami struktur dataset, menemukan pola atau tren yang menarik, serta mempersiapkan data untuk tahap analisis yang lebih lanjut.

Analisis Univariat

Analisis Univariat merupakan bentuk analisis data yang hanya merepresentasikan informasi yang terdapat pada satu variabel. Jenis visualisasi ini umumnya digunakan untuk memberikan gambaran terkait distribusi sebuah variabel dalam suatu dataset. Berikut adalah visualisasi EDA dari Analisis Univariate dari data NUMERIK

![image](https://github.com/thedoctorrr17/Effeciency-Energy-Analysis/assets/143855919/2226ed58-45eb-4034-9dd8-8b8f6ef94e77)
Gambar 1. Analisis Univariate

![image](https://github.com/daffahadyan/Effeciency-Energy-Analysis/assets/165827077/b619979f-7f9e-4058-a222-f15c0c569849)


Berdasarkan data diatas, didapatkan

* Luas permukaan bangunan paling luas dengan ukuran 808.5 meter persegi
* Luas dinding bangunan berkisar antara 214 hingga 416,5 meter persegi
* Tinggi atap paling tinggi adalah 7 meter
* Rasio volume bangunan berkisar antara 0,62 hingga 0,98

Multivariate Analysis
Analisis Multivariat merupakan jenis analisis data yang terdapat dalam lebih dari dua variabel. Jenis visualisasi ini digunakan untuk merepresentasikan hubungan dan pola yang terdapat dalam multidimensional data. Berikut adalah visualisasi EDA dari Analisis Multivariate

![image](https://github.com/daffahadyan/Effeciency-Energy-Analysis/assets/165827077/b65c4ca9-d530-4601-864e-8271ae1375b1)

Gambar 2. Analisis Multivariate

![image](https://github.com/daffahadyan/Effeciency-Energy-Analysis/assets/165827077/67a2f598-0c46-40b1-a516-0d64278dc796)

Gambar 3. Correlation Map


# Data Preparation
Pada proses Data Preparation dilakukan kegiatan seperti Data Gathering, Data Assessing, dan Data Cleaning. Pada proses Data Gathering, data diimpor sedemikian rupa agar bisa dibaca dengan baik menggunakan dataframe Pandas. Untuk proses Data Assessing, berikut adalah beberapa pengecekan yang dilakukan:

Duplicate data (data yang serupa dengan data lainnya)
Missing value (data atau informasi yang "hilang" atau tidak tersedia)
Outlier (data yang menyimpang dari rata-rata sekumpulan data yang ada)
Pada proses Data Cleaning, secara garis besar, terdapat tiga metode yang dapat digunakan antara lain seperti berikut:

Dropping (metode yang dilakukan dengan cara menghapus sejumlah baris data)
Imputation (metode yang dilakukan dengan cara mengganti nilai yang "hilang" atau tidak tersedia dengan nilai tertentu yang bisa berupa median atau mean dari data)
Interpolation (metode menghasilkan titik-titik data baru dalam suatu jangkauan dari suatu data) Pada kasus proyek ini, tidak ditemukan Duplicate Data dan Missing Value.

## Outlier
![image](https://github.com/daffahadyan/Effeciency-Energy-Analysis/assets/165827077/31496389-0608-41fb-b364-041729a3b8a5)

Gambar 4. Box Plot
Berdasarkan box plot diatas, tidak ditemukanya outlier pada dataset. Hal ini menandakan bahwa dataset memiliki persebaran data yang bagus.

## Reduction With PCA
Reduksi dimensi dengan PCA (Principal Component Analysis) adalah teknik yang digunakan untuk mengurangi jumlah fitur (variabel) dalam dataset, tetapi tetap mempertahankan sebanyak mungkin informasi yang mungkin. Berdasarkan analisis multivariat yang dilakukan, diketahui bahwa terdapat korelasi antara heating load dan cooling load Sehingga, dilakukan reduksi PCA pada fitur-fitur tersebut.
![image](https://github.com/daffahadyan/Effeciency-Energy-Analysis/assets/165827077/9561badf-2ded-4b69-a04c-6bd14eebd389)

Gambar 5. Visualisasi Hubungan antara Heating load dengan Cooling Load

## Modeling
Model yang digunakan untuk memprediksi kegagalan mesin adalah model regresi. Dalam bentuk yang sederhana, regresi terdiri dari intersep dan slope yang dituliskan dalam rumusan berikut:

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <mi>y</mi>
  <mo>=</mo>
  <mi>a</mi>
  <mo>+</mo>
  <mi>b</mi>
  <mi>X</mi>
</math>

dimana:

y adalah variabel kriterium (variabel terikat yang digunakan untuk memprediksi)
a adalah intersep (variabel konstan yang memiliki arti sebagai titik perpotongan suatu garis dengan sumbu Y),
b adalah slope (nilai koefisien yang menyatakan ukuran kemiringan suatu garis), dan
X adalah variabel prediktor (variabel yang digunakan untuk memprediksi atau menjelaskan variabel lain dalam suatu model)
Secara khusus, metode regresi sering digunakan untuk memprediksi atau meramalkan pengaruh variabel prediktor terhadap variabel kriterium atau membuktikan ada atau tidaknya hubungan fungsional antara variabel bebas (X) dengan variabel terikat (y). Berikut adalah kelebihan dan kekurangan dari model regresi: Kelebihan regresi:

Kemudahan untuk digunakan
Kekuatan Prediktor dalam mengidentifikasi sekuat apa pengaruh yang diberikan oleh variabel prediktor (variabel independen) terhadap variabel lainnya (variabel dependen).
Dapat memprediksi nilai/tren di masa yang mendatang
Kelemahan dari model regresi adalah karena hasil ramalan dari analisis regresi merupakan nilai estimasi sehingga kemungkinan untuk tidak sesuai dengan data aktual tetaplah ada. 


## Evaluation
Adapun metrik yang sebagai alat ukur perfoma model yang dibuat antara lain **MSE · MAE · R<sup>2</sup>**. 

Berikut merupakan rumus dari masing-masing metrik yang digunakan:

$$ MAE = (1/n) Σ |y<sub>i</sub> - ŷ<sub>i</sub>| $$

$$ MSE = (1/n) Σ (y<sub>i</sub> - ŷ<sub>i</sub>)<sup>2</sup> $$

$$ R<sup>2</sup> = 1 - (MSE / Var(y)) $$

y<sub>i</sub> mewakili nilai yang diamati,
ŷ<sub>i</sub> mewakili nilai prediksi,
n adalah jumlah titik data,
Var(y) mewakili varians dari nilai yang diamati.

Berikut merupakan penjelasan kegunaan dari masing-masing metrik yang digunakan:
- MAE menghitung rata-rata dari selisih absolut antara nilai prediksi dan nilai aktual. Semakin kecil nilai MAE, semakin baik kualitas model tersebut.
- MSE menghitung rata-rata dari selisih kuadrat antara nilai prediksi dan nilai aktual. Semakin kecil nilai MSE, semakin baik kualitas model tersebut.
- R<sup>2</sup> digunakan untuk menilai seberapa besar pengaruh variabel independen tertentu terhadap variabel dependen



![image](https://github.com/daffahadyan/Effeciency-Energy-Analysis/assets/165827077/a3010016-ea62-4b01-985b-f4cce54b7772)









