
# Threshold Uygulaması

Giriş olarak verilen görüntüyü ikili görüntüye çevirmek için kullanılan bir yöntemdir.

İkili görüntü (binary), görüntünün siyah ve beyaz olarak tanımlanmasıdır.

Morfolojik operatörler gibi görüntü üzerindeki gürültüleri azaltmak veya nesne belirlemek gibi farklı amaçlar için kullanılır.

Giriş olarak verilen görüntü üzerinde uygulanan thresholding tipine bağlı olarak, pikselleri verilen eşik değerine göre siyah ya da beyaz olarak günceller.

Eğer piksel değeri bir eşik değerden büyükse, bir değere (beyaz olabilir), başka bir değere (siyah olabilir) atanır.

Kullanılan işlev cv2.threshold'dır.

İlk argüman gri tonlamalı olması gereken kaynak görüntüsüdür.Yani uygulamaya başlarken ilk yapılan görseli gri tonlamalı görüntüye çevirmektir.

İkinci argüman, piksel değerlerini sınıflandırmak için kullanılan eşik değeridir.

Üçüncü argüman, piksel değeri eşik değerden daha büyükse (bazen daha azsa) verilecek değeri temsil eden maxVal'dir.

OpenCV farklı eşikleme stilleri sağlar ve fonksiyonun dördüncü parametresi tarafından karar verilir. 
