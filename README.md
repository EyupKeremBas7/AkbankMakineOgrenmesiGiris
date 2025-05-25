# Akbank Makine Öğrenmesine Giriş Bootcamp Projesi

## Giriş

Bu projede, [UCI Adult](https://archive.ics.uci.edu/dataset/2/adult) veri seti kullanılarak bireylerin gelirlerinin 50K$'dan fazla olup olmadığını tahmin etmek için çeşitli makine öğrenmesi algoritmaları uygulanmıştır. Proje kapsamında veri ön işleme, modelleme, değerlendirme ve hiperparametre optimizasyonu adımları gerçekleştirilmiştir.

## Kullanılan Veri Seti

- **Veri seti:** UCI Adult (Census Income)  
- **Özellikler:** Yaş, eğitim, meslek, medeni durum, cinsiyet, saatlik çalışma, ülke vb.
- **Hedef:** income (<=50K veya >50K, 0 ve 1 olarak kodlandı)

## Uygulanan Modeller

- Lojistik Regresyon
- Karar Ağacı (Decision Tree)
- K-En Yakın Komşu (KNN)
- Destek Vektör Makineleri (SVM)

Veri setindeki kategorik değişkenler sayısal değerlere dönüştürülmüş, tüm özellikler standartlaştırılmıştır. Eğitim ve test setleri ayrılmıştır.

## Hiperparametre Optimizasyonu

Lojistik Regresyon ve SVM modelleri için GridSearchCV ile hiperparametre optimizasyonu yapılmıştır. Böylece modellerin azınlık sınıfa (yüksek gelirli bireyler) duyarlılığı artırılmaya çalışılmıştır.

## Sonuçlar ve Yorumlar

- **Lojistik Regresyon:** Genel doğruluk ve dengeli sınıflandırma açısından iyi sonuçlar vermiştir.
- **SVM:** Çoğunluk sınıfını çok iyi tahmin ederken azınlık sınıfında düşük başarı göstermiştir.
- Hiperparametre optimizasyonu ile bazı modellerin azınlık sınıfa duyarlılığı artmış, ancak genel doğrulukta düşüş gözlemlenmiştir.
- Sınıf dengesizliği, modellerin performansını önemli ölçüde etkilemiştir.

### Örnek Metrikler

| Model                | Accuracy | Macro F1 | Sınıf 1 Recall |
|----------------------|----------|----------|---------------|
| Lojistik Regresyon   | 0.83     | 0.72     | 0.46          |
| SVM                  | 0.80     | 0.58     | 0.16          |

## Gerçek Hayatta Uygulama Örnekleri

- **Kredi Skorlama ve Bankacılık:** Müşterilerin gelir seviyesini tahmin ederek kredi risk analizi.
- **Sigorta Sektörü:** Poliçe fiyatlandırması ve müşteri segmentasyonu.
- **Pazarlama:** Hedefli reklam kampanyaları için yüksek gelirli bireylerin tespiti.
- **Kamu Politikaları:** Sosyal yardım ve destek programlarının planlanması.
- **İK ve İşe Alım:** Maaş tekliflerinin optimize edilmesi.

### Sonuç ve Kişisel Öğrenimlerim

Bu proje kapsamında makine öğrenmesi sürecinin veri ön işleme, modelleme, değerlendirme ve hiperparametre optimizasyonu gibi temel adımlarını uygulama fırsatı buldum. Özellikle veri setindeki kategorik değişkenlerin sayısallaştırılması, veri ölçekleme ve eğitim/test ayrımı gibi işlemlerin model başarısı üzerindeki etkisini gözlemledim.

Çeşitli algoritmalar denedikten sonra, **Lojistik Regresyon** modelini tercih ettim. Bunun başlıca nedeni, modelin hem doğruluk hem de sınıflar arası denge açısından daha tutarlı sonuçlar vermesi oldu. Sınıf dengesizliği olan veri setlerinde, sadece doğruluk oranına bakmanın yanıltıcı olabileceğini; F1-score, precision ve recall gibi metriklerin de mutlaka değerlendirilmesi gerektiğini öğrendim.

Hiperparametre optimizasyonunda ise **GridSearchCV** yöntemini kullandım. GridSearch, belirlediğim parametre aralıklarında tüm kombinasyonları sistematik olarak denediği için, özellikle küçük ve orta büyüklükteki veri setlerinde güvenilir sonuçlar veriyor. Alternatif olarak kullanılabilecek **RandomizedSearchCV** ise daha büyük parametre alanlarında ve zaman kısıtı olduğunda avantajlı olabilir. Ancak bu projede parametre alanım çok geniş olmadığı için GridSearchCV'yi tercih ettim.

Ayrıca, modelin azınlık sınıfa (yüksek gelirli bireyler) olan duyarlılığını artırmak için class_weight parametresiyle oynamanın ve hiperparametre optimizasyonunun önemini deneyimledim. Sadece kod yazmak değil, elde edilen sonuçları yorumlamak ve iş hedeflerine uygun model seçimi yapmak gerektiğini de bu süreçte daha iyi kavradım.

Sonuç olarak, bu proje bana makine öğrenmesinde veri hazırlamanın, doğru metriklerle değerlendirme yapmanın ve model/hyperparametre seçiminin ne kadar kritik olduğunu gösterdi. Gelecekte daha büyük veri setleriyle çalışırken farklı optimizasyon tekniklerini ve gelişmiş modelleri de denemek istiyorum.

## Kaggle Linkleri

https://www.kaggle.com/code/eypkeremba/akbank-makine-renimine-giri-bootcamp
