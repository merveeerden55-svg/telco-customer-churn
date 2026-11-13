# Telco Customer Churn – Müşteri Kaybı Tahmin Projesi

## Proje Hakkında

Bu projede telekomünikasyon sektöründe müşteri kaybı (Customer Churn) incelenmiş ve makine öğrenmesi algoritmaları kullanılarak müşterilerin hizmetten ayrılma olasılıkları tahmin edilmiştir.

Projenin temel amacı, müşteri kaybıyla ilişkili faktörleri analiz etmek ve işletmelerin müşteri tutundurma stratejilerine veri odaklı karar desteği sağlamaktır.

## Kullanılan Veri Seti

- **Veri seti:** Telco Customer Churn
- **Kaynak:** [Kaggle – Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- **Başlangıç kayıt sayısı:** 7.043
- **Temizleme sonrası kayıt sayısı:** 7.032
- **Hedef değişken:** Churn (Yes / No)

## Kullanılan Teknolojiler

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Veri Ön İşleme

- Eksik veriler incelenmiş ve gerekli temizlik işlemleri yapılmıştır.
- Sayısal ve kategorik değişkenler ayrıştırılmıştır.
- Modelleme için müşteri kimlik numarası analiz dışı bırakılmıştır.
- Kategorik değişkenler One-Hot Encoding yöntemiyle dönüştürülmüştür.
- Eğitim ve test verileri ayrılmıştır.
- Veri sızıntısını önlemek amacıyla ön işleme adımları model pipeline'ı içerisinde uygulanmıştır.

## Keşifsel Veri Analizi

Müşteri kaybı; sözleşme türü, müşteri kıdemi, aylık ücret ve ödeme yöntemi gibi değişkenler üzerinden incelenmiştir.

Analiz kapsamında müşteri kayıp dağılımı ve farklı müşteri özellikleri arasındaki ilişkiler grafiklerle değerlendirilmiştir.

## Makine Öğrenmesi Modelleri

Projede iki sınıflandırma algoritması kullanılmıştır:

1. Logistic Regression
2. Decision Tree

Modeller Accuracy, Precision, Recall ve Confusion Matrix metrikleriyle değerlendirilmiştir.

## Model Sonuçları

| Metrik | Logistic Regression | Decision Tree |
|---|---:|---:|
| Accuracy | %72,6 | %73,3 |
| Precision | %49,0 | %49,9 |
| Recall | %79,7 | %79,4 |

Modellerin müşteri kaybı yaşayan müşterileri yakalama performansları yaklaşık %79 seviyesindedir.

## Ekonomik Değerlendirme

Yanlış sınıflandırmaların işletmeye oluşturabileceği maliyetler varsayımsal bir senaryo üzerinden karşılaştırılmıştır.

- Yanlış pozitif (FP) maliyeti: 100 birim
- Yanlış negatif (FN) maliyeti: 1.500 birim

Bu varsayımlar altında Logistic Regression modelinin tahmini toplam maliyeti 145.000 birim, Decision Tree modelinin tahmini toplam maliyeti 145.300 birim olarak hesaplanmıştır.

Bu değerlendirme, model seçiminde yalnızca tahmin başarısının değil, hataların ekonomik sonuçlarının da dikkate alınması gerektiğini göstermektedir.

*Not: Maliyet değerleri gerçek işletme verilerine değil, karşılaştırma amacıyla oluşturulmuş varsayımlara dayanmaktadır.*

## Ek Analiz: Müşteri Kayıp Riski Sınıflandırması

Decision Tree modeli kullanılarak test verisindeki müşteriler ayrılma olasılıklarına göre düşük, orta ve yüksek risk gruplarına ayrılmıştır.

Bu analizle işletmelerin müşteri tutundurma bütçelerini öncelikli risk gruplarına yönlendirebileceği bir karar destek yaklaşımı geliştirilmiştir.

## Genel Sonuç

Çalışma, veri analitiği ve makine öğrenmesi yöntemlerinin müşteri ilişkileri yönetimi, gelir sürekliliği ve işletmelerin kaynak tahsisi kararlarında kullanılabileceğini göstermektedir.

Elde edilen bulgular betimsel ve tahmine dayalıdır; değişkenler arasındaki ilişkiler tek başına nedensellik kanıtı olarak değerlendirilmemelidir.

## Proje Dosya Yapısı
## Proje Dosya Yapısı

```text
telco-customer-churn/
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── notebooks/
│   └── customer_churn.ipynb
│
└── README.md
```

## Kurulum

Gerekli Python kütüphanelerini yüklemek için:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

## Çalıştırma

1. Depoyu bilgisayarınıza indirin veya klonlayın.
2. Gerekli Python kütüphanelerini yükleyin.
3. `notebooks/customer_churn.ipynb` dosyasını VS Code veya Jupyter Notebook ile açın.
4. Hücreleri sırasıyla çalıştırın.

## Keşifsel Veri Analizi

Müşteri kaybı; sözleşme türü, müşteri kıdemi, aylık ücret ve ödeme yöntemi gibi değişkenler üzerinden incelenmiştir.

Analiz kapsamında toplam 8 grafik kullanılarak müşteri kayıp dağılımı ve farklı müşteri özellikleri arasındaki ilişkiler değerlendirilmiştir.

Ek analizlerde:

- StreamingTV ve StreamingMovies hizmetlerinin kullanımı,
- Partner ve Dependents değişkenleri üzerinden aile ve hane yapısı,
- PhoneService ve MultipleLines değişkenleri üzerinden telefon hizmeti kullanımı

ile müşteri kaybı oranları karşılaştırılmıştır.

Bu analizler, müşteri kaybıyla ilişkili olabilecek farklı müşteri özelliklerini incelemek ve işletmeler için veri odaklı çıkarımlar geliştirmek amacıyla gerçekleştirilmiştir.
