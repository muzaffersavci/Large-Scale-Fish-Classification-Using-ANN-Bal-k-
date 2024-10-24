# Balık Türlerini Sınıflandırma - Derin Öğrenme Projesi

Bu proje, Akbank Derin Öğrenme Bootcamp'inde yapılan balık türlerini sınıflandırmaya yönelik bir derin öğrenme projesidir. Veri seti, çeşitli balık türlerinin görüntülerini içermekte olup, her görüntü için hangi balık türüne ait olduğu etiketlenmiştir. Projede, **ResNet50V2** ve **MobileNetV2** gibi transfer öğrenme modelleri kullanılarak, balık fotoğraflarının sınıflandırılması hedeflenmiştir.

## İçindekiler
- [Proje Tanımı](#proje-tanımı)
- [Veri Seti](#veri-seti)
- [Model Mimarisi](#model-mimarisi)
- [Ön İşleme ve Veri Artırma](#ön-işleme-ve-veri-artırma)
- [Eğitim ve Test Setlerinin Hazırlanması](#eğitim-ve-test-setlerinin-hazırlanması)
- [Sonuçlar](#sonuçlar)
- [Nasıl Çalıştırılır](#nasıl-çalıştırılır)
- [Gereksinimler](#gereksinimler)

## Proje Tanımı
Bu proje, bir görüntü veri seti üzerinde çalışarak, çeşitli balık türlerini sınıflandırmak için derin öğrenme modellerini kullanmaktadır. Veri setinde toplamda 9 farklı balık türü yer almakta olup, her bir balığın görüntüleri belirli etiketlerle ilişkilendirilmiştir.

Projedeki adımlar şunlardır:
1. Veri yükleme ve veri ön işleme
2. Transfer öğrenme modellerinin kullanımı (ResNet50V2, MobileNetV2)
3. Eğitim ve test veri setlerine ayırma
4. Model eğitimi ve değerlendirme

## Veri Seti
Bu proje, Kaggle üzerinde bulunan "A Large-Scale Fish Dataset" veri setini kullanmaktadır. Veri setinde 9 farklı balık türüne ait toplamda **9000 görüntü** bulunmaktadır. Her sınıfta 1000 görüntü yer almaktadır. Sınıflar şunlardır:
- **Hourse Mackerel**
- **Black Sea Sprat**
- **Sea Bass**
- **Red Mullet**
- **Trout**
- **Striped Red Mullet**
- **Shrimp**
- **Gilt-Head Bream**
- **Red Sea Bream**

## Model Mimarisi
Proje kapsamında, transfer öğrenme yöntemi ile önceden eğitilmiş **ResNet50V2** ve **MobileNetV2** modelleri kullanılmıştır. Bu modeller, balık fotoğraflarından özellik çıkarımı yaparak sınıflandırma işlemi gerçekleştirmektedir. Model mimarisi, sınıflandırma için ek katmanlarla zenginleştirilmiştir:

- **Conv2D**: Görüntülerin özelliklerini çıkaran katman
- **MaxPooling2D**: Özellik haritası boyutlarını küçültmek için kullanılır
- **Flatten**: Katmanlar arası geçiş için kullanılır
- **Dense**: Tam bağlantılı katman

## Ön İşleme ve Veri Artırma
Veri seti, eğitim sırasında daha dengeli ve verimli sonuçlar elde etmek amacıyla aşağıdaki adımlarla ön işlenmiştir:

- Görüntülerin yeniden boyutlandırılması: Tüm görüntüler **224x224** boyutuna getirildi.
- **ImageDataGenerator** kullanılarak veri artırma işlemleri yapıldı:
  - Resim döndürme, kırpma, ölçeklendirme vb. işlemler uygulandı.
  - Verilerin eğitim, doğrulama ve test setlerine bölünmesi sağlandı.

## Eğitim ve Test Setlerinin Hazırlanması
Veri seti şu şekilde bölünmüştür:
- **%80 eğitim seti** (5760 görüntü)
- **%20 doğrulama seti** (1440 görüntü)
- **%20 test seti** (1800 görüntü)

## Sonuçlar
Modelin eğitiminden sonra elde edilen sonuçlar aşağıda belirtilmiştir:
- Eğitim doğruluğu: `%X`
- Test doğruluğu: `%X`
- Confusion Matrix ve Classification Report ile sınıflandırma sonuçları detaylı olarak sunulmuştur.

## Nasıl Çalıştırılır
Projeyi kendi bilgisayarınızda çalıştırmak için aşağıdaki adımları takip edebilirsiniz:

1. **Gereksinimleri yükleyin:**
    ```bash
    pip install -r requirements.txt
    ```

2. **Veri setini indirin:**
    Kaggle üzerinden veri setini indirin ve belirtilen dizine yerleştirin.

3. **Projeyi çalıştırın:**
    Python dosyasını çalıştırarak modeli eğitebilir ve sonuçları gözlemleyebilirsiniz.
    ```bash
    python train.py
    ```

## Gereksinimler
Projeyi çalıştırmak için gerekli olan Python kütüphaneleri:
- TensorFlow == 2.16.1
- Numpy
- Pandas
- Matplotlib
- Seaborn
- scikit-learn
Muzaffer Savcıoğlu
Kaggle Link : https://www.kaggle.com/code/muzaffersv/large-scale-fish-classification-using-ann-bal-k/notebook?scriptVersionId=203197178
