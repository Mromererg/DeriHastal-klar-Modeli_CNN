# Deri Hastalıkları Sınıflandırma Modeli

Bu proje, Kaggle'dan indirilen "Skin Diseases Dataset" veri setini kullanarak çeşitli deri hastalıklarını sınıflandırmak için derin öğrenme tabanlı bir model eğitme çalışmasıdır. Önceden eğitilmiş ResNet50 modeli kullanılarak, veri ön işleme, veri artırma ve model eğitimi adımları PyTorch kütüphanesi ile gerçekleştirilmiştir.

## Proje Tanımı

Bu çalışma, makine öğrenmesi ve derin öğrenme tekniklerini uygulayarak farklı deri hastalıklarını görüntüler üzerinden otomatik olarak sınıflandırabilen bir model geliştirmeyi amaçlar. Model, ResNet50 mimarisini temel alır ve görsel verilerden özellik çıkararak hastalık türlerini ayırt etmeyi öğrenir.

## Kullanılan Veri Seti
*   **Adı:** Skin Diseases Dataset
*   **Kaynak:** Kaggle (Sayed Hossain Jobayer)
*   **Erişim:** [https://www.kaggle.com/datasets/sayedhossainjobayer/skin-diseases-dataset](https://www.kaggle.com/datasets/sayedhossainjobayer/skin-diseases-dataset)

Bu veri seti, çeşitli deri hastalıklarına ait görsel örnekler içermektedir. Proje kapsamında indirilip kullanılmıştır.

## Metodoloji ve Modelin Çalışması

Proje temel olarak aşağıdaki adımları takip eder:

1.  **Veri Setinin İndirilmesi ve Hazırlığı:**
    *   Kaggle API kullanılarak veri seti Google Colab ortamına indirilir.
    *   İndirilen zip dosyası açılır.
    *   `.kaggle` klasörü oluşturulur, API anahtarı kopyalanır ve gerekli izinler ayarlanır.

2.  **İlk Veri Analizi ve Temizliği:**
    *   Veri setindeki sınıf dağılımı incelenir ve sınıflardaki görsel sayıları kontrol edilir.
    ![İlk Sınıf Dağılımı](SinifDagilimlari.png)
    *   Görsel dosyaları doğrulanır ve bozuk veya geçersiz formatta olan görseller silinerek veri seti temizlenir.

3.  **Veri Dengeleme (Data Augmentation):**
    *   Veri setindeki sınıflar arası dengesizlikleri gidermek ve modelin farklı görsel varyasyonlarına karşı daha dayanıklı olmasını sağlamak amacıyla veri artırma teknikleri uygulanır.
    *   `torchvision.transforms` kullanılarak rastgele yatay çevirme, döndürme, renk değişimi gibi dönüşümler uygulanır.
    *   Her sınıfın belirli bir hedef görsel sayısına (örneğin 1500) ulaşması hedeflenerek az sayıdaki sınıflara ait görseller çoğaltılır.
    ![Veri Artırma Süreci](ArttirilmisVeri.png)

4.  **Veri Setinin Eğitim ve Doğrulama Kümelerine Ayrılması:**
    *   Dengelenmiş veri seti, model eğitimi ve performans doğrulaması için eğitim ve doğrulama (validation) kümelerine ayrılır. `sklearn.model_selection.train_test_split` kullanılarak verinin %80'i eğitime, %20'si doğrulamaya ayrılır ve ilgili klasörlere kopyalanır.

5.  **Veri Yükleyicilerin Hazırlanması:**
# Deri Hastalıkları Sınıflandırma Modeli

Bu proje, Kaggle'dan indirilen "Skin Diseases Dataset" veri setini kullanarak çeşitli deri hastalıklarını sınıflandırmak için derin öğrenme tabanlı bir model eğitme çalışmasıdır. Önceden eğitilmiş ResNet50 modeli kullanılarak, veri ön işleme, veri artırma ve model eğitimi adımları PyTorch kütüphanesi ile gerçekleştirilmiştir.

## Proje Tanımı

Bu çalışma, makine öğrenmesi ve derin öğrenme tekniklerini uygulayarak farklı deri hastalıklarını görüntüler üzerinden otomatik olarak sınıflandırabilen bir model geliştirmeyi amaçlar. Model, ResNet50 mimarisini temel alır ve görsel verilerden özellik çıkararak hastalık türlerini ayırt etmeyi öğrenir.

## Kullanılan Veri Seti
*   **Adı:** Skin Diseases Dataset
*   **Kaynak:** Kaggle (Sayed Hossain Jobayer)
*   **Erişim:** [https://www.kaggle.com/datasets/sayedhossainjobayer/skin-diseases-dataset](https://www.kaggle.com/datasets/sayedhossainjobayer/skin-diseases-dataset)

Bu veri seti, çeşitli deri hastalıklarına ait görsel örnekler içermektedir. Proje kapsamında indirilip kullanılmıştır.

## Metodoloji ve Modelin Çalışması

Proje temel olarak aşağıdaki adımları takip eder:

1.  **Veri Setinin İndirilmesi ve Hazırlığı:**
    *   Kaggle API kullanılarak veri seti Google Colab ortamına indirilir.
    *   İndirilen zip dosyası açılır.
    *   `.kaggle` klasörü oluşturulur, API anahtarı kopyalanır ve gerekli izinler ayarlanır.

2.  **İlk Veri Analizi ve Temizliği:**
    *   Veri setindeki sınıf dağılımı incelenir ve sınıflardaki görsel sayıları kontrol edilir.
    ![İlk Sınıf Dağılımı](SinifDagilimlari.png)
    *   Görsel dosyaları doğrulanır ve bozuk veya geçersiz formatta olan görseller silinerek veri seti temizlenir.

3.  **Veri Dengeleme (Data Augmentation):**
    *   Veri setindeki sınıflar arası dengesizlikleri gidermek ve modelin farklı görsel varyasyonlarına karşı daha dayanıklı olmasını sağlamak amacıyla veri artırma teknikleri uygulanır.
    *   `torchvision.transforms` kullanılarak rastgele yatay çevirme, döndürme, renk değişimi gibi dönüşümler uygulanır.
    *   Her sınıfın belirli bir hedef görsel sayısına (örneğin 1500) ulaşması hedeflenerek az sayıdaki sınıflara ait görseller çoğaltılır.
    ![Veri Artırma Süreci](ArttirilmisVeri.png)

4.  **Veri Setinin Eğitim ve Doğrulama Kümelerine Ayrılması:**
    *   Dengelenmiş veri seti, model eğitimi ve performans doğrulaması için eğitim ve doğrulama (validation) kümelerine ayrılır. `sklearn.model_selection.train_test_split` kullanılarak verinin %80'i eğitime, %20'si doğrulamaya ayrılır ve ilgili klasörlere kopyalanır.

5.  **Veri Yükleyicilerin Hazırlanması:**
    *   PyTorch `torchvision.datasets.ImageFolder` kullanılarak eğitim ve doğrulama klasörlerindeki görüntüler yüklenir.
    *   `torch.utils.data.DataLoader` ile veri yükleyiciler oluşturulur. Eğitim verisine rastgele augmentasyonlu dönüşümler uygulanırken, doğrulama verisine sadece boyutlandırma ve normalizasyon dönüşümleri uygulanır.

6.  **Model Tanımlama:**
    *   PyTorch'un `torchvision.models` kütüphanesinden ImageNet üzerinde önceden eğitilmiş bir ResNet50 modeli yüklenir. ResNet50, derin ağların eğitimindeki bozunma (degradation) problemini çözmek için atlamalı bağlantılar (skip connections) kullanan güçlü bir Evrişimsel Sinir Ağı (CNN) mimarisidir ve görüntü sınıflandırma görevlerinde yaygın olarak kullanılır.
    *   Modelin son tam bağlantılı (fully connected) katmanı, veri setindeki sınıf sayısına (7 deri hastalığı + Normal cilt) uygun şekilde yeniden yapılandırılır.
    *   Model, eğitim için uygun cihaza (GPU veya CPU) gönderilir.

7.  **Eğitim Ortamının Hazırlanması:**
    *   Sınıflandırma görevi için `torch.nn.CrossEntropyLoss` kaybı fonksiyonu tanımlanır.
    *   Model ağırlıklarını güncellemek için `torch.optim.Adam` optimize edici tanımlanır.

8.  **Modelin Eğitilmesi:**
    *   Model, belirlenen epoch sayısı boyunca eğitim veri kümesi üzerinde eğitilir.
    *   Her epoch sonunda modelin eğitim ve doğrulama kümelerindeki kaybı ve doğruluğu hesaplanır ve yazdırılır.
    ![Eğitim ve Doğrulama Grafikleri](Sonuc.Grafigi.png)

9.  **Model Değerlendirmesi:**
    *   Eğitim tamamlandıktan sonra, modelin performansı doğrulama veri seti üzerinde `sklearn.metrics` ve `seaborn` kullanılarak değerlendirilir.
    *   Modelin hangi sınıfları doğru tahmin ettiğini ve hangi sınıfları birbiriyle karıştırdığını gösteren Karışıklık Matrisi (Confusion Matrix) oluşturulur ve görselleştirilir.
    ![Karışıklık Matrisi](ConfusionMatrix.png)
    *   Sınıflandırma raporu (Classification Report) hesaplanabilir (notebook'ta açıkça yazdırılmamış, ancak matris varsa hesaplanabilir).

10. **Eğitilmiş Modelin Kaydedilmesi:**
    *   Eğitilmiş modelin ağırlıkları (`state_dict`), PyTorch'un `torch.save` fonksiyonu kullanılarak `.pth` formatında (`resnet50_skin_disease.pth`) kaydedilir.
    *   Kaydedilen model dosyası Google Colab ortamından indirilebilir veya Google Drive gibi bulut depolama alanlarına kaydedilebilir.

## Proje Nasıl Kullanılır/Çalıştırılır

Proje `Untitled15.ipynb` adlı Jupyter Notebook dosyasındadır ve Google Colab gibi GPU desteği sunan bir Jupyter ortamında çalıştırılması önerilir. Notebook'taki kod hücrelerini sırasıyla çalıştırarak tüm adımları uygulayabilirsiniz.

1.  **Notebook'u Açın:** `Untitled15.ipynb` dosyasını Google Colab veya benzer bir Jupyter ortamında açın.
2.  **Kaggle API Anahtarını Yükleyin:** İlk kod hücresini çalıştırarak Kaggle API anahtarınız olan `kaggle.json` dosyasını Colab'a yükleyin.
3.  **Veri Setini İndirin ve Çıkarın:** İlgili kod hücrelerini çalıştırarak veri setini indirin, `.kaggle` klasörünü oluşturup anahtarı kopyalayın, izinleri ayarlayın ve veri setini `skin_diseases` klasörüne çıkarın.
4.  **Veriyi Hazırlayın ve Dengeleyin:** Veri setindeki sınıf dağılımını kontrol eden, bozuk görselleri silen ve veri artırma uygulayarak veri setini dengeleyen hücreleri sırasıyla çalıştırın.
5.  **Veriyi Bölün ve Yükleyicileri Oluşturun:** Veri setini eğitim ve doğrulama kümelerine ayıran ve PyTorch `DataLoader` nesnelerini oluşturan hücreleri çalıştırın.
6.  **Modeli Tanımlayın:** Önceden eğitilmiş ResNet50 modelini yükleyen, son katmanını ayarlayan ve modeli uygun cihaza gönderen hücreyi çalıştırın. Cihazın GPU olarak ayarlandığından emin olun.
7.  **Eğitim Ortamını Ayarlayın:** Kayıp fonksiyonunu ve optimize ediciyi tanımlayan hücreleri çalıştırın.
8.  **Modeli Eğitin:** Model eğitim döngüsünü içeren hücreyi çalıştırın.
9.  **Sonuçları Görselleştirin:** Eğitim süresince elde edilen kayıp ve doğruluk değerlerinin grafiklerini çizen hücreyi çalıştırın.
10. **Modeli Kaydedin:** Eğitilmiş modelin ağırlıklarını `.pth` dosyasına kaydeden hücreyi çalıştırın. İndirme veya Google Drive'a kaydetme adımlarını içeren hücreleri ihtiyacınıza göre çalıştırın.
11. **Modeli Değerlendirin (Karışıklık Matrisi):** Karışıklık matrisi ve sınıflandırma metriklerini oluşturan ve görselleştiren hücreyi çalıştırın.

## Dosya Yapısı

