---
layout: post
title: Düzenli, Hızlı Gist Yönetimi - gistpaste
category: github
tags: gistpaste
---

Paketleri yüklüyelim :
	
	wget http://github.com/dblevins/gistpaste/raw/master/gistpaste 
	chmod 755 gistpaste 
	sudo mv gistpaste /usr/local/bin/

Gistleri düzenli depo etmek için dizin oluşturuyoruz ve içine giriyoruz :

	mkdir ~/gist
	cd ~/gist

bütün gistlerimizi `gist` dizininin altında depolayacağız. Daha sonra yeni gist dizini oluşturuyoruz ve içine giriyoruz :  

	mkdir new
	cd new

new dizini altında dosyalarımızı koyuyoruz daha sonra tüm dosyaları yolluyoruz :

	gistpaste *

(Dikkat! `.` ile başlayan   veya `.pyc` `.swp` dosyalarını eklemeden önce silmeyi unutmayın.) Yolladıktan sonra size
	
	  http://gist.github.com/123456
	  
tarzında bir numara dönecek, eski new dizinimizi silelim ve yeni gist'mizi clone edelim.
 
	  sudo rm -rf new
	  git@gist.github.com:123456

Bu şekilde çalışmanın avantajı ise tek hamlede add, push yapması.
