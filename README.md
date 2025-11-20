# Analisis Differencing & Uji KPSS pada Data Tenaga Kerja Wanita AS (1948–1981)

Repository ini berisi proses analisis time series pada data jumlah tenaga kerja wanita berusia 20 tahun ke atas di Amerika Serikat (1948–1981). Analisis difokuskan pada proses differencing, pemeriksaan pola, serta uji KPSS untuk mengevaluasi stasioneritas.

### Isi Repository
 - Dataset USFemalesAged20+Job1948-81.csv (446 observasi)
   
https://drive.google.com/file/d/1HvvgtM_XqaCKy4fp-5Rr_JBvIRkQZOem/view?usp=sharing

### Tools
- Python
- pandas
- statsmodels
- matplotlib
- PythonTsa (untuk ACF–PACF figure)

### Exploratory Data Analysis (EDA)
1. Analisis Tren Data
Plot utama menunjukkan:
- Tren meningkat panjang
- Fluktuasi musiman
- Indikasi non-stasioneritas

2. Subset 1963–1965
- Dipakai untuk melihat pola musiman dengan lebih jelas.

3. Plot Musiman (Monthly Seasonal Plot)
- Menunjukkan pola berulang tiap tahun → bukti adanya seasonality.

### Differencing (Diferensiasi)
Dilakukan dua tahap differencing:
- Differencing Biasa (1st difference) → menghilangkan tren
- Differencing Musiman (periode 12) → menghilangkan musiman
  
Hasilnya menunjukkan data berfluktuasi lebih stabil di sekitar mean → indikasi stasioneritas meningkat.

### ACF & PACF
Plot ACF dan PACF digunakan untuk:
- Menilai apakah autokorelasi sudah berkurang
- Mengecek apakah differencing sudah cukup
- Memberi gambaran pola model ARIMA (jika dilanjutkan)

Hasilnya menunjukkan autokorelasi melemah → mendukung stasioneritas.

### Uji Stasioneritas (KPSS)
Hasil uji KPSS:
- Data sebelum differencing → non-stasioner
- Data setelah differencing biasa + musiman → stasioner

KPSS mengonfirmasi bahwa langkah differencing sudah tepat

### Kesimpulan
- Data asli memiliki tren + musiman kuat
- Dibutuhkan 1 diferensiasi biasa dan 1 musiman
- Setelah differencing, data bersifat stasioner
- ACF–PACF serta KPSS mendukung kesimpulan tersebut
- Analisis ini merupakan dasar kuat jika ingin melanjutkan ke model ARIMA/SARIMA
