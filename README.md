# Segmentasi dan Klasifikasi Pelanggan Berdasarkan Transaksi

Proyek ini bertujuan untuk melakukan segmentasi pelanggan berdasarkan perilaku belanja mereka menggunakan metode unsupervised learning (clustering), lalu menerapkan supervised learning (klasifikasi) untuk memprediksi segmen pelanggan dari data baru. Pendekatan ini sangat bermanfaat untuk pengambilan keputusan bisnis dan strategi pemasaran yang lebih tepat sasaran.

---

## 📁 Dataset

Dataset berisi informasi transaksi pelanggan dengan rincian sebagai berikut:

| Kolom           | Deskripsi                                    |
|------------------|----------------------------------------------|
| `Order_ID`       | ID pesanan                                   |
| `Customer_ID`    | ID pelanggan                                 |
| `Customer_Type`  | Tipe pelanggan (misalnya baru/lama)          |
| `Product`        | Nama produk                                  |
| `Category`       | Kategori produk                              |
| `Unit_Price`     | Harga satuan produk                          |
| `Quantity`       | Jumlah barang yang dibeli                    |
| `Discount`       | Diskon yang diberikan                        |
| `Total_Price`    | Total harga setelah diskon                   |
| `Region`         | Wilayah/lokasi pelanggan                     |
| `Order_Date`     | Tanggal transaksi                            |

Ukuran dataset: **10.000 baris x 11 kolom**  
📥 Karena ukuran file cukup besar, dataset dapat diunduh melalui link berikut:

🔗 **[Unduh Dataset dari Google Drive](https://drive.google.com/uc?export=download&id=1CwdIsSq4ok4SM70rfxYTIcef-c7_UzYl)**

---

## 🔍 Hasil Clustering

Data pelanggan telah dikelompokkan menjadi 3 kluster berdasarkan `Unit_Price`, `Total_Price`, `Quantity`, dan `Discount`. Berikut ringkasan tiap kluster:

### 📦 Kluster 0
- **Rata-rata Harga Satuan:** €4.22  
- **Rata-rata Total Harga:** €82.06  
- **Rata-rata Kuantitas:** 28.50  
- **Rata-rata Diskon:** 0.19  

💡 **Analisis:**  
Pelanggan dengan pembelian produk murah dalam jumlah besar. Kemungkinan pembeli ritel atau pembeli eceran grosir.

---

### 📦 Kluster 1
- **Rata-rata Harga Satuan:** €92.11  
- **Rata-rata Total Harga:** €6445.27  
- **Rata-rata Kuantitas:** 79.09  
- **Rata-rata Diskon:** 0.25  

💡 **Analisis:**  
Pelanggan B2B dengan transaksi besar. Membeli produk mahal dalam jumlah banyak dan mendapatkan diskon besar.

---

### 📦 Kluster 2
- **Rata-rata Harga Satuan:** €44.80  
- **Rata-rata Total Harga:** €2201.97  
- **Rata-rata Kuantitas:** 63.20  
- **Rata-rata Diskon:** 0.18  

💡 **Analisis:**  
Pelanggan dengan transaksi menengah. Produk yang dibeli sedikit lebih mahal dari kluster 0, namun tidak sebesar kluster 1.

---

## 🤖 Klasifikasi

Setelah data diklaster, model klasifikasi digunakan untuk memprediksi kluster dari data baru. Berikut hasil evaluasi beberapa model:

| Model               | Akurasi | Presisi | Recall | F1 Score |
|---------------------|--------|---------|--------|----------|
| KNN                 | 0.9864 | 0.9854  | 0.9864 | 0.9852   |
| Decision Tree       | 1.0000 | 1.0000  | 1.0000 | 1.0000   |
| Random Forest       | 1.0000 | 1.0000  | 1.0000 | 1.0000   |
| SVM                 | 0.9907 | 0.9908  | 0.9907 | 0.9898   |
| Naive Bayes         | 0.8863 | 0.9726  | 0.8863 | 0.9210   |
| Logistic Regression | 0.9835 | 0.9820  | 0.9835 | 0.9811   |

---

## 📦 Instalasi Dependensi

Instal semua library yang dibutuhkan menggunakan perintah berikut:

```bash
pip install -r requirements.txt
