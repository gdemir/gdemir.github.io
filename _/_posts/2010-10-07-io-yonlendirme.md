---
layout: post
title: Standart i/o İşlemlerinin Yönlendirilmesi
category: linux
tags: i/o
---

#### Standart i/o İşlemleri

Unix'ta programlar ve dosyalar, i/o işlemleri yönünden;  

	  0 : stdout (çıktı almak için)  
	  1 : stdin  (girdi girmek için)  
	  2 : stderr (hataları görüntülemek için)  

olmak üzere 3 akıntı yoluna sahiptir.  
Bu 3 işlem programın veya dosyanın temel işlemleridir.  

#### Standart i/o İşlemlerinin Yönlendirilmesi

Bazen programların veya dosyaların; hatalarını, çıktılarını, girdilerini  
başka yerlere yönlendirerek,  işleyişini incelemek isteriz.  
Örneğin, bir program da hataları bir dosyaya yönlendirmek istersek :  

	program_adı 2>dosya_adı

şeklinde kullanıyoruz. Bir `c` kodunda,  

	fprintf(stderr, "Hata : kaynak bulunamadı");  
	     
ifadesi çalıştığında, hatalar ekranda görüntülenmez, bunun yerine `dosya_adı` isimli dosyaya yazılır. Eğer hataları ekranda görmek istiyorsak çıktıya yönlendirmemiz gerekiyor, bunun için :

	program_adı 2>&1

hataları çıktı olarak yönlendiririz. Eğer programın çıktıları yönlendirmek istiyorsak

	program_adı 1>dosya_adı

veya 

	program_adı >dosya_adı

diyerekte kullanabiliriz. Yani default değeri 1 olarak kendisi atıyor.
