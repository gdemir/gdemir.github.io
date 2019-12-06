---
layout: post
title: Bootstrap Responsive Tasarım
category: bootstrap
tags: [responsive, navbar]
---

Bootstrap `navbar` gibi css bileşenleriyle; tarayıcı, tablet, mobil gibi cihazların ekran çözünürlüğüne duyarlı(ekran çözünürlüğüne göre yeniden şekillenen) görünüm sunmaktadır. Bunu sitenize sadece `bootstrap-css`, `bootstrap-js` dosyalarını ekleyerek ve `navbar` gibi bileşenleri kullanarak duyarlı hale getiremezsiniz. Bunun için ek olarak aşağıdaki `meta` etiketini `head` etiketleri arasına eklemeniz gerekiyor.

	<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">

Bu `meta` etiketini açıklayacak olursak,

`width=device-width`: Cihazın ekran genişliğini elde ediyoruz.

`initial-scale`: Sayfa açıldığında ne kadar zoom yapılacağını belirliyoruz. Mesela 1 diyerek gerçek boyut elde ediliyor.

`maximum-scale`: Kullanıcın sayfayı ne kadar zoom yapabileceğini ayarlıyor.

`user-scalable=no`: Kullanıcının sayfada zoom yapmasını engelliyorsunuz.

Not: Bu sitedeki header ve footer'da birer `navbar`dır ve responsive çalışmaktadır :-)

#### Kaynak
---

- [http://getbootstrap.com/css/#overview-mobile](http://getbootstrap.com/css/#overview-mobile)

- [http://getbootstrap.com/components/#navbar](http://getbootstrap.com/components/#navbar)

- [http://mhmtyylc.com/responsive-tasarim-nedir](http://mhmtyylc.com/responsive-tasarim-nedir)
