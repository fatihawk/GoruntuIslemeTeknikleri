# Özellik Eşleştirme(Homography)

Özellik eşleme, mükemmel eşleşmenin gerekli olduğu şablon eşleştirmenin(template matching) biraz daha etkileyici bir sürümü olacak.

Bulmayı umduğumuz resimle başlıyoruz ve sonra bu resmi başka bir resim içinde arayabiliyoruz. Buradaki fark yaratıcı kısım, görüntünün aynı ışıklandırma, açı, dönüş vb. olması gerekmez. Özelliklerin sadece eşleşmesi gerekiyor.

Başlamak için bazı örnek resimlere ihtiyacımız var. Bizim "şablon" veya resmimizle eşleşmeye çalışacağız:

Burada, şablon resmimiz, şablonda arayacağımız resimden biraz daha küçük. Aynı zamanda farklı bir rotasyon ve bazı farklı gölgeler yok ama eğer bu özelliklere sahip başka görseller olursa daha iyi sonuçlar alabiliriz.

Bu uygulamada bir ""brute force" eşleştirme şekli kullanacağız. Her iki resimdeki tüm özellikleri bulacağız. Sonra bu özellikleri eşleştiriyoruz. Daha sonra istediğimiz kadar çekip çıkarabiliriz. Yine de dikkatli olmakta fayda var çünkü 500 eşleşme söylersek, birçok yanlış elde edebiliriz.

Burada eşleştirme işlemini OpenCV'nin "cv2.drawMatches()"fonksiyonunu kullanarak gerçekleştirdim.

![alt text](https://github.com/fatihawk/GoruntuIslemeTeknikleri/blob/master/%C3%96zellik%20E%C5%9Fle%C5%9Ftirme(Homography)/Sonuc.png)
