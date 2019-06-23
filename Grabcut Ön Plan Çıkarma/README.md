# Grabcut Ön Plan Çıkarma

Buradaki amaç ön planı bulmak ve arka planı kaldırmaktır.

Bu bir yeşil ekranın yaptığını yapacağız.Sadece burada yeşil ekrana ihtiyacımız olmayacak.

İlk başta cv2, numpy ve matplotlib'i içe aktardık.

Sonra görüntüyü yüklüyoruz, maske oluşturuyoruz, algoritmanın dahili olarak kullandığı arkaplan ve ön plan modelini belirtiyoruz.

Asıl önemli kısım tanımladığımız doğrultudur. Bu rect = (start_x, start_y, width, height).Ana nesneyi çevreleyen dikdörtgen budur.

Buradaki koordinatlar bu görsele ait.Farklı görseller için farklı görseller kullanmak gerekir.

Bu yüzden biz burada birkaç parametre aldık ve cv2.grabCut kullandık.

Önce giriş görüntüsü, ardından maske, sonra ana nesnemiz için dikdörtgen, arka plan modeli, ön plan modeli, çalıştırılacak yineleme miktarı ve hangi modu kullandığımızı belirtiyoruz.



![alt text](https://github.com/fatihawk/GoruntuIslemeTeknikleri/blob/master/Grabcut%20%C3%96n%20Plan%20%C3%87%C4%B1karma/saat_test.jpg)


![alt text](https://github.com/fatihawk/GoruntuIslemeTeknikleri/blob/master/Grabcut%20%C3%96n%20Plan%20%C3%87%C4%B1karma/Sonuc.png)
