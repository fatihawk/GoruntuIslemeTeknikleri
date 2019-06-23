# Goruntu İşleme Teknikleri

# OpenCV kullanarak Python üzerinde Temel Görüntü işleme Tekniklerinin Uygulanması

1-Görüntü üzerinde MOG filtresinin uygulanması

Gaussianların Karışımı( Mixture of Gaussians=MOG), statik kameralardan hareketli cisimleri saptamak için arkaplan modellemesi için yaygın olarak kullanılan bir yaklaşımdır.

Ben de OpenCV destekli "createBackgroundSubtractorMOG2()"fonksiyonu yardımıyla alınan bir görüntü üzerindeki hareketli nesneleri tespit etmek için kullanılan filtreleme işlemini yaptım.

2-CannyEdge Uygulaması

Canny kenar dedektörü, görüntülerdeki çok çeşitli kenarları algılamak için çok aşamalı bir algoritma kullanan bir kenar algılama operatörüdür.

Ben bu uygulamada aynı şekilde OpenCV kütüphanesi yardımıyla "cv2.Canny()"fonksiyonunu kullanarak alınan canlı görüntü üzerinde bir kenar belirleme uygulaması yaptım.

3-Template Matching Uygulaması

Buradaki fikir, sağladığımız şablonla eşleşen ve belirli bir eşik değeri veren bir görüntünün aynı bölgelerini bulmaktır.

Burada önemli olan eşleştirmek istediğimiz nesnenin şablonda birden fazla ve aynı şekilde yer alması.

Ben bu uygulamada OpenCV'nin "cv2.matchTemplate()" fonksiyonunu kullanarak eşleştirme yaptım.

4-YuzTanımaSistemi(Face detection)

Haar özellik tabanlı kaskad sınıflandırıcılarını kullanarak Nesne Tespiti, Paul Viola ve Michael Jones tarafından 2001 yılında "Basit Özellikler Kaskadını Kullanarak Hızlı Nesne Tespiti" başlıklı makalesinde önerilen etkili bir nesne algılama yöntemidir.

kaskad işlevi, birçok olumlu ve olumsuz görüntüden eğitilmiştir. Daha sonra diğer resimlerdeki nesneleri tespit etmek için kullanılır.

Burada yüz tanıma ile çalıştım.

OpenCV dedektörün yanı sıra bir eğitmen ile birlikte gelir. Kendi sınıflandırıcımızı, araba, uçak vb. Herhangi bir nesne için eğitmek istiyorsak, bir tane oluşturmak için OpenCV kullanabilirsiniz.

Burada algılama ile ilgileneceğiz. OpenCV zaten yüz, gözler, gülümsemeler vb. İçin önceden eğitilmiş sınıflandırıcıları içerir. Bu XML dosyaları opencv / data / haarcascades / klasöründe depolanır. OpenCV ile bir yüz ve göz dedektörü oluşturdum.

Öncelikle gerekli XML sınıflandırıcılarını yüklememiz gerekiyor. Ardından giriş resmimizi (veya videomuzu) gri tonlamalı modda yükledim.

Sonrasında görüntüdeki yüzleri buluyoruz. Yüzler bulunursa, algılanan yüzlerin pozisyonlarını Rect (x, y, w, h) olarak döndürür. Bu konumlara ulaştıktan sonra, yüz için bir ROI oluşturabilir ve bu ROI'ye göz algılama uygulayabiliriz.

Burada yapılan uygulamada önceden kaydedilmiş bir görüntü kullanılmadı.Webcam kullanarak anlık yüz ve göz tanıma işlemi yapıldı.Dolayısıyla hassasiyeti belirleyen çok fazla parametre var.Bunu da dikkate almak gerekir.

5-Özellik Eşleştirme(Homography)

Özellik eşleme, mükemmel eşleşmenin gerekli olduğu şablon eşleştirmenin(template matching) biraz daha etkileyici bir sürümü olacak.

Bulmayı umduğumuz resimle başlıyoruz ve sonra bu resmi başka bir resim içinde arayabiliyoruz. Buradaki fark yaratıcı kısım, görüntünün aynı ışıklandırma, açı, dönüş vb. olması gerekmez. Özelliklerin sadece eşleşmesi gerekiyor.

Başlamak için bazı örnek resimlere ihtiyacımız var. Bizim "şablon" veya resmimizle eşleşmeye çalışacağız:

Burada, şablon resmimiz, şablonda arayacağımız resimden biraz daha küçük. Aynı zamanda farklı bir rotasyon ve bazı farklı gölgeler yok ama eğer bu özelliklere sahip başka görseller olursa daha iyi sonuçlar alabiliriz.

Şimdi bir ""brute force" eşleştirme şekli kullanacağız. Her iki resimdeki tüm özellikleri bulacağız. Sonra bu özellikleri eşleştiriyoruz. Daha sonra istediğimiz kadar çekip çıkarabiliriz. Yine de dikkatli olmakta fayda var çünkü 500 eşleşme söylersek, birçok yanlış pozitif elde edebiliriz.

Burada eşleştirme işlemini "cv2.drawMatches()"fonksiyonunu kullanarak gerçekleştirdim.

6-Grabcut Ön Plan Çıkarma

Buradaki amaç ön planı bulmak ve arka planı kaldırmaktır.

Bu bir yeşil ekranın yaptığını yapacağız.Sadece burada yeşil ekrana ihtiyacımız olmayacak.

İlk başta cv2, numpy ve matplotlib'i içe aktardık.

Sonra görüntüyü yüklüyoruz, maske oluşturuyoruz, algoritmanın dahili olarak kullandığı arkaplan ve ön plan modelini belirtiyoruz.

Asıl önemli kısım tanımladığımız doğrultudur. Bu rect = (start_x, start_y, width, height).Ana nesneyi çevreleyen dikdörtgen budur.

Buradaki koordinatlar bu görsele ait.Farklı görseller için farklı görseller kullanmak gerekir.

Bu yüzden biz burada birkaç parametre aldık ve cv2.grabCut kullandık.

Önce giriş görüntüsü, ardından maske, sonra ana nesnemiz için dikdörtgen, arka plan modeli, ön plan modeli, çalıştırılacak yineleme miktarı ve hangi modu kullandığımızı belirtiyoruz.

7-Yeşil renkli nesne algılama uygulaması

Bilgisayarla görme tekniklerini kullanarak yeşil renkli nesneleri takip eden bir uygulama.

Bu uygulamayı yaparken çeşitli github projelerinden ve blog yazılarından faydalandım.


















