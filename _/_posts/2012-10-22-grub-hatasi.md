---
layout: post
title: Grub 'error&#58; no such partition grub rescue&#58;' Hatası
category: linux
tags: error grub
---

Bu hata genellikle linux işletim sistemlerini tekrar yüklerken ortaya çıkmaktadır. Çözümü kolaydır bunun için bootable CD veya USB ile bilgisayarı başlatın ve aşağıdaki adımları izleyin.

#### linux sürücüsünün tespiti

Öncelikle sürücülerde ne var bakmak gerekiyor.

	fdisk -l

Bu kaynaktan mesela ana diskin `/dev/sda` ve linux yüklü sürücünün de `/dev/sda6` olduğunu tespit ettik diyelim.

#### linux sürücünün bağlanması

Tespit ettiğimiz linux sürücüyü bilgisayara bağlıyalım.

	mkdir /media/sda6
	mount /dev/sda6 /media/sda6

#### grubun tekrar yüklenmesi

Grubu ana sürücüye tekrar yüklemek için.

	grub-install --root-directory=/media/sda6 /dev/sda

Not: Buradaki `/dev/sda6` ve `/dev/sda` değişebilir.
