# Template Matching Uygulaması

Buradaki fikir, sağladığımız şablonla eşleşen ve belirli bir eşik değeri veren bir görüntünün aynı bölgelerini bulmaktır.

Kesin nesne eşleşmeleri için, tam aydınlatma / ölçek / açı ile, bu sistem daha verimli çalışabilir. 

Bu koşulların genellikle karşılandığı bir örnek, bilgisayardaki herhangi bir GUI ile ilgilidir. Düğmeler ve benzeri öğeler her zaman aynıdır, böylece şablon eşleştirmesini kullanabiliriz.

Başlamak için bir ana görüntüye ve bir şablona ihtiyacımız olacak. Şablonunuzu, görüntüde tam olarak aradığınız "şey" den almalıyız.

Ben bu uygulamada aynı girişlere sahip bir PC görseli aldım.

Burada önemli olan eşleştirmek istediğimiz nesnenin şablonda birden fazla ve aynı şekilde yer alması.

Ben bu uygulamada OpenCV'nin "cv2.matchTemplate()" fonksiyonunu kullanarak eşleştirme yaptım.

Burada Threshold değerini değiştirerek eşleşme doğruluğunu kontrol edebiliriz.

Şablon:

![alt text](https://github.com/fatihawk/GoruntuIslemeTeknikleri/blob/master/Template%20Matching%20(Sablon%20Esleme)%20Uygulamas%C4%B1/Sablon.jpg)

Eşleştirilecek görsel:
![alt text](https://github.com/fatihawk/GoruntuIslemeTeknikleri/blob/master/Template%20Matching%20(Sablon%20Esleme)%20Uygulamas%C4%B1/Eslestirilecek_gorsel.jpg)

Sonuç:
![alt text](https://github.com/fatihawk/GoruntuIslemeTeknikleri/blob/master/Template%20Matching%20(Sablon%20Esleme)%20Uygulamas%C4%B1/Sonuc.png)

