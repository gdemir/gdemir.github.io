---
layout: post
title: SSH Kimlik Taşıma ve Kullanımı
category: linux
tags: ssh
---

#### Kurulum

local bilgisayarımıza kuruyoruz.

	sudo apt-get install ssh

#### Kullanım

Örneğin sanal makinamız olsun. Sanal makina kullanıcı ismi `f3` olsun şu şekilde bağlanılır.

	ssh f3@192.168.1.1

#### Kimlik taşıma

`ssh -A` bunun farkı sizin kendi bilgisayarınızdaki `~/ssh/id_rsa.pub` dosyayı bağlanılan bilgisayara taşıyıp, bağlandıgınız bilgisayarı kendi bilgisayarınız gibi kullanmaktır. Yani, localdeki kendi kimliğinizi taşımaya sağlar.

	ssh -A f3@192.168.1.1

#### Kimlik kullanımı

Kendi kimligimizi taşıyıp (`ssh -A`) `github clone` veya bunun benzeri işler yapacaksak  

	sudo -E git <islem> (Ör. sudo -E git clone git@github.com:gdemir/gdemir.github.com.git)

`-E` konmazsa kimliğinizi tanımayıp fatal hatası verecektir

