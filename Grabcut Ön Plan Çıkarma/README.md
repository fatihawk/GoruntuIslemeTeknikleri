Grabcut Ön Plan Çýkarma

Buradaki amaç ön planý bulmak ve arka planý kaldýrmaktýr.

Bu bir yeþil ekranýn yaptýðýný yapacaðýz.Sadece burada yeþil ekrana ihtiyacýmýz olmayacak.

Ýlk baþta cv2, numpy ve matplotlib'i içe aktardýk.

Sonra görüntüyü yüklüyoruz, maske oluþturuyoruz, algoritmanýn dahili olarak kullandýðý arkaplan ve ön plan modelini belirtiyoruz.

Asýl önemli kýsým tanýmladýðýmýz doðrultudur. Bu rect = (start_x, start_y, width, height).Ana nesneyi çevreleyen dikdörtgen budur.

Buradaki koordinatlar bu görsele ait.Farklý görseller için farklý görseller kullanmak gerekir.

Bu yüzden biz burada birkaç parametre aldýk ve cv2.grabCut kullandýk.

Önce giriþ görüntüsü, ardýndan maske, sonra ana nesnemiz için dikdörtgen, arka plan modeli, ön plan modeli, çalýþtýrýlacak yineleme miktarý ve hangi modu kullandýðýmýzý belirtiyoruz.