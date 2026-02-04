# 🎬 Ultimate Hybrid Recommendation Engine

> 👉 **[Tıkla: Projeyi nbviewer'da Aç](https://nbviewer.org/github/sametcsk/Hybrid-Ensemble-Recommendation-Engine/blob/main/recommend.ipynb)**

---

## 🚀 Projenin Amacı

Bu proje, tekil öneri sistemlerinin (sadece Collaborative veya sadece Content-Based) eksiklerini gidermek amacıyla geliştirilmiş, **Cold Start (Soğuk Başlangıç)** ve **Sparsity (Seyreklik)** problemlerine çözüm üreten **Hibrit bir Öneri Motorudur.**

Netflix veya Spotify gibi modern platformların kullandığı **"Ensemble" (Topluluk)** mantığını simüle eder.

## 🧠 Kullanılan Mimari ve Teknikler

Proje 4 ana stratejik katmandan oluşur:

### 1. Veri İşleme & Gürültü Temizliği (EDA)
* Amazon/MovieLens veri setlerindeki **%98+ Sparsity (Seyreklik)** problemi analiz edildi.
* "Long Tail" (Uzun Kuyruk) etkisini kırmak ve hesaplama maliyetini düşürmek için istatistiksel filtreleme (aktif kullanıcılar & popüler filmler) uygulandı.

### 2. User-Based Collaborative Filtering (İşbirlikçi Filtreleme)
* Kullanıcılar arası **Cosine Similarity** (Kosinüs Benzerliği) hesaplandı.
* **Weighted Scoring (Ağırlıklı Puanlama):** Sadece verilen puana değil, puanı veren kişinin "hedef kullanıcıya ne kadar benzediğine" göre dinamik ağırlıklandırma yapıldı.

### 3. Content-Based Filtering (NLP & İçerik Tabanlı)
* Film türleri (Metadata) **TF-IDF Vectorizer** (Term Frequency-Inverse Document Frequency) ile sayısallaştırıldı.
* Bu sayede, henüz kimse tarafından puanlanmamış (Cold Start) yeni filmler bile içerik benzerliğine göre doğru kişilere önerilebilir hale geldi.

### 4. Ultimate Ensemble Logic (Final Karar Verici)
* Collaborative ve Content-Based modellerin çıktıları **"Fermuar Yöntemi" (Zipper Approach)** ile birleştirildi.
* Algoritma, mükerrer önerileri (Duplicates) eledi ve kullanıcıya hem popüler hem de kişisel zevklerine uygun dengeli bir liste sundu.

## 🛠️ Teknolojiler

* **Python**
* **Pandas & NumPy:** Vektörel işlemler ve veri manipülasyonu.
* **Scikit-learn:** Cosine Similarity, TF-IDF, pairwise metrics.
* **Seaborn & Matplotlib:** Veri görselleştirme ve EDA.

## 📊 Kurulum ve Çalıştırma

1. Repoyu klonlayın:
   ```bash
   git clone [https://github.com/sametcsk/Hybrid-Ensemble-Recommendation-Engine.git](https://github.com/sametcsk/Hybrid-Ensemble-Recommendation-Engine.git)