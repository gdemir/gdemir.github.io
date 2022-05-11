---
layout: post
title: Virtualbox'a Ip Atama
category: network
tags: virtualbox
---

Bilgisayarınızdaki bir sanal makinayı, ana makina ile ağ kurmasını sağlamak istiyorsanız şu adımları izleyin :

- Hangi sanal makina'da bu ayarı uygulayacaksanız, o **sanal makineyi** seçiyoruz :

![virtualboxs](/file/vb.png)

- Virtualbox'ın üstteki menüsünden **ayarlar** kısmını seçiyoruz :

![menu](/file/vb-menu.png)

- Ayarlarda çıkan menüden, **ağ** bölümünü seçiyoruz :

![ag](/file/vb-ag.png)

- Bağdastırıcı-1 de sanal bağdaştırıcının ana bilgisayara bağlanma tipini **bridged adapter** olarak seçiyoruz : (ana makina gibi 192.168.x.x gibi bir ip alsın diye) ve internete çıkarmak için ana bilgisayar net'e nasıl bağlı ise o bağlanma ismini seçin : (ör. eth0, wlan0, usb0)

![bagdas-1](/file/vb-bagdas1.png)

Ayrıca ek bilgi olarak, bilgisayarınıza veya sanal makinanıza seçtiginiz bir ip'yi atamak istiyorsanız.

Kablolu için:

	sudo ifconfig eth0 192.168.1.19

Kablosuz için:

	sudo ifconfig wlan0 192.168.1.19

şeklinde atayabiliyorsunuz.
