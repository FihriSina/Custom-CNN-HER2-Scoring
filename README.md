# Custom-CNN-HER2-Scoring 🔬🧠

Bu projede, Breast Cancer Immunohistochemical (BCI) veri seti kullanılarak HER2 skorlarının sınıflandırılması amacıyla sıfırdan bir Convolutional Neural Network (CNN) modeli tasarlanmıştır.

## 🚀 Proje Özeti

- ✅ Kullanılan veri seti: Ödev olarak yaptığım ve dataset bana ait olmadığı için paylaşamıyorum
- ✅ Sınıflar: `0`, `1+`, `2+`, `3+`
- ✅ Görüntü boyutu: `1024x1024x3` → `128x128x3` olarak yeniden boyutlandırıldı.
- ✅ Kullanılan kütüphaneler: PyTorch, torchvision, sklearn, TensorBoard

## 📊 Model Mimarisi

CNN modeli sıfırdan tanımlanmış olup aşağıdaki katmanlardan oluşur:

- 4 adet Conv2D + ReLU + MaxPool bloğu
- Flatten
- 3 adet Fully Connected katman (ReLU aktivasyonlu)
- Sonuç katmanı (4 sınıf için)

Model mimarisi görsel olarak şöyle gösterilmiştir:

![Model Diagram](./model_diagram.png)  ← (*Eğer çizdiğin görseli koyarsan*)

## 📈 Eğitim Süreci

- Epoch: 200  
- Loss Function: CrossEntropyLoss  
- Optimizer: Adam (lr=0.001)  
- TensorBoard ile loss ve accuracy izleme yapılmıştır.  
- Validation Accuracy ~ %61

## 🧪 Sonuçlar

- Accuracy: %61 civarında  
- Confusion Matrix ve sınıf bazlı başarı skorları eklenmiştir.  
- Overfitting tespiti yapılmış, çözüm önerileri sunulmuştur.

## 🔍 Gözlemler

- Dengesiz veri dağılımı sonucu sınıflarda farklı başarı oranları gözlemlenmiştir.
- Eğitim setinde yüksek doğruluk, validation setinde sabit doğruluk → Overfitting problemi
- İyileştirme için: Data Augmentation, Dropout, BatchNorm, EarlyStopping önerilmiştir.

## 📁 Proje Dosyaları

- `DeepLearning.ipynb`: Eğitim & test kodları
- `best_model.pt`: En iyi model ağırlıkları
- `runs/`: TensorBoard kayıtları
- `README.md`: Bu açıklama dosyası

## 📝 Not

Bu çalışma tamamen eğitim amaçlı hazırlanmıştır. Model, hazır CNN kütüphaneleri kullanmadan sıfırdan yazılmıştır.
