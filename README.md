# NLP ile Duygu Analizi (Sentiment Analysis) Projesi

Bu projede, makine öğrenmesi ve doğal dil işleme (NLP) teknikleri kullanılarak Twitter gönderilerinin (tweetler) **olumlu** veya **olumsuz** duygu taşıyıp taşımadığını otomatik olarak sınıflandıran bir model geliştirilmiştir.

## Kullanılan Veri Seti

- [Sentiment140](https://www.kaggle.com/datasets/kazanova/sentiment140)
- 5000 olumlu ve 5000 olumsuz tweet rastgele seçilerek dengeli bir veri seti oluşturulmuştur.

## Proje Adımları

### 1. Veri Yükleme ve Dengeleme
- Veri setinden sadece 0 (negatif) ve 4 (pozitif) etiketli tweetler seçildi.
- Her iki sınıftan eşit sayıda (5000'er) örnek alınarak birleştirildi.

### 2. Ön İşleme (Data Preprocessing)
- Metinler küçük harfe çevrildi.
- Linkler, kullanıcı adları ve noktalama işaretleri kaldırıldı.
- Gereksiz boşluklar temizlendi.

### 3. Özellik Çıkarımı (Feature Extraction)
- Tweetler sayısal vektörlere dönüştürüldü (TF-IDF ile).

### 4. Model Eğitimi ve Testi
- Logistic Regression modeli ile eğitim gerçekleştirildi.
- Model, test verisinde yaklaşık %74 doğruluk oranına ulaştı.

### 5. Sonuçların Değerlendirilmesi

|           | Precision | Recall | F1-Score | Support |
|-----------|-----------|--------|----------|---------|
| Negatif   |   0.75    |  0.74  |   0.74   |  1013   |
| Pozitif   |   0.73    |  0.74  |   0.74   |   987   |
| **Accuracy** |       |        | **0.74** |  2000   |

### 6. Anahtar Kelime Analizi ve Görselleştirme
- Negatif ve pozitif tweetlerde en sık geçen 20 kelime grafiklerle gösterildi.

![negatif_tweetler_grafik](negatif_tweetler.png)
![pozitif_tweetler_grafik](pozitif_tweetler.png)

---

## Kullanılan Kütüphaneler

- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- re (regular expressions)
- collections.Counter

## Projeyi Çalıştırmak İçin

1. Gerekli kütüphaneleri yükleyin:
   ```sh
   pip install pandas numpy scikit-learn matplotlib seaborn

Jupyter Notebook ortamında notebook dosyasını açın ve adımları sırayla çalıştırın.

Sonuç grafiklerini inceleyin.
Notlar
Daha iyi sonuçlar için farklı modeller, stopwords çıkarımı veya n-gram gibi gelişmiş metin işleme yöntemleri denenebilir.

Bu proje, temel seviye bir NLP duygu analizi örneğidir ve eğitim amacıyla hazırlanmıştır.

English Version 
Sentiment Analysis with NLP
This project develops a machine learning model to automatically classify Twitter posts as positive or negative using NLP techniques.

Dataset
Sentiment140

5000 positive and 5000 negative tweets were randomly sampled to create a balanced dataset.

Project Steps
Data Loading & Balancing: Only 0 (negative) and 4 (positive) tweets are used.

Preprocessing: Lowercasing, URL/user removal, punctuation and whitespace cleaning.

Feature Extraction: Tweets are converted into numerical vectors using TF-IDF.

Model Training & Evaluation: Logistic Regression model achieves about 74% accuracy.

Keyword Analysis: Top 20 words in positive and negative tweets visualized.