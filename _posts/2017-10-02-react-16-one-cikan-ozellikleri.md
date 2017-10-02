---
title: React 16 Öne Çıkan Özellikleri
---

Bu yazıda uzunca süredir beklenen yeni React 16 (Kod Adı "Fiber") versiyonunun öne çıkan özelliklerinden kısaca bahsedeceğim. Listelemek gerekirse;

* Baştan yazılan yeni bir çekirdek mimari
* Daha performanslı SSR (Server-side rendering)
* Custom DOM attribute desteği (Artık `data-foo="42"` gibi attributeleri hata almadan yazabileceğiz)
* `render` methodunda Array ve String döndürme desteği
* Hata yakalama
* Portallar

Benim örnek vermek istediğim son 3 madde olacak. Çünkü bu 3 madde gerçektente hayat kurtaracak derece önemli. Hemen örneklere geçiyorum.
# `render` methodunda Array ve String döndürme
Çoğumuzun başına gelmiştir. Bir component'te birden fazla element döndürmeye kalkarız ve React bize bir hata mesajı verir. Biz de o elementleri bir `div` içerisine alır devam ederiz. Artık bunu yapmamıza gerek kalmayacak. Benim en çok hoşuma giden özellik bu oldu. Artık daha sade bir DOM yapısı oluşuturabileceğiz.

<script src="https://gist.github.com/mertkahyaoglu/2d28e482618a0b723282573735fbf2db.js"></script>

Burada dikkat etmemiz gereken tek şey her bir array elemanına  `key` değeri vermemiz olacak.

Diğer bir güzel özellik ise artık `render` methodunda stringleri span içerisine almadan direk olarak döndürebileceğiz.

<script src="https://gist.github.com/mertkahyaoglu/9aac921368ecac8ab6d8b7c8ab7856c6.js"></script>

# Hata yakalama
Artık React componentlerimizde herhangi bir nedenle hata aldığımızda `componentDidCatch`  methodu ile bu hatayı yakalayıp önlemler alabileceğiz. 

<script src="https://gist.github.com/mertkahyaoglu/a28f2ade37d72f747529bbdc537c0ba2.js"></script>

Burada basit bir sayaç örneğimiz var. 5'e kadar sayıldığında bir hata fırlatıyor. Bu hatayı parent component'te yakalayıp, ona göre bir mesaj gösteriyoruz. Gerçek hayata dair örnek vermek gerekirse, başarısızlıkla sonuçlanan ve hata fırlatın bir GET request'i sonrası kullanıcılara hata mesajını güzel bir şekilde gösteren bir component sunabiliriz.

# Portallar
Portal ana React component'imizi mount ettiğimiz DOM elementinin dışında herhangi bir DOM elementinde render işlemi yapabilmemizi sağlayan güzel bir özellik.

<script src="https://gist.github.com/mertkahyaoglu/edad56982631a291af28b7548a9aa2db.js"></script>

Burada listeleme yapan ana componentimiz ilk 3 elemanı  `root`  id'li `div`'e mount olmuşken geri kalanları `root2` id'li `div`'e mount oldu. Bu gerçek hayatta nerede işimize yarar derseniz; overlay ya da modal kullanmamız gereken yerlerde bize büyük kolaylık sağlayabilir. Böylece mount olunan DOM elementi dışında modal veya overlay elementlerini `createPortal` ile tanımlayabiliriz.

Bu yazının olabildiğince kısa ve öz olmasını istedim. Umarım React 16'nın bu önemli özellikleri hakkında az çok bilgi verebilmişimdir. Herkes iyi geliştirmeler..