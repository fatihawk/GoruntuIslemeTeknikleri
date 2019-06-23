# Görüntü üzerinde MOG filtresinin uygulanması

Gaussianların Karışımı( Mixture of Gaussians=MOG), statik kameralardan hareketli cisimleri saptamak için arkaplan modellemesi için yaygın olarak kullanılan bir yaklaşımdır.

Ben de OpenCV destekli "createBackgroundSubtractorMOG2()"fonksiyonu yardımıyla alınan bir görüntü üzerindeki hareketli nesneleri tespit etmek için kullanılan filtreleme işlemini yaptım.

NOT:Eğer alınan bir görüntü üzerinde bu işlemi yapmak istiyorsanız,elinizdeki bu görüntüleri proje dosyasına atmalısınız.

Test1:Video içinde seçilmiş orijinal video görüntüsü.
![alt text](https://github.com/fatihawk/GoruntuIslemeTeknikleri/blob/master/G%C3%B6r%C3%BCnt%C3%BC%20%C3%BCzerinde%20MOG%20filtresinin%20uygulanmas%C4%B1/Test1.png)


Test2:MOG uygulanmış video görüntüsü.
![alt text](https://github.com/fatihawk/GoruntuIslemeTeknikleri/blob/master/G%C3%B6r%C3%BCnt%C3%BC%20%C3%BCzerinde%20MOG%20filtresinin%20uygulanmas%C4%B1/Test2.png)

