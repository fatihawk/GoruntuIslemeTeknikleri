## Canny Edge Uygulaması

Canny kenar dedektörü, görüntülerdeki çok çeşitli kenarları algılamak için çok aşamalı bir algoritma kullanan bir kenar algılama operatörüdür.

Bu algoritma 5 aşamadan oluşur.

1)Gürültü azaltma:Görüntünün arkasında yer alan matematik temelde türevlere dayandığından, kenar algılama sonuçları görüntü gürültüsüne karşı oldukça hassastır.Görüntüdeki gürültüden kurtulmanın bir yolu, Gauss bulanıklığını pürüzsüzleştirmek için uygulamaktır.

2)Gradyan hesaplaması:Kenar algılama operatörlerini kullanıp resmin gradyanını hesaplayarak kenar yoğunluğunu ve yönünü algılar.Kenarlar, piksellerin yoğunluğundaki değişime karşılık gelir. Bunu tespit etmenin en kolay yolu, bu yoğunluk değişimini vurgulayan filtreleri her iki yönde de uygulamaktır.

3)Maksimum olmayan bastırma işlemi:İdeal olarak, son görüntünün ince kenarları olmalıdır. Bu nedenle, kenarları inceltmek için maksimum olmayan baskılama uygulamamız gerekir.Prensip basittir: algoritma, gradyan yoğunluk matrisi üzerindeki tüm noktalardan geçer ve kenar yönlerinde maksimum değeri olan pikselleri bulur.

4)Çift Threshold işlemi:Çift eşik adımı, 3 tür pikselin belirlenmesini amaçlamaktadır: güçlü, zayıf ve konuyla ilgili olmayan.Güçlü pikseller yoğunluğu o kadar yüksek olan piksellerdir; son kenara katkıda bulunduklarından eminiz.Zayıf pikseller, yoğunluk değeri olarak kabul edilmek için yeterli olmayan, ancak kenar algılama için uygun olmadığı düşünülebilecek kadar küçük olmayan bir yoğunluk değerine sahip piksellerdir.Diğer pikseller kenar için uygun değildir.

5)Histeresiz ile Kenar Takibi:Eşik sonuçlarına dayanarak, histerezis, zayıf pikselleri güçlü olanlara dönüştürmekten ibarettir.

Ben bu uygulamada aynı şekilde OpenCV kütüphanesi yardımıyla "cv2.Canny()"fonksiyonunu kullanarak alınan canlı görüntü üzerinde bir kenar belirleme uygulaması yaptım.
