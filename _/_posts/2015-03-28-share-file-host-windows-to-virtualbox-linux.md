---
layout: post
title: Windowstan Linux Sanal Makineye Dosya Paylaşımı
category: network
tags: virtualbox share
---

#### VirtualBox'a Paylaşılacak Dosyayı Ekleme
`Devices > Shared Folder Settings (Aygıtlar > Paylaşılan Klasör Ayarları)` kısmına tıklıyoruz

![share-file-option](/file/virtualbox-share-file-option.png)

Paylaşılacak yeni dosya ekliyoruz

![share-file-add](/file/network/share-file-add.png)

Paylaşılacak dosyanın ayarlarını `otomatik bağla` ve `kalıcı yap` diyoruz

![share-file-add-option](/file/virtualbox-share-file-add-option.png)

#### VirtualBox'a Misafir Eklentilerinin Kurulması

VirtualBox'ta Linux sanal makineler için eklentilerin kurulması gerekiyor.

Ubuntu için

	sudo apt-get install build-essential linux-headers-generic

Debian için

	sudo apt-get install build-essential linux-headers-{amd64 OR 686-pae OR 486}

`Devices > Install Guest Additions` (`Aygıtlar > Misafir Eklentileri CD kalıbını ekle`) kısmına tıklayarak CD kalıbımızı ekliyoruz.

![install-guest-additions](/file/virtualbox-install-guest-additions.png)

Eğer yukarıdaki adımda aşağıdaki gibi `could not mount the media/drive '/usr/share/virtualbox/vboxguestadditions.iso'` hatası alıyorsanız, Manuel olarak komutlarla kurmak için şu sayfayı okuyun: [setup-manual-vboxguestadditions/](/category/network/setup-manual-vboxguestadditions/)

![install-guest-additions-error](/file/virtualbox-install-guest-additions-error.png)

Eklediğimiz `VBoxGuestAdditions.iso` dosyası sorunsuz yüklendiğini kontrol etmek için
`CD/DVD Devices > VBoxGuestAddtions.iso` (`CD/DVD Aygıtlar > VBoxGuestAddtions.iso`) kısmına bakıyoruz.

![install-guest-additions-check](/file/virtualbox-install-guest-additions-check.png)

Aynı şekilde eklenen eklentiler `/media/cdrom` dizini altında gözükecektir.

#### Paylaşılan Dosyanın/Dizinin VirtualBox'a Alınması

Paylaşılan dizinini/dosyanın aynı adında bir dizin oluşturup Virtual Machine (Sanal Makina)da dahil ediyoruz

	sudo mkdir /media/SHARE_FILE
	sudo mount -t vboxsf SHARE_FILE	/media/SHARE_FILE

Hepsi bu kadar, umarım yardımı olur.


### Kaynaklar

- [Linux Guest Additions Kurulumu](https://forums.virtualbox.org/viewtopic.php?t=15679)

<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/BSg-_3OFlrQ"></iframe>
</div>
