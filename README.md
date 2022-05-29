# P2_Probstat_A_5025201089
Praktikum Probstat Modul 2 
Andi Muhammad Rafli - 5025201089

### Soal 1
> Seorang peneliti melakukan penelitian mengenai pengaruh aktivitas 𝐴 terhadap kadar saturasi oksigen pada manusia. Peneliti tersebut mengambil sampel sebanyak 9 responden. Pertama, sebelum melakukan aktivitas 𝐴, peneliti mencatat kadar saturasi oksigen dari 9 responden tersebut. Kemudian, 9 responden tersebut diminta melakukan aktivitas 𝐴. Setelah 15 menit, peneliti tersebut mencatat kembali kadar saturasi oksigen dari 9 responden tersebut. Berikut data dari 9 responden mengenai kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas 𝐴

<img width="211" alt="Screen Shot 2022-05-29 at 6 52 57 PM" src="https://user-images.githubusercontent.com/102727966/170866622-330cd4a2-8061-4f03-9a34-32c47c13af16.png">

Berdasarkan data pada tabel diatas, diketahui kadar saturasi oksigen dari responden ke-3 ketika belum melakukan aktivitas 𝐴 sebanyak 67, dan setelah melakukan aktivitas 𝐴 sebanyak 70.

a. Carilah Standar Deviasi dari data selisih pasangan pengamatan tabel diatas
> Untuk mencari Standar Deviasi dari data diatas dapat menggunakan `sdev`
```
Data_Frame = data.frame(Responden, x, y)
sdev = sd(Data_Frame$x-Data_Frame$y)
sdev
```
Output :
# <img width="92" alt="Screen Shot 2022-05-29 at 7 44 14 PM" src="https://user-images.githubusercontent.com/102727966/170869157-4a8993d5-2ede-4de7-acd0-aa3de81046bb.png">

b. carilah nilai t (p-value)
> Untuk mencari nilai t, dapat menggunakan `pval` sebagai berikut

```
h = Data_Frame$y - Data_Frame$x
 t_mu = mean(h)
 t_zbar = mean(h[1:6])
 t_n = 6
 t_s = sd(h[1:6])
 t = (t_zbar - t_mu) / (t_s/sqrt(t_n))
 t
 pval = 2 * pt(-abs(t), df = t_n - 1)
 pval
```
Output :
# <img width="287" alt="Screen Shot 2022-05-29 at 7 47 03 PM" src="https://user-images.githubusercontent.com/102727966/170869305-2e8682f7-bdb9-4b77-9351-e2c3ff75de17.png">

c. tentukanlah apakah terdapat pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴 jika diketahui tingkat signifikansi 𝛼 = 5% serta H0 : “tidak ada pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴”
> Nilai dari t lebih besar dari nilai kritis t dengan tingkat signifikasi 5%. dari situ dapat disimpulkan bahwa H0 ditolak dan H1 diterima. Terdapat pengaruh signifikasi secara statistika dalam hal kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas A

### Soal 2
> Diketahui bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun. Untuk menguji klaim ini, 100 pemilik mobil yang dipilih secara acak diminta untuk mencatat jarak yang mereka tempuh. Jika sampel acak menunjukkan rata-rata 23.500 kilometer dan standar deviasi 3900 kilometer. (Kerjakan menggunakan library seperti referensi pada modul).

```
install.packages("BSDA")
library(BSDA)
zsum.test(mean.x=23500, sigma.x = 3900, n.x = 100,  
          alternative = "less", mu = 0,
          conf.level = 0.95)
```

a. Apakah Anda setuju dengan klaim tersebut?
> Kesimpulan dari uji z menolak H0 sehingga mobil dikendarai dengan rata-rata lebih dari 20000 kilometer per tahun. Maka dari itu Setuju

b. Jelaskan maksud dari output yang dihasilkan!
> Maksud dari output yang dihasilkan yaitu hipotesis alternatif karena H1 diterima sehingga klaim dapat dibilang benar
 
c.  Buatlah kesimpulan berdasarkan P-Value yang dihasilkan!
> Kesimpulan berdasarkan P-value dari uji z mendekati 0 yaitu hipotesis awal ditolak dan hipotesis alternatif diterima

### Soal 3
> Diketahui perusahaan memiliki seorang data analyst ingin memecahkan permasalahan pengambilan keputusan dalam perusahaan tersebut. Selanjutnya didapatkanlah data berikut dari perusahaan saham tersebut.

# <img width="430" alt="Screen Shot 2022-05-29 at 6 52 11 PM" src="https://user-images.githubusercontent.com/102727966/170866593-4a150df2-c1ff-41dc-b484-65ee0da05701.png">

> Dari data diatas berilah keputusan serta kesimpulan yang didapatkan dari hasil diatas. Asumsikan nilai variancenya sama, apakah ada perbedaan pada rata-ratanya (α= 0.05)? Buatlah :

a. H0 dan H1
> H0 dan H1 dilakukan perhitungan untuk H0

# <img width="268" alt="Screen Shot 2022-05-29 at 9 36 02 PM" src="https://user-images.githubusercontent.com/102727966/170874873-01504e64-89ba-4853-abdf-a313ee646c1d.png">

> Dilakukannya perhitungan untuk H1 sebagai berikut

# <img width="278" alt="Screen Shot 2022-05-29 at 9 36 20 PM" src="https://user-images.githubusercontent.com/102727966/170874892-72bdc70a-17ac-4473-bc16-5dae2a8b1346.png">

b. Hitung Sampel Statistik
> Perhitunngan dapat dilakukan sebagai berikut
```
tsum.test(mean.x=3.64, s.x = 1.67, n.x = 19, mean.y =2.79 , s.y = 1.32, n.y = 27, alternative = "greater", var.equal = TRUE)
```

# <img width="484" alt="Screen Shot 2022-05-29 at 9 38 04 PM" src="https://user-images.githubusercontent.com/102727966/170874979-a134cc4c-ce66-4e32-b894-5e278d9df7b0.png">

c. Lakukan Uji Statistik (df =2)
> Pertama, install library mosaic terlebih dahulu
```
install.packages("mosaic")
library(mosaic)
```
```
plotDist(dist='t', df=2, col="blue")
Output :
```

# <img width="449" alt="Screen Shot 2022-05-29 at 9 48 11 PM" src="https://user-images.githubusercontent.com/102727966/170875539-b5e7a29b-333f-4186-aa1f-f6b0c2908831.png">

d. Nilai Kritikal
>
```
Nilai kritikal Adapun untuk mendapatkan nilai kritikal bisa menggunakan qchisq dengan df=2 sesuai soal sebelumnya
```
Output :

# <img width="322" alt="Screen Shot 2022-05-29 at 9 48 55 PM" src="https://user-images.githubusercontent.com/102727966/170875572-5270336f-52e3-477a-819a-d61d57c1381e.png">


e. Keputusan
>
```
Teori keputusan adalah teori formal pengambilan keputusan di bawah ketidakpastian. Aksinya adalah : ({a}_{a∈A}) Kemungkinan konsekuensi : ({c}_{c∈C}) (tergantung pada keadaan dan tindakan) Maka keputusan dapat dibuat dengan t.test
```


f. Kesimpulan
>
```
Kesimpulan yang didapatkan dari persoalan yaitu perbedaan rata-rata yang terjadi tidak ada jika melihat dari uji statistik dan akan ada tetapi tidak signifikan jika dipengaruhi nilai kritikal.
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
> berdasarkan plot kuantil normal di atas, tidak ditemukan outlier utama pada homogenitas varians

Source code dan output :
```
my_data <- read.delim(file.choose())

my_data$Group <- as.factor(my_data$Group)
my_data$Group = factor(my_data$Group, labels = c("grup1", "grup1", "grup3"))


grup1 <- subset(my_data, Group == "grup1")
grup2 <- subset(my_data, Group == "grup1")
grup3 <- subset(my_data, Group == "grup3")

qqnorm(grup1$Length)

qqnorm(grup2$Length)

qqnorm(grup3$Length)
```
Output : 
# <img width="787" alt="Screen Shot 2022-05-29 at 9 23 18 PM" src="https://user-images.githubusercontent.com/102727966/170874097-ff281784-b86c-49ec-9893-f32161b4e4ab.png">


b. Carilah atau periksalah Homogeneity of variances nya , Berapa nilai p yang
didapatkan? , Apa hipotesis dan kesimpulan yang dapat diambil ?

Source code dan output :
```
bartlett.test(Length ~ Group, data = my_data)
```
Output : 
```
Bartlett's K-squared = 0.013315, df = 1, p-value = 0.9081

```
 
c. Untuk uji ANOVA (satu arah), buatlah model linier dengan Panjang versus
Grup dan beri nama model tersebut model 1.

Source code:
```
model1 <- aov(Length ~ Group, data = my_data)
summary(model1)
```
Output : 

# <img width="340" alt="Screen Shot 2022-05-29 at 9 24 49 PM" src="https://user-images.githubusercontent.com/102727966/170874175-db1fea8c-8327-4c0c-bcb9-f3201c90744e.png">

 
d. Dari Hasil Poin C, Berapakah nilai-p ? , Apa yang dapat Anda simpulkan
dari H0?
> nilai dari p adalah 0.0013 dimana angkat tersebut kurang dari 0.005, sehingga h0 ditolak
 
e. Verifikasilah jawaban model 1 dengan Post-hoc test Tukey HSD, dari nilai p
yang didapatkan apakah satu jenis kucing lebih panjang dari yang lain?

Source code dan output :
```
TukeyHSD(model1)
```
Output : 

# <img width="400" alt="Screen Shot 2022-05-29 at 9 29 06 PM" src="https://user-images.githubusercontent.com/102727966/170874422-69b7944e-7197-485d-8067-83159055c0a7.png">

f. Visualisasikan data dengan ggplot2
```
library("ggplot2")

ggplot(my_data, aes(x = Group, y = Length)) + 
  geom_boxplot(fill = "white", colour = "black") + 
  scale_x_discrete() + xlab("Group") + ylab("Length")
```

### Soal 5
> Data yang digunakan merupakan hasil eksperimen yang dilakukan untuk mengetahui pengaruh suhu operasi (100 ̊C, 125 ̊C dan 150 ̊C) dan tiga jenis kaca pelat muka (A, B dan C) pada keluaran cahaya tabung osiloskop. Percobaan dilakukan sebanyak 27 kali dan didapat data sebagai berikut: Data Hasil Eksperimen. Dengan data tersebut:

a. Buatlah plot sederhana untuk visualisasi data
>  
```
install.packages("multcompView")
library(readr)
library(ggplot2)
library(multcompView)
library(dplyr)

GTL <- read_csv("GTL.csv")
head(GTL)

str(GTL)

qplot(x = Temp, y = Light, geom = "point", data = GTL) +
  facet_grid(.~Glass, labeller = label_both)
```
b. Lakukan uji ANOVA dua arah
>
```
GTL$Glass <- as.factor(GTL$Glass)
GTL$Temp_Factor <- as.factor(GTL$Temp)
str(GTL)

anova <- aov(Light ~ Glass*Temp_Factor, data = GTL)
summary(anova)
```
Output :
```

```

c. Tampilkan tabel dengan mean dan standar deviasi keluaran cahaya untuk setiap perlakuan (kombinasi kaca pelat muka dan suhu operasi)
```
data_summary <- group_by(GTL, Glass, Temp) %>%
  summarise(mean=mean(Light), sd=sd(Light)) %>%
  arrange(desc(mean))
print(data_summary)
```

d. Lakukan uji Tukey
> Gunakan fungsi 
```
tukey <- TukeyHSD(anova)
print(tukey)
```
Output :
```

```

e. Gunakan compact letter display untuk menunjukkan perbedaan signifikan
antara uji Anova dan uji Tukey
>s
```
tukey.cld <- multcompLetters4(anova, tukey)
print(tukey.cld)

cld <- as.data.frame.list(tukey.cld$`Glass:Temp_Factor`)
data_summary$Tukey <- cld$Letters
print(data_summary)
```

