Template Matching Uygulamasý

Buradaki fikir, saðladýðýmýz þablonla eþleþen ve belirli bir eþik deðeri veren bir görüntünün ayný bölgelerini bulmaktýr.

Kesin nesne eþleþmeleri için, tam aydýnlatma / ölçek / açý ile, bu sistem daha verimli çalýþabilir. 

Bu koþullarýn genellikle karþýlandýðý bir örnek, bilgisayardaki herhangi bir GUI ile ilgilidir. Düðmeler ve benzeri öðeler her zaman aynýdýr, böylece þablon eþleþtirmesini kullanabiliriz.

Baþlamak için bir ana görüntüye ve bir þablona ihtiyacýmýz olacak. Þablonunuzu, görüntüde tam olarak aradýðýnýz "þey" den almalýyýz.

Ben bu uygulamada ayný giriþlere sahip bir PC görseli aldým.

Burada önemli olan eþleþtirmek istediðimiz nesnenin þablonda birden fazla ve ayný þekilde yer almasý.

Ben bu uygulamada OpenCV'nin "cv2.matchTemplate()" fonksiyonunu kullanarak eþleþtirme yaptým.

Burada Threshold deðerini deðiþtirerek eþleþme doðruluðunu kontrol edebiliriz.