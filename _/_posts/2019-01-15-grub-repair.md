---
layout: post
title: Grub Önyükleyicisini Onarmak
category: linux
tags: boot repair grub bootable yannubuntu
---

Çoğunlukla Windows yanına bir Linux işletim sistemi kullanılırken Windows’u bir sebepten dolayı yeniden kurulmasında çıkmaktadır. Windows tekrardan kurulduktan sonra Linux'a erşim sağlayamamaktadır. Çünkü Windows kurulurken Linux'un kurmuş olduğu önyükleyicisini silip kendi önyükleyicisini kurmakta ve bu önyükleyicide sadece Windows'u görmektedir. Ancak Linux önyükleyicileri Windows ve Linux'u görmektedir. Buradaki önyükleyicisini onarmak yani Linux önyükleyicisini tekrardan kurmak için aşağıdaki adımları izleyebilirsiniz.

#### Bootable Linux ISO'sunu Yazdırma

Hangi Linux kurulumunu gerçekleştirecekseniz o  işletim sisteminin (mesela bir Ubuntu Desktop) iso'sunu indirin bunu CD/DVD ya da bootable(ilklendirilebilir) USB'ye yazdırın. Linux'u Bootable USB'ye yazmak için için [www.pendrivelinux.com](https://www.pendrivelinux.com/universal-usb-installer-easy-as-1-2-3/) kullanabilirsiniz.

#### Bootable Linux'u Başlatma

CD/DVD ya da USB'yi bilgisayarınıza bağlayın ve başlatın. Linux'u kurumadan başlatmak için ekrana gelen menüde "Try Ubuntu Without Installing" (Kurulumu gerçekleştirmeden Ubuntu'yu dene) gibi bir seçenek varsa bunu seçerek başlatın.

#### Boot-Repair Kurulumu

Terminal Açalım (`Ctrl+Alt+T`) ve terminalde şu komutu ile depoyu koyarak paket yöneticisine bu paketi görmesini sağlayarak ekleyelim:

    sudo add-apt-repository ppa:yannubuntu/boot-repair

Paket yöneticisinde paket listemizi güncelleyelim:

    sudo apt-get update

Boot Repair programını kuralım:

    sudo apt-get install -y boot-repair && boot-repair

Program yönetici (root) parolanızı soracak. Grubu tekrar yüklemek ve ya onarmak için “Önerilen Onarım” (“Recommended repair”) seçeğine tıklamanız yeterli olacaktır. Boot-Repair önyükleyiciyi harddiskte kuracağı yeri kendisi otomatik olarak göremezse bunun neresi olacağını sizin yönlendirmeniz gerekecektir. Burada dikkatli olunması Windows(NTFS/FAT) veya Linux(EXT4) gibi yerlere değil, silinmemiş ise Windows önyükleyicisinin olduğu yere veya boş bir harddisk bölümüne kaydetmeniz gerekmektedir.

