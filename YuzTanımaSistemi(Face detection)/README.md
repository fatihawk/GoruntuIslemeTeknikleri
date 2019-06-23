# Yüz Tanıma Sistemi(Face detection)

Haar özellik tabanlı kaskad sınıflandırıcılarını kullanarak Nesne Tespiti, Paul Viola ve Michael Jones tarafından 2001 yılında "Basit Özellikler Kaskadını Kullanarak Hızlı Nesne Tespiti" başlıklı makalesinde önerilen etkili bir nesne algılama yöntemidir.

Kaskad işlevi, birçok olumlu ve olumsuz görüntüden eğitilmiştir. Daha sonra diğer resimlerdeki nesneleri tespit etmek için kullanılır.

Burada yüz tanıma ile çalıştım.

OpenCV dedektörün yanı sıra bir eğitmen ile birlikte gelir. Kendi sınıflandırıcımızı, araba, uçak vb. Herhangi bir nesne için eğitmek istiyorsak, bir tane oluşturmak için OpenCV kullanabiliriz.

Burada algılama ile ilgileneceğiz. OpenCV zaten yüz, gözler, gülümsemeler vb. İçin önceden eğitilmiş sınıflandırıcıları içerir. Bu XML dosyaları opencv / data / haarcascades / klasöründe depolanır. OpenCV ile bir yüz ve göz dedektörü oluşturdum.

Öncelikle gerekli XML sınıflandırıcılarını yüklememiz gerekiyor. Ardından giriş resmimizi (veya videomuzu) gri tonlamalı modda yükledim.

Sonrasında görüntüdeki yüzleri buluyoruz. Yüzler bulunursa, algılanan yüzlerin pozisyonlarını Rect (x, y, w, h) olarak döndürür. Bu konumlara ulaştıktan sonra, yüz için bir ROI oluşturabilir ve bu ROI'ye göz algılama uygulayabiliriz.

Burada yapılan uygulamada önceden kaydedilmiş bir görüntü kullanılmadı.Webcam kullanarak anlık yüz ve göz tanıma işlemi yapıldı.Dolayısıyla hassasiyeti belirleyen çok fazla parametre var.Bunu da dikkate almak gerekir.
