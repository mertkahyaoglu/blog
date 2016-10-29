---
title: 'NPM''e büyük rakip: Facebook''tan Yarn'
layout: post
---

<img src="/blog/img/posts/yarn-banner.png" style="float:left;width:250px;" data-action="zoom"/>
[Yarn](https://yarnpkg.com/), geçtiğimiz günlerde Facebook'un  open source olarak yayınladığı  yeni Javascript paket yöneticisi (package, dependency manager). Yarn, open source edilmesiyle beraber büyük bir ilgi gördü ve ilk haftada [Github](https://github.com/yarnpkg/yarn) üzerinde 10.000 yıldız almayı başardı. Bu yazıda neden Yarn'ın bu kadar ilgi gördüğünden ve NPM'e artı olarak sunduğu özelliklerden bahsedeceğim. Belki sizde NPM'i bırakıp benim gibi Yarn kullanmaya başlayabilirsiniz. :smiley:

Facebook, Yarn'ı yayınlarken vurguladığı 2 önemli özellik var. **Hızlı** ve **güvenilir** olması. Ben bu yazıda sadece hız konusu ele alacağım. NPM ile hız karşılaştırması yapıp ne kadar hızlı olup olmadığını göreceğiz.

Yarn'ın diğer özellikleri;

* **Offline mode**: Daha önce yüklemiş olduğunuz bir paketi, internetiniz olmadığı zamanlarda tekrar kullanabiliyorsunuz. (global cache)

* **Deterministic**: Yüklediğiniz dependency'ler (paketler), hangi makinada olursanız olun sırası farketmeden aynı şekilde yükleniyor (yarn.lock dosyası aracılığı ile).

* **Network Resilience**: Yüklediğiniz herhangi bir pakette hata oluştuğunda, bu hata diğer paketlerin indirilmesini etkilemiyor. Hatalı  paketler daha sonra tekrar isteniyor.

* En önemli özellik => **Daha fazla emoji**. Console ekranında artık daha fazla emoji görebilirsiniz :scream:

## Nasıl yükleriz?

En kolay yolları sırasıyla;

{% highlight shell %}

curl -o- -L https://yarnpkg.com/install.sh | bash

{% endhighlight %}

ya da `npm` ile :grin:

{% highlight shell %}

npm install -g yarn

{% endhighlight %}


## Kullanımı

Kullanımı npm ile oldukça benzer;

{% highlight shell %}
yarn                        # package.json'daki tüm paketleri yükle
yarn install                # yarn alternatifi
yarn init                   # npm reposu başlat (package.json oluşturma)
yarn add [package]          # npm paketi yükle
yarn upgrade [package]      # npm paketi güncelleme
yarn remove [package]       # npm paketi silme
{% endhighlight %}


## Hız Testi
Yarn'ın en önemli özelliğide hızı. Birçok geliştiricinin Yarn'a geçme sebebi de bu olsa gerek. Bakalım Yarn ne kadar hızlı..

Hız testini Jekyll Admin projem üzerinden yaptım. Ne kadar modül yüklü olduğunu [burdan](https://github.com/jekyll/jekyll-admin/blob/master/package.json) görebilirsiniz.

**npm sonucu**

{% highlight bash %}
rm -rf node_modules
npm cache clean
time npm i
..
real	6m43.163s
{% endhighlight %}

**yarn sonucu**

{% highlight bash %}
rm -rf node_modules yarn.lock
npm cache clean
time yarn
..
real	1m3.919s
{% endhighlight %}

### Sonuç

Sonuç, testi yaptığım projeyi geliştirirken keşke yarn olsaydı dedirttiren cinsten. Modüller yarn ile neredeyse 6 kat daha hızlı yüklenmiş. Hele Travis gibi CI toolları kullanıyorsanız projenizin build time'ı oldukça düşüyor ve her bir feature için daha az bekliyorsunuz.

Yarn'ın bir anda bu kadar popüler olması, yukarıda bahsettiğim özelliklerin dışında, arkasında Facebook gibi büyük bir şirketin olması. İşin içinde Facebook olunca arkasındaki community de oldukça büyük oluyor. Bu sayede de ortaya çıkan ürünler muazzam bir destek alıyor ve bizler de iyi bir yazılımın keyfini sürebiliyoruz.

Facebook ekibine, bizi npm tekelinde bırakmadığı ve daha hızlı bir paket yöneticisi sağladığı için teşekkürlerimi sunuyorum.
