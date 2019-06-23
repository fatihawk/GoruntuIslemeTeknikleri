Yüz Tanýma Sistemi(Face detection)

Haar özellik tabanlý kaskad sýnýflandýrýcýlarýný kullanarak Nesne Tespiti, Paul Viola ve Michael Jones tarafýndan 2001 yýlýnda "Basit Özellikler Kaskadýný Kullanarak Hýzlý Nesne Tespiti" baþlýklý makalesinde önerilen etkili bir nesne algýlama yöntemidir.

Kaskad iþlevi, birçok olumlu ve olumsuz görüntüden eðitilmiþtir. Daha sonra diðer resimlerdeki nesneleri tespit etmek için kullanýlýr.

Burada yüz tanýma ile çalýþtým.

OpenCV dedektörün yaný sýra bir eðitmen ile birlikte gelir. Kendi sýnýflandýrýcýmýzý, araba, uçak vb. Herhangi bir nesne için eðitmek istiyorsak, bir tane oluþturmak için OpenCV kullanabiliriz.

Burada algýlama ile ilgileneceðiz. OpenCV zaten yüz, gözler, gülümsemeler vb. Ýçin önceden eðitilmiþ sýnýflandýrýcýlarý içerir. Bu XML dosyalarý opencv / data / haarcascades / klasöründe depolanýr. OpenCV ile bir yüz ve göz dedektörü oluþturdum.

Öncelikle gerekli XML sýnýflandýrýcýlarýný yüklememiz gerekiyor. Ardýndan giriþ resmimizi (veya videomuzu) gri tonlamalý modda yükledim.

Sonrasýnda görüntüdeki yüzleri buluyoruz. Yüzler bulunursa, algýlanan yüzlerin pozisyonlarýný Rect (x, y, w, h) olarak döndürür. Bu konumlara ulaþtýktan sonra, yüz için bir ROI oluþturabilir ve bu ROI'ye göz algýlama uygulayabiliriz.

Burada yapýlan uygulamada önceden kaydedilmiþ bir görüntü kullanýlmadý.Webcam kullanarak anlýk yüz ve göz tanýma iþlemi yapýldý.Dolayýsýyla hassasiyeti belirleyen çok fazla parametre var.Bunu da dikkate almak gerekir.
