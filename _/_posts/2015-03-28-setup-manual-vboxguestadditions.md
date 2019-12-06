---
layout: post
title: Manuel VboxGuestAdditions Kurulumu
category: network
tags: virtualbox
---

Windows host makinenizdaki `VirtualBox` dizinin yerini saptayın. (`C:\Program Files\Oracle\VirtualBox` gibi)

`VirtualBox` dizinizi Önceki windows'tan VirtualBox Machine(Sanal Makina)ya dosya paylaşma girdisindeki gibi paylaşın. Paylaşım işlemini tamamlandıktan sonra `VirtualBox` dizininiz `/media/VirtualBox` path'inde var mı kontrol edin. Her şey tamamsa bizim için gerekli olan `VBoxGuestAdditions.iso` ISO dosyasını `/media` dizini altına kopyalayalım ve izinlerini ayarlıyalım.

	sudo cp -a /media/VirutalBox/VBoxGuestAdditions.iso /media/.
	sudo chmod 777 /media/VBoxGuestAdditions.iso

ISO dosyamız için bir dizin oluşturup sistemimize dahil edelim.

	sudo mkdir /media/GuestAdditionsISO
	sudo mount -o loop /media/VBoxGuestAdditions.iso /media/GuestAdditionsISO

çıkarılan ISO doyalarımızdan `VBoxLinuxAdditions.run` betiğini bulup çalıştıralım.

	cd /media/GuestAdditionsISO
	sudo ./VBoxLinuxAdditions.run

#### Kaynak

[Manuel VBoxGuestAdditions Kurulumu](http://askubuntu.com/questions/321589/unable-to-mount-the-cd-dvd-image-on-the-machine-sandbox?answertab=votes#tab-top)
