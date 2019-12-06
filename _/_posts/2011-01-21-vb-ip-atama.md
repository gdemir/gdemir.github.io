---
layout: post
title: Virtualbox'a Ip Atama
category: network
tags: virtualbox
---

Bilgisayarınızdaki bir sanal makinayı, ana makina ile ağ kurmasını sağlamak istiyorsanız şu adımları izleyin :

- hangi sanal makina'da bu ayarı uygulayacaksanız, o **sanal makineyi** seçiyoruz :

![virtualboxs](http://gdemir.github.io/file/vb.png)

- virtualbox'ın üstteki menüsünden **ayarlar** kısmını seçiyoruz :

![menu](http://gdemir.github.io/file/vb-menu.png)

- ayarlarda çıkan menüden, **ağ** bölümünü seçiyoruz :

![ag](http://gdemir.github.io/file/vb-ag.png)

- bağdastırıcı-1 de sanal bağdaştırıcının ana bilgisayara bağlanma tipini **bridged adapter** olarak seçiyoruz : (ana makina gibi 192.168.x.x gibi bir ip alsın diye) ve internete çıkarmak için ana bilgisayar net'e nasıl bağlı ise o bağlanma ismini seçin : (ör. eth0, wlan0, usb0)

![bagdas-1](http://gdemir.github.io/file/vb-bagdas1.png)

Ayrıca ek bilgi olarak, bilgisayarınıza veya sanal makinanıza seçtiginiz bir ip'yi atamak istiyorsanız.

Kablolu için:

	sudo ifconfig eth0 192.168.1.19

Kablosuz için:

	sudo ifconfig wlan0 192.168.1.19

şeklinde atayabiliyorsunuz.
