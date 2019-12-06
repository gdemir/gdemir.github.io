---
layout: post
title: Freebsd'de 'Was Not Properly Dismounted' Hatası
category: linux
tags: error freebsd fsck
---

Freebsd üzerinde geçenlerde şöyle bir hata ile karşılaştım. Hata öncesi

        /tmp was not properly dismounted
        /usr was not properly dismounted

tarzı uyarılar veriyordu. Bunun manası harddisk'i okuyamaz hale gelmiş olmasıdır. Sonrasında da;

        Enter full pathname of shell or RETRUN for/bin/sh:

gibi bir satırda takılı kalıyordu. Çözüm yolu ise şu şekilde. Öncelikle; `Enter` basıp prompt'a düşün. Sizi "**#**" şeklinde bir prompt karşılayacak. Sonrasında;

        fsck -y

yazın ve 5 aşamalı işlem bittikten sonra

        ***** FILE SYSTEM MARKED CLEAN *****
        ***** FILE SYSTEM WAS MODIFIED *****

yazısı çıkacaktır. Sisteme tekrardan power off-on yaparsanız (ki reset makinalarda çalışan process'leri durdurmuyor, tavsiye etmiyoruz) makinanız eski hale dönecektir.

NOT: Genelde bu problemler makinanın enerjisinin fiş yoluyla çekilmesi veya reset tuşuna basılması ile kaynaklıdır.
