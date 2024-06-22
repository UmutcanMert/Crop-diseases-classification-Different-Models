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

çalışılmıştır. Mimari de genel
olarak önce veri hazırlanmış, gerekli preprocessing işlemler uygulanmış, sonrasında model
kurulup eğitilmiş ve grafik ile tablolar oluşturulmuştur.
Geliştirilen mimari detaylıca şöyledir:
1. Veri setine ait tüm dosyalar yüklenmiştir ve ardından gerekli kütüphaneler import
edilmiştir.
“train.csv” dosyası okunup ardından dataframe’e dönüştürülmüştür.\n Dataframe’e
“label_name” ve “image_path” sütunları eklenmiştir.
