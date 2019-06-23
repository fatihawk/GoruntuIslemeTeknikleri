Özellik Eþleþtirme(Homography)

Özellik eþleme, mükemmel eþleþmenin gerekli olduðu þablon eþleþtirmenin(template matching) biraz daha etkileyici bir sürümü olacak.

Bulmayý umduðumuz resimle baþlýyoruz ve sonra bu resmi baþka bir resim içinde arayabiliyoruz. Buradaki fark yaratýcý kýsým, görüntünün ayný ýþýklandýrma, açý, dönüþ vb. olmasý gerekmez. Özelliklerin sadece eþleþmesi gerekiyor.

Baþlamak için bazý örnek resimlere ihtiyacýmýz var. Bizim "þablon" veya resmimizle eþleþmeye çalýþacaðýz:

Burada, þablon resmimiz, þablonda arayacaðýmýz resimden biraz daha küçük. Ayný zamanda farklý bir rotasyon ve bazý farklý gölgeler yok ama eðer bu özelliklere sahip baþka görseller olursa daha iyi sonuçlar alabiliriz.

Bu uygulamada bir ""brute force" eþleþtirme þekli kullanacaðýz. Her iki resimdeki tüm özellikleri bulacaðýz. Sonra bu özellikleri eþleþtiriyoruz. Daha sonra istediðimiz kadar çekip çýkarabiliriz. Yine de dikkatli olmakta fayda var çünkü 500 eþleþme söylersek, birçok yanlýþ elde edebiliriz.

Burada eþleþtirme iþlemini "cv2.drawMatches()"fonksiyonunu kullanarak gerçekleþtirdim.
