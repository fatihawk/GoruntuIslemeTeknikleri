
Threshold Uygulamasý

Giriþ olarak verilen görüntüyü ikili görüntüye çevirmek için kullanýlan bir yöntemdir.

Ýkili görüntü (binary), görüntünün siyah ve beyaz olarak tanýmlanmasýdýr.

Morfolojik operatörler gibi görüntü üzerindeki gürültüleri azaltmak veya nesne belirlemek gibi farklý amaçlar için kullanýlýr.

Giriþ olarak verilen görüntü üzerinde uygulanan thresholding tipine baðlý olarak, pikselleri verilen eþik deðerine göre siyah ya da beyaz olarak günceller.

Eðer piksel deðeri bir eþik deðerden büyükse, bir deðere (beyaz olabilir), baþka bir deðere (siyah olabilir) atanýr.

Kullanýlan iþlev cv2.threshold'dýr.

Ýlk argüman gri tonlamalý olmasý gereken kaynak görüntüsüdür.Yani uygulamaya baþlarken ilk yapýlan görseli gri tonlamalý görüntüye çevirmektir.

Ýkinci argüman, piksel deðerlerini sýnýflandýrmak için kullanýlan eþik deðeridir.

Üçüncü argüman, piksel deðeri eþik deðerden daha büyükse (bazen daha azsa) verilecek deðeri temsil eden maxVal'dir.

OpenCV farklý eþikleme stilleri saðlar ve fonksiyonun dördüncü parametresi tarafýndan karar verilir. 