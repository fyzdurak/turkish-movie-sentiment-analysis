# turkish-movie-sentiment-analysis
Türkçe Film Yorumları Duygu Analizi (NLP &amp; Machine Learning)
#  Turkish Movie Sentiment Analysis (Türkçe Film Yorumları Duygu Analizi)

Bu proje, sinema filmlerine yapılan Türkçe kullanıcı yorumlarını analiz ederek metnin "Olumlu" mu yoksa "Olumsuz" mu olduğunu otomatik olarak tahmin eden bir Doğal Dil İşleme (NLP) ve Makine Öğrenmesi projesidir.

##  Proje Özeti & Metrikler
* **Veri Seti:** Kaggle - Turkish Movie Sentiment Analysis Dataset (~83,000 yorum)
* **Kullanılan Model:** Logistic Regression
* **Metin Dönüştürme:** TF-IDF Vectorizer (5000 özellik)
* **Model Başarısı (Accuracy):** %77.69

##  Yapılan İşlemler (Pipeline)
1. **Veri Etiketleme (Labeling):** Sürekli sayısal puan verileri (1-10 arası), 5 eşik değeri kabul edilerek Olumlu (1) ve Olumsuz (0) olarak sınıflandırıldı.
2. **Metin Ön İşleme (Text Preprocessing):** 
   * Tüm metinler küçük harfe çevrildi.
   * Noktalama işaretleri, sayılar ve web linkleri Regex (`re`) kullanılarak temizlendi.
   * Türkçe etkisiz kelimeler (`NLTK Stopwords`) metinden ayıklandı.
3. **Vektörleştirme (Vectorization):** Temizlenen metinler, kelimelerin frekans ve ayırt edicilik değerlerini hesaplayan **TF-IDF** yöntemiyle sayısal matrislere dönüştürüldü.
4. **Modelleme:** Veri %80 Eğitim, %20 Test olarak bölündü ve Scikit-Learn kütüphanesi ile Logistic Regression modeli eğitildi.

##  Örnek Tahminler
* *"Hayatımda izlediğim en muhteşem filmdi, oyuncu kadrosu harika."* -> **😊 OLUMLU**
* *"Tam bir zaman kaybı, param boşa gitti. Kimseye tavsiye etmem."* -> **😞 OLUMSUZ**
