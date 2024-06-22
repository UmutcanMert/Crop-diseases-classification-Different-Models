#### Crop-diseases-classificatio-Different-Models
[](https://www.kaggle.com/datasets/mexwell/crop-diseases-classification/data)https://www.kaggle.com/datasets/mexwell/crop-diseases-classification/data

Yukarıda belirtilen linkteki ilgili veri seti üzerinde proje uygulanmıştır.

Proje kapsamında ilgili veri seti ile;
1. Alexnet, VGGnet, Resnet ve Googlenet mimarileriyle modellerinin kurulması
2. Model için öğrenme hızı, kernel boyutu, padding vb. farklı parametre ayarlamaları
3. Doğruluk, Kesinlik, Geri Çağırma, F-ölçüsüne dayalı olarak sonuçları içeren modellerin
performansı için bir karşılaştırma tablosu
4. Geliştirilen mimarinin detaylıca anlatımı
5. En iyi performans elde edilen parametre değerleri sunulmuştur.

Mimari de genel olarak önce veri hazırlanmış, gerekli preprocessing işlemler uygulanmış, sonrasında model
kurulup eğitilmiş ve grafik ile tablolar oluşturulmuştur.
Geliştirilen mimari detaylıca şöyledir:
1. Veri setine ait tüm dosyalar yüklenmiştir ve ardından gerekli kütüphaneler import
edilmiştir.

“train.csv” dosyası okunup ardından dataframe’e dönüştürülmüştür. Dataframe’e
“label_name” ve “image_path” sütunları eklenmiştir.

Dataframe, train ve test olarak bölünmüştür.

İlk 3 adım için veri seti ayrıca incelenmiş. Bazı sınıfların yoğunlukta olduğu
gözlemlenmiştir.


4. Sıra modelleri kurmaya geldi. İlk modelimiz “ALEXNET” için katmanları oluşturup model
kurulmuştur.
a. ALEXNET için input_shape 227x227x3 dür. Conv2D ile MaxPool2D arasında
“BatchNormalization” kullanılmıştır. Toplam 6 adet kullanılması uygun
görülmüştür. Ayrıca Dense katmanlarından sonra 2 adet “Dropout” kullanılmıştır.
Tüm parametreler resimde görüldüğü gibidir.

5. Alexnet modeli için model compile yapılmış olup SGD, "Stochastic Gradient Descent"
kullanılmıştır. Learning rate olarak “0.0001” kullanılmıştır. Metrics olarak da accuracy
yapılmıştır.

6. Bu adımda “epochs”, “batch_size”, ”image_height”, “image_widht” parametleri statik
olarak belirlenmiştir. Bu hem modele uygunluk için hem de optimum sonuçları almak için
deneme yanılma yoluyla böyle belirlenmiştir.
a. Ardından veri normalize edilip veri artırma işlemi için “ImageDataGenerator”
fonksiyonu kullanılmıştır. Bu fonksiyondaki parametre ayarları yine deneme
yanılma yoluyla denenmiş ve buna göre ayarlanmıştır. Resimde tüm parametreler
gözükmektedir.

7. Veri artırma jeneratörleri (data augmentation generator), her bir epoch (iterasyon)
sırasında görüntülerin farklı varyasyonlarını sağlayarak eğitim veri setini sürekli olarak
çeşitlendirir ve modelin daha genelleştirilebilir olmasını sağlar. Bu şekilde, overfitting
(aşırı uyum) riski azaltılır ve daha iyi bir model performansı elde edilir. Bu yüzden
mimaride de kullanılması uygun görülmüştür.

8. Alexnet modeli eğitilmiştir ve accuracy değeri 0.6513 olarak bitmiştir.

9. Alexnet modelinin çıktıları “accuracy-val_accuracy” ve “loss-val_loss” grafikleri
çizilmiştir.
