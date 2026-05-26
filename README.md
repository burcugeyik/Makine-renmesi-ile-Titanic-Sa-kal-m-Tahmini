# 🚢 Titanic Sağkalım Tahmini - XGBoost ile Uçtan Uca Veri Bilimi Projesi

Bu proje, veri biliminin klasikleşmiş "Titanic: Machine Learning from Disaster" veri seti üzerinde, ham verilerin temizlenmesinden (data preprocessing) özellik mühendisliğine (feature engineering) ve makine öğrenmesi modelinin eğitilmesine kadar olan tüm süreçleri içeren uçtan uca bir veri bilimi uygulamasıdır.

## 🎯 Projenin Amacı
Gemi yolcularının demografik ve bilet bilgilerini (yaş, cinsiyet, bilet sınıfı, aile durumu vb.) analiz ederek, bir yolcunun facia esnasında hayatta kalıp kalamayacağını (`Survived`) yüksek doğrulukla tahmin etmek.

## 🛠️ Kullanılan Teknolojiler ve Kütüphaneler
* **Python 3.13**
* **Pandas & NumPy:** Veri manipülasyonu ve analizi
* **Scikit-Learn:** Veriyi bölme (`train_test_split`) ve başarı metrikleri hesaplama
* **XGBoost:** Gradient Boosting tabanlı güçlü makine öğrenmesi algoritması

## 📊 Uygulanan Veri Bilimi Adımları

### 1. Eksik Verilerin Yönetimi (Missing Value Imputation)
* Veri setinde bulunan eksik yaş (`Age`) verileri, veri kaybını önlemek amacıyla yolcuların yaş ortalaması (`mean`) ile dinamik olarak doldurulmuştur.

### 2. Kategorik Verilerin Sayısallaştırılması (Label Encoding)
* Algoritmanın metinsel ifadeleri işleyebilmesi için `Sex` (Cinsiyet) kolonundaki `male` ve `female` değerleri sırasıyla `0` ve `1` sayısal değerlerine haritalanmıştır (`map`).

### 3. Özellik Mühendisliği (Feature Engineering)
* Modelin tahmin başarısını artırmak adına yolcuların yalnızlık/aile durumunu temsil eden yeni bir öznitelik üretilmiştir. `SibSp` (Kardeş/Eş) ve `Parch` (Ebeveyn/Çocuk) kolonları matematiksel olarak toplanarak **`FamilySize` (Aile Boyutu)** kolonu oluşturulmuştur.

### 4. Model Eğitimi ve Doğrulama (Validation)
* Veri seti **%80 Eğitim (Train)** ve **%20 Test** olmak üzere ikiye ayrılmıştır.
* Model olarak endüstri standardı olan **XGBoost Classifier** tercih edilmiştir.

## 🏆 Proje Sonucu ve Kaggle Başarısı
Model, daha önce hiç görmediği test verileri üzerinde yapılan denemelerde **%79.89** yerel doğruluk skoru elde etmiştir. 

Üretilen tahmin dosyası Kaggle platformuna yüklenmiş, test edilmiş ve format doğrulaması (Successful Submission) alınarak ilk denemede küresel çapta **0.74880 (Public Score)** başarısına ulaşmıştır.
