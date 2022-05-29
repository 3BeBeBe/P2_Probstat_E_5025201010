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
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/1_a_1.png)

  Setelah itu barulah dicetak hasil devisiasi standar untuk data sebelum.
  ```R
  devisiasiStandar_sebelum <- sd(sebelum)
  devisiasiStandar_sebelum
  ```
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/1_a_2.png)


  Setelah itu barulah dicetak hasil devisiasi standar untuk data sesudah.
  ```R
  devisiasiStandar_sesudah <- sd(sesudah)
  devisiasiStandar_sesudah
  ```
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/1_a_3.png)

- Carilah nilai t (p-value).
  ```R
  t.test(sebelum, sesudah, alternative = "greater", var.equal = FALSE)
  ```
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/1_b.png)
  
- Tentukanlah apakah terdapat pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴 jika diketahui tingkat signifikansi 𝛼 = 5% serta H0 : “tidak ada pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen, sebelum dan sesudah melakukan aktivitas 𝐴”

  Melihat hasil komparasi
  ```R
  var.test(sebelum, setelah)
  ```
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/1_c_1.png)
  
  ```R
  t.test(sebelum, after, mu = 0, alternative = "two.sided", var.equal = TRUE)
  ```
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/1_c_2.png)
  Dapat dilihat bahwa mean dan convidence sama dengan 1b dan p-value juga df berbeda. Sehingga tidak memiliki pengaruh yang signifikan.

## Soal 2
Diketahui bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun. Untuk menguji klaim ini, 100 pemilik mobil yang dipilih secara acak diminta untuk mencatat jarak yang mereka tempuh. Jika sampel acak menunjukkan rata-rata 23.500 kilometer dan standar deviasi 3900 kilometer. (Kerjakan menggunakan library seperti referensi pada modul).
- Apakah Anda setuju dengan klaim tersebut?
  
  `Iya, saya setuju.`

- Jelaskan maksud dari output yang dihasilkan!
  ```R
  tsum.test(mean.x=23500, sd(3900), n.x=100)
  ```
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/2_b.png)

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
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/2_c_1.png)  
  Perhitungan diatas dilakukan untuk mencari nilai z.

  Barulah mencari nilai p-value.
  ![alt text](https://github.com/3BeBeBe/P2_Probstat_E_5025201010/blob/main/Assets/2_c_1.png)  
 
  
