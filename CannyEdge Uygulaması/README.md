CannyEdge Uygulamasý

Canny kenar dedektörü, görüntülerdeki çok çeþitli kenarlarý algýlamak için çok aþamalý bir algoritma kullanan bir kenar algýlama operatörüdür.

Bu algoritma 5 aþamadan oluþur.

1)Gürültü azaltma:Görüntünün arkasýnda yer alan matematik temelde türevlere dayandýðýndan, kenar algýlama sonuçlarý görüntü gürültüsüne karþý oldukça hassastýr.Görüntüdeki gürültüden kurtulmanýn bir yolu, Gauss bulanýklýðýný pürüzsüzleþtirmek için uygulamaktýr.

2)Gradyan hesaplamasý:Kenar algýlama operatörlerini kullanýp resmin gradyanýný hesaplayarak kenar yoðunluðunu ve yönünü algýlar.Kenarlar, piksellerin yoðunluðundaki deðiþime karþýlýk gelir. Bunu tespit etmenin en kolay yolu, bu yoðunluk deðiþimini vurgulayan filtreleri her iki yönde de uygulamaktýr.

3)Maksimum olmayan bastýrma iþlemi:Ýdeal olarak, son görüntünün ince kenarlarý olmalýdýr. Bu nedenle, kenarlarý inceltmek için maksimum olmayan baskýlama uygulamamýz gerekir.Prensip basittir: algoritma, gradyan yoðunluk matrisi üzerindeki tüm noktalardan geçer ve kenar yönlerinde maksimum deðeri olan pikselleri bulur.

4)Çift Threshold iþlemi:Çift eþik adýmý, 3 tür pikselin belirlenmesini amaçlamaktadýr: güçlü, zayýf ve konuyla ilgili olmayan.Güçlü pikseller yoðunluðu o kadar yüksek olan piksellerdir; son kenara katkýda bulunduklarýndan eminiz.Zayýf pikseller, yoðunluk deðeri olarak kabul edilmek için yeterli olmayan, ancak kenar algýlama için uygun olmadýðý düþünülebilecek kadar küçük olmayan bir yoðunluk deðerine sahip piksellerdir.Diðer pikseller kenar için uygun deðildir.

5)Histeresiz ile Kenar Takibi:Eþik sonuçlarýna dayanarak, histerezis, zayýf pikselleri güçlü olanlara dönüþtürmekten ibarettir.

Ben bu uygulamada ayný þekilde OpenCV kütüphanesi yardýmýyla "cv2.Canny()"fonksiyonunu kullanarak alýnan canlý görüntü üzerinde bir kenar belirleme uygulamasý yaptým.