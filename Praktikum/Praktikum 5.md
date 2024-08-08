# NOMOR 1
## kode program
```mysql
SELECT COUNT(NIP) AS JumlahPegawai, COUNT(Jabatan) AS JumlahJabatan FROM pegawai;
```

## HASIL 
![[Screenshot_20240801-132316_Termux.jpg]]

## ANALISIS 

1. `COUNT(NIP) AS JumlahPegawai`: Menghitung jumlah pegawai berdasarkan jumlah NIP (Nomor Induk Pegawai). Kolom NIP biasanya bersifat unik untuk setiap pegawai, sehingga perintah ini akan memberikan total jumlah pegawai dalam tabel `pegawai`.
    
2. `COUNT(Jabatan) AS JumlahJabatan`: Menghitung jumlah entri pada kolom `Jabatan`. Kolom `Jabatan` mungkin memiliki nilai yang sama untuk beberapa pegawai (misalnya, banyak pegawai yang memiliki jabatan yang sama), tetapi query ini menghitung jumlah total baris yang memiliki nilai dalam kolom `Jabatan`.
    

Analisis lebih lanjut dari hasil query ini dapat mencakup hal-hal berikut:

1. **Jumlah Pegawai (JumlahPegawai)**: Ini memberikan total jumlah individu yang tercatat dalam sistem atau database. Jika nilai ini tinggi, itu menunjukkan banyaknya pegawai yang ada dalam organisasi.
    
2. **Jumlah Jabatan (JumlahJabatan)**: Ini memberikan jumlah total jabatan yang diisi oleh pegawai. Jika nilai ini berbeda dari jumlah pegawai, bisa jadi ada pegawai yang tidak memiliki jabatan yang tercatat atau ada jabatan yang dicatat lebih dari satu kali (mungkin karena ada pegawai yang memiliki jabatan ganda atau pencatatan yang tidak konsisten).
    
3. **Konsistensi Data**: Jika jumlah pegawai dan jumlah jabatan sangat berbeda, ini mungkin menandakan adanya masalah dalam pencatatan data, seperti pegawai yang tidak memiliki jabatan yang dicatat atau data jabatan yang tidak lengkap.
    
4. **Pengelolaan Sumber Daya Manusia**: Informasi ini dapat digunakan untuk analisis lebih lanjut mengenai distribusi pegawai dalam berbagai jabatan, mengidentifikasi jabatan yang kurang atau lebih banyak diisi, dan membantu dalam perencanaan sumber daya manusia.


# NOMOR 2
## kode program 
```mysql
SELECT COUNT(NIP) AS JumlahPegawai
FROM pegawai
WHERE NoCab = 'C102';
```

## HASIL 
![[Screenshot_20240801-132618_Termux.jpg]]

## ANALISIS 

- **Jumlah Pegawai di Cabang Tertentu**:
    
    - `COUNT(NIP) AS JumlahPegawai`: Menghitung jumlah pegawai yang bekerja di cabang dengan kode 'C102'. Karena NIP adalah Nomor Induk Pegawai yang unik untuk setiap pegawai, hasil query ini akan memberikan total jumlah pegawai di cabang tersebut.
- **Filter Berdasarkan Kode Cabang**:
    
    - `WHERE NoCab = 'C102'`: Filter ini memastikan bahwa hanya pegawai yang bekerja di cabang dengan kode 'C102' yang dihitung. Ini penting untuk analisis spesifik cabang tersebut.
- **Kegunaan Analisis**:
    
    - **Perencanaan Sumber Daya Manusia**: Informasi ini sangat berguna untuk manajemen dalam merencanakan alokasi sumber daya manusia di cabang tertentu. Jika jumlah pegawai di cabang ini rendah, mungkin perlu dilakukan rekrutmen tambahan atau redistribusi pegawai.
    - **Evaluasi Cabang**: Dapat digunakan untuk mengevaluasi beban kerja di cabang tersebut. Jika jumlah pegawai terlalu banyak atau terlalu sedikit dibandingkan dengan cabang lain atau kebutuhan operasi, manajemen dapat mengambil tindakan yang sesuai.
    - **Penentuan Kebijakan**: Memungkinkan perusahaan untuk membuat kebijakan yang lebih tepat berdasarkan distribusi pegawai di berbagai cabang.
- **Pengelolaan Efisiensi Cabang**:
    
    - **Mengidentifikasi Kebutuhan**: Jika cabang 'C102' memiliki banyak pegawai, tetapi kinerjanya rendah, mungkin perlu dilakukan evaluasi lebih lanjut terhadap efisiensi operasional di cabang tersebut.
    - **Komparasi Antar Cabang**: Data ini juga dapat dibandingkan dengan data dari cabang lain untuk melihat apakah ada ketidakseimbangan dalam distribusi pegawai di berbagai cabang perusahaan.


# NOMOR 3
```mysql
SELECT COUNT(NIP) AS JumlahPegawai
FROM pegawai
WHERE NoCab = 'C102';
```
## HASIL 
![[Screenshot_20240801-132618_Termux 1.jpg]]
## ANALISIS 


- **`SELECT COUNT(NIP) AS JumlahPegawai`**: Menghitung total jumlah pegawai (berdasarkan NIP) yang bekerja di cabang tertentu.
- **`FROM pegawai`**: Mengambil data dari tabel `pegawai`.
- **`WHERE NoCab = 'C102'`**: Memfilter data sehingga hanya pegawai yang bekerja di cabang dengan kode 'C102' yang dihitung.


# NOMOR 4
## kode program 
```mysql
SELECT NoCab, COUNT(NIP) AS Jumlah_pegawai
FROM pegawai
GROUP BY NoCab
HAVING COUNT(NIP) >= 3
```
## HASIL 
![[Screenshot_20240801-132624_Termux 1.jpg]]

## ANALISIS 
- **`SELECT NoCab, COUNT(NIP) AS Jumlah_pegawai`**: Memilih kolom `NoCab` (kode cabang) dan menghitung jumlah pegawai (`COUNT(NIP)`) di setiap cabang.
- **`FROM pegawai`**: Mengambil data dari tabel `pegawai`.
- **`GROUP BY NoCab`**: Mengelompokkan hasil berdasarkan kode cabang (`NoCab`).
- **`HAVING COUNT(NIP) >= 3`**: Menyaring hasil untuk hanya menampilkan cabang yang memiliki tiga pegawai atau lebih.
# NOMOR 5
## kode program 
```mysql
SELECT SUM(Gaji) AS Total_Gaji
FROM pegawai;
```
## HASIL 
![[Screenshot_20240801-133812_Termux 1.jpg]]
## ANALISIS 

# NOMOR 6
## kode program 
```mysql
SELECT SUM(Gaji) AS Gaji_Manajer
FROM pegawai
WHERE Jabatan = 'Manajer';
```
## HASIL 
![[Screenshot_20240801-133904_Termux.jpg]]

## ANALISIS 

# NOMOR 7
## kode program 
```mysql
SELECT NoCab, SUM(Gaji) AS TotalGaji
FROM pegawai
GROUP BY NoCab;

```
## HASIL
![[Screenshot_20240801-133955_Termux.jpg]]
## ANALISIS 

# NOMOR 8
## kode program 
```mysql
SELECT NoCab, SUM(Gaji) AS TotalGaji
FROM pegawai
GROUP BY NoCab HAVING SUM(Gaji) >= 8000000;
```
## HASIL 
![[Screenshot_20240801-134040_Termux.jpg]]
## ANALISIS 

# NOMOR 9
```mysql
SELECT AVG(Gaji) AS Rata_rata
FROM tabel_pegawai;';
```
## HASIL
![[Screenshot_20240801-134152_Termux 1.jpg]]
## ANALISIS 

# NOMOR 10
## kode program 
```mysql
SELECT AVG(Gaji) AS GajiRataMgr
FROM pegawai
WHERE Jabatan = 'Manajer';
```
## HASIL 
![[Screenshot_20240801-134231_Termux 1.jpg]]

## ANALISIS 

# NOMOR 11
## kode program 
```mysql
SELECT NoCab, AVG(Gaji) AS RataGaji
FROM pegawai
GROUP BY NoCab;
```
## HASIL 
![[Screenshot_20240801-134321_Termux.jpg]]
## ANALISIS 

# NOMOR 12
## kode program 
```mysql
SELECT NoCab, AVG(Gaji) AS RataGaji
FROM pegawai
GROUP BY NoCab HAVING NoCab = 'C101' OR NoCab = 'C102';
```
## HASIL 
![[Screenshot_20240801-134424_Termux.jpg]]
## ANALISIS 

# NOMOR 13
## kode program 
```mysql
SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
FROM pegawai;
```
## HASIL 
![[Screenshot_20240801-134508_Termux.jpg]]
## ANALISIS 

# NOMOR 14
```mysql
SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
FROM pegawai
WHERE Jabatan = 'Manajer';
```
## HASIL 
![[Screenshot_20240801-134605_Termux.jpg]]

## ANALISIS 

# NOMOR 15
## kode program 
```mysql
SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
FROM pegawai
GROUP BY NoCab;
```
## HASIL 
![[Screenshot_20240801-134653_Termux.jpg]]
## ANALISIS 

# NOMOR 16
## kode program 
```mysql
SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
FROM pegawai
GROUP BY NoCab HAVING COUNT(NIP) >= 3;
```
## HASIL 
![[Screenshot_20240801-134739_Termux.jpg]]
## ANALISIS 

# NOMOR 17
```mysql
SELECT 
  COUNT(NIP) AS JumlahPegawai,
  SUM(Gaji) AS TotalGaji,
  AVG(Gaji) AS RataGaji,
  MAX(Gaji) AS GajiMaks,
  MIN(Gaji) AS GajiMin
FROM pegawai;
```
## HASIL 
![[Screenshot_20240801-134825_Termux.jpg]]
## ANALISIS 

# NOMOR 18
## kode program 
```mysql
SELECT 
  NoCab,
  COUNT(NIP) AS JumlahPegawai,
  SUM(Gaji) AS TotalGaji,
  AVG(Gaji) AS RataGaji,
  MAX(Gaji) AS GajiMaks,
  MIN(Gaji) AS GajiMin
FROM pegawai
WHERE Jabatan = 'Staf' OR Jabatan = 'Sales'
GROUP BY NoCab
HAVING SUM(Gaji) <= 2600000;
```

## HASIL ![[Screenshot_20240801-134916_Termux.jpg]]

## ANALISIS 