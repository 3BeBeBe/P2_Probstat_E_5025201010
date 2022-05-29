# Praktikum PROBSTAT Modul 2 Kelas E 2022

    Nama : I Putu Bagus Adhi Pradana
    NRP  : 5025201010
    Kelas: PROBSTAT E

## Soal 1

Seorang peneliti melakukan penelitian mengenai pengaruh aktivitas 𝐴 terhadap kadar saturasi oksigen pada manusia. Peneliti tersebut mengambil sampel sebanyak 9 responden. Pertama, sebelum melakukan aktivitas 𝐴, peneliti mencatat kadar saturasi oksigen dari 9 responden tersebut. Kemudian, 9 responden tersebut diminta melakukan aktivitas 𝐴. Setelah 15 menit, peneliti tersebut mencatat kembali kadar saturasi oksigen dari 9 responden tersebut. Berikut data dari 9 responden mengenai kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas 𝐴.


Berdasarkan data pada tabel diatas, diketahui kadar saturasi oksigen dari responden ke-3 ketika belum melakukan aktivitas 𝐴 sebanyak 67, dan setelah melakukan aktivitas 𝐴 sebanyak 70.
  
- Carilah Standar Deviasi dari data selisih pasangan pengamatan tabel
diatas.

  Memasukan tiap data yang ada.
  
    - Data Sebelum melakukan aktivitas
      ```R 
      sebelum <- c(78, 75, 67, 77, 70, 72, 28, 74, 77)
      ```
    - Data Setelah melakukan aktivitas
      ```R  
      sesudah <- c(100, 95, 70, 90, 90, 90, 89, 90, 100)
      ```
  Lalu data yang dimasukan dicek dengan `data.frame`.
  ```R
  data_oxigenSaturation <- data.frame(
      group = rep(c("sebelum", "sesudah"), each = 9),
      saturation = c(sebelum, sesudah)
  )
  ```
  Barulah dilahkukan pencetakan untuk melihat isi frame.
  ```R
  print(data_oxigenSaturation)
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/1_a_1.png)

  Setelah itu barulah dicetak hasil devisiasi standar untuk data sebelum.
  ```R
  devisiasiStandar_sebelum <- sd(sebelum)
  devisiasiStandar_sebelum
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/1_a_2.png)


  Setelah itu barulah dicetak hasil devisiasi standar untuk data sesudah.
  ```R
  devisiasiStandar_sesudah <- sd(sesudah)
  devisiasiStandar_sesudah
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/1_a_3.png)

- Carilah nilai t (p-value).
  ```R
  t.test(sebelum, sesudah, alternative = "greater", var.equal = FALSE)
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/1_b.png)
  
- Tentukanlah apakah terdapat pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴 jika diketahui tingkat signifikansi 𝛼 = 5% serta H0 : “tidak ada pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen, sebelum dan sesudah melakukan aktivitas 𝐴”

  Melihat hasil komparasi
  ```R
  var.test(sebelum, setelah)
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/1_c_1.png)
  
  ```R
  t.test(sebelum, after, mu = 0, alternative = "two.sided", var.equal = TRUE)
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/1_c_2.png)
  Dapat dilihat bahwa mean dan convidence sama dengan 1b dan p-value juga df berbeda. Sehingga tidak memiliki pengaruh yang signifikan.

## Soal 2
Diketahui bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun. Untuk menguji klaim ini, 100 pemilik mobil yang dipilih secara acak diminta untuk mencatat jarak yang mereka tempuh. Jika sampel acak menunjukkan rata-rata 23.500 kilometer dan standar deviasi 3900 kilometer. (Kerjakan menggunakan library seperti referensi pada modul).
- Apakah Anda setuju dengan klaim tersebut?
  
  `Iya, saya setuju.`

- Jelaskan maksud dari output yang dihasilkan!
  ```R
  tsum.test(mean.x=23500, sd(3900), n.x=100)
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/2_b.png)

  Diketahui 
  - n = 100
  - Rata-Rata (X̄) = 23500
  - standar deviasi(σ) = 3900

  Maka hipotesis yang dihasilkan adalah
  ```
  H0 : μ = 20000
  ```
  Dengan alternatif
  ```
  H1 : μ > 20000
  ```
- Buatlah kesimpulan berdasarkan P-Value yang dihasilkan
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/2_c_1.png)  
  Perhitungan diatas dilakukan untuk mencari nilai z.

  Barulah mencari nilai p-value.
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/2_c_1.png)  
 
### Soal 3
Diketahui perusahaan memiliki seorang data analyst ingin memecahkan permasalahan pengambilan keputusan dalam perusahaan tersebut. Selanjutnya didapatkanlah data berikut dari perusahaan saham tersebut.  

Dari data diatas berilah keputusan serta kesimpulan yang didapatkan dari hasil diatas. Asumsikan nilai variancenya sama, apakah ada perbedaan pada rata-ratanya (α= 0.05)? Buatlah :
- H0 dan H1
  - H0
    ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/3_a_1.png)
  - H1
    ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/3_a_2.png)

- Hitung Sampel Statistik
  ```R
  tsum.test(mean.x=3.64, s.x = 1.67, n.x = 19, 
          mean.y =2.79 , s.y = 1.32, n.y = 27, 
          alternative = "greater", var.equal = TRUE)
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/3_b.png)

- Lakukan Uji Statistik (df =2)
  ```R
  install.packages("mosaic")
  library(mosaic)
  ```
  ```R
  plotDist(dist='t', df=2, col="blue")
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/3_c.png)

- Nilai Kritikal

  Nilai Kritikal bisa menggunakan `qchisq` dengan `df=2` sesuai soal sebelumnya.

  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/3_d.png)

- Keputusan

  Teori keputusan adalah teori formal pengambilan keputusan di bawah ketidak pastian dengan  
  - Aksinya : `({a}_{a∈A})` 
  - Kemungkinan konsekuensi : `({c}_{c∈C})` (tergantung keadaan dan tindakan) 
  Maka keputusan dapat dibuat dengan `t.test`

- Kesimpulan
  Nilai rata rata tidak akan nampak bila dilihat dari uji statatik dan akan tampak bila dipengaruhi nilai kritikal, tetapi itupun tidak secara signifikan.

## Soal 4
Seorang Peneliti sedang meneliti spesies dari kucing di ITS. Dalam penelitiannya ia mengumpulkan data tiga spesies kucing yaitu kucing oren, kucing hitam dan kucing putih dengan panjangnya masing-masing.
Jika : 

diketahui dataset https://intip.in/datasetprobstat1
H0 : Tidak ada perbedaan panjang antara ketiga spesies atau rata-rata panjangnya sama

Maka Kerjakan atau Carilah:
- Buatlah masing masing jenis spesies menjadi 3 subjek "Grup" (grup 1,grup 2,grup 3). Lalu Gambarkan plot kuantil normal untuk setiap kelompok dan lihat apakah ada outlier utama dalam homogenitas varians.

  Mengambil data dari link.
  ```R
  myFile  <- read.table(url("https://rstatisticsandresearch.weebly.com/uploads/1/0/2/6/1026585/onewayanova.txt"))
  dim(myFile)
  head(myFile)
  attach(myFile)
  ```
  
  Membuat grup dari myFile.
  ```R
  myFile$V1 <- as.factor(myFile$V1)
  myFile$V1 = factor(myFile$V1,labels = c("Kucing Oren","Kucing Hitam","Kucing Putih","Kucing Oren"))
  ```

  Pengecekan apakah dia mengandung nilai di grupnya.
  ```R
  class(myFile$V1)
  ```

  Bagi value ke 3 bagian pada 3 grup
  ```R
  group1 <- subset(myFile, Group=="Kucing Oren")
  group2 <- subset(myFile, Group=="Kucing Hitam")
  group3 <- subset(myFile, Group=="Kucing Putih")
  ```
- carilah atau periksalah Homogeneity of variances nya , Berapa nilai p yang didapatkan? , Apa hipotesis dan kesimpulan yang dapat diambil ?

  ```R
  bartlett.test(Length~Group, data=dataoneway)
  ```
  Sehingga nilai p-value = 0.8054. Kesimpulan yang didapatkan yaitu Bartlett's K-squared memiliki nilai sebesar 0.43292 dan df bernilai 2.

- Untuk uji ANOVA (satu arah), buatlah model linier dengan Panjang versus Grup dan beri nama model tersebut model 1.
  ```R
  qqnorm(group1$Length)
  qqline(group1$Length)
  ```
  ![alt text](https://github.com/3BeBeBe/P1_Probstat_E_5025201010/blob/main/Assets/4_c.png)

- Dari Hasil Poin C, Berapakah nilai-p ?, Apa yang dapat Anda simpulkan dari H0?
  `p-value = 0.8054.`
- Verifikasilah jawaban model 1 dengan Post-hoc test Tukey HSD, dari nilai p
yang didapatkan apakah satu jenis kucing lebih panjang dari yang lain? Jelaskan.

  menggunakan command ANOVA
  ```
  model1 <- lm(Length~Group, data=myFile)
  ```
  Selanjutnya menggunakan command
  ```
  anova(model1)
  ```
  Lalu menggunakan model Post-hoc Tukey HSD sebagai berikut
  ```
  TukeyHSD(aov(model1))
  ```

- Visualisasikan data dengan ggplot2
  ```
  library(ggplot2)
  ggplot(dataoneway, aes(x = Group, y = Length)) + geom_boxplot(fill = "grey80", colour = "black") + scale_x_discrete() + xlab("Treatment Group") +  ylab("Length (cm)")
  ```

## Soal 5
Data yang digunakan merupakan hasil eksperimen yang dilakukan untuk mengetahui pengaruh suhu operasi (100 ̊C, 125 ̊C dan 150 ̊C) dan tiga jenis kaca pelat muka (A, B dan C) pada keluaran cahaya tabung osiloskop. Percobaan dilakukan sebanyak 27 kali dan didapat data sebagai berikut: Data Hasil Eksperimen. Dengan data tersebut:
- Buatlah plot sederhana untuk visualisasi data
- Lakukan uji ANOVA dua arah
- Tampilkan tabel dengan mean dan standar deviasi keluaran cahaya untuk
setiap perlakuan (kombinasi kaca pelat muka dan suhu operasi)
- Lakukan uji Tukey
- Gunakan compact letter display untuk menunjukkan perbedaan signifikan
antara uji Anova dan uji Tukey
