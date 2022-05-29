# P2_Probstat_A_5025201089
Praktikum Probstat Modul 2 
Andi Muhammad Rafli - 5025201089

### Soal 1
> Seorang peneliti melakukan penelitian mengenai pengaruh aktivitas 𝐴 terhadap kadar saturasi oksigen pada manusia. Peneliti tersebut mengambil sampel sebanyak 9 responden. Pertama, sebelum melakukan aktivitas 𝐴, peneliti mencatat kadar saturasi oksigen dari 9 responden tersebut. Kemudian, 9 responden tersebut diminta melakukan aktivitas 𝐴. Setelah 15 menit, peneliti tersebut mencatat kembali kadar saturasi oksigen dari 9 responden tersebut. Berikut data dari 9 responden mengenai kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas 𝐴

<img width="211" alt="Screen Shot 2022-05-29 at 6 52 57 PM" src="https://user-images.githubusercontent.com/102727966/170866622-330cd4a2-8061-4f03-9a34-32c47c13af16.png">

Berdasarkan data pada tabel diatas, diketahui kadar saturasi oksigen dari responden ke-3 ketika belum melakukan aktivitas 𝐴 sebanyak 67, dan setelah melakukan aktivitas 𝐴 sebanyak 70.

a. Carilah Standar Deviasi dari data selisih pasangan pengamatan tabel diatas
> Menggunakan fungsi `dgeom` untuk mendapatkan nilai peluang soal. Setelah dijalankan, akan didapatkan nilai peluang yaitu sebagai berikut 
```
dgeom(x=3, prob=0.20)
```
Output :
```
[1] 0.1024
```

b. carilah nilai t (p-value)
> mean Distribusi Geometrik dengan 10000 data random , prob = 0,20 dimana distribusi geometrik acak tersebut X = 3
> `rgeom` digunakan karena diminta data rando
```
mean(rgeom(n=10000, prob=0.20) == 3)
```

Output :
```
[1] 0.1004
```
c. tentukanlah apakah terdapat pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴 jika diketahui tingkat signifikansi 𝛼 = 5% serta H0 : “tidak ada pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴”
```

```
Output :
```

```
### Soal 2
> Diketahui bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun. Untuk menguji klaim ini, 100 pemilik mobil yang dipilih secara acak diminta untuk mencatat jarak yang mereka tempuh. Jika sampel acak menunjukkan rata-rata 23.500 kilometer dan standar deviasi 3900 kilometer. (Kerjakan menggunakan library seperti referensi pada modul).

a. Apakah Anda setuju dengan klaim tersebut?
```
dbinom(4, 20, 0.2)
```
Output :
```

```

b. Jelaskan maksud dari output yang dihasilkan!
```
data.frame(x = 0:10, prob = dbinom(x = 0:10,20,0.2)) %>%
  mutate(X = ifelse(x == 4, 4, "other")) %>%
  ggplot(aes(x = factor(x), y = prob, fill = X)) +
  geom_col() +
  geom_text(
    aes(label = round(prob,2), y = prob + 0.01),
    position = position_dodge(0.9),
    size = 3,
    vjust = 0
  ) +
  labs(title = "Peluang jika X = 4 pasien sembuh.", x = "Sembuh (x)", y = "Peluang")
  ```
 


c.  Buatlah kesimpulan berdasarkan P-Value yang dihasilkan!
> Nilai rataan dapat dicari dengan `μ = n*p` sedangkan varian `σ² = npq` 
```
p = 0.2
n = 4
rataan = n*p
rataan
varian = n*p*(1-p)
varian
```

Output :
```
[1] 0.8
[1] 0.64
```

### Soal 3
> Diketahui perusahaan memiliki seorang data analyst ingin memecahkan permasalahan pengambilan keputusan dalam perusahaan tersebut. Selanjutnya didapatkanlah data berikut dari perusahaan saham tersebut.

<img width="430" alt="Screen Shot 2022-05-29 at 6 52 11 PM" src="https://user-images.githubusercontent.com/102727966/170866593-4a150df2-c1ff-41dc-b484-65ee0da05701.png">

Dari data diatas berilah keputusan serta kesimpulan yang didapatkan dari hasil diatas. Asumsikan nilai variancenya sama, apakah ada perbedaan pada rata-ratanya (α= 0.05)? Buatlah :

a. H0 dan H1
```

```
Output :
```

```

b. Hitung Sampel Statistik
setahun (n = 365)
```

```
Output:
```

```
c. Lakukan Uji Statistik (df =2)
```

```
Output :
```

```
d. Nilai Kritikal
```

```
Output :
```

```

e. Keputusan
```

```
Output :
```

```

f. Kesimpulan
```

```
Output :
```

```
### Soal 4
> Seorang Peneliti sedang meneliti spesies dari kucing di ITS . Dalam penelitiannya ia mengumpulkan data tiga spesies kucing yaitu kucing oren, kucing hitam dan kucing putih dengan panjangnya masing-masing.
Jika :
diketahui dataset https://intip.in/datasetprobstat1
H0 : Tidak ada perbedaan panjang antara ketiga spesies atau rata-rata panjangnya sama
Maka Kerjakan atau Carilah:

a. Buatlah masing masing jenis spesies menjadi 3 subjek "Grup" (grup 1,grup
2,grup 3). Lalu Gambarkan plot kuantil normal untuk setiap kelompok dan
lihat apakah ada outlier utama dalam homogenitas varians.
> 
Source code dan output :
```

```
Output : 
```

```
b. Carilah atau periksalah Homogeneity of variances nya , Berapa nilai p yang
didapatkan? , Apa hipotesis dan kesimpulan yang dapat diambil ?
> 
Source code dan output :
```

```
Output : 
```

```
 
c. Untuk uji ANOVA (satu arah), buatlah model linier dengan Panjang versus
Grup dan beri nama model tersebut model 1.
> 
Source code dan output :
```

```
Output : 
```

```
 
d. Dari Hasil Poin C, Berapakah nilai-p ? , Apa yang dapat Anda simpulkan
dari H0?
> 
Source code dan output :
```

```
Output : 
```

```
 
e. Verifikasilah jawaban model 1 dengan Post-hoc test Tukey HSD, dari nilai p
yang didapatkan apakah satu jenis kucing lebih panjang dari yang lain?
> 
Source code dan output :
```

```
Output : 
```

```

### Soal 5
> Data yang digunakan merupakan hasil eksperimen yang dilakukan untuk mengetahui pengaruh suhu operasi (100 ̊C, 125 ̊C dan 150 ̊C) dan tiga jenis kaca pelat muka (A, B dan C) pada keluaran cahaya tabung osiloskop. Percobaan dilakukan sebanyak 27 kali dan didapat data sebagai berikut: Data Hasil Eksperimen. Dengan data tersebut:

a. Buatlah plot sederhana untuk visualisasi data
>  
```

```
Output :
```

```

b. Lakukan uji ANOVA dua arah
```

```
Output :
```

```

c. Tampilkan tabel dengan mean dan standar deviasi keluaran cahaya untuk setiap perlakuan (kombinasi kaca pelat muka dan suhu operasi)

d. Lakukan uji Tukey
```

```
Output :
```

```
