# Görüntü üzerinde MOG filtresinin uygulanması

Gaussianların Karışımı( Mixture of Gaussians=MOG), statik kameralardan hareketli cisimleri saptamak için arkaplan modellemesi için yaygın olarak kullanılan bir yaklaşımdır.

Ben de OpenCV destekli "createBackgroundSubtractorMOG2()"fonksiyonu yardımıyla alınan bir görüntü üzerindeki hareketli nesneleri tespit etmek için kullanılan filtreleme işlemini yaptım.

NOT:Eğer alınan bir görüntü üzerinde bu işlemi yapmak istiyorsanız,elinizdeki bu görüntüleri proje dosyasına atmalısınız.

Test1:Video içinde seçilmiş orijinal video görüntüsü.
Test2:MOG uygulanmış video görüntüsü.
