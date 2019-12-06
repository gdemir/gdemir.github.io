---
layout: post
title: phpMyAdmin Kurulumu
category: php
tags: apache nginx lighttpd phpmyadmin
---

### phpMyAdmin Kurulumu

Paketi kuruyoruz:

	sudo apt-get install phpmyadmin

Kurulum sırasında kullanılacak web sunucuları soracaktır (Ör.: `apache2`, `lighttpd`), burada nginx üzerinde çalışıyorsanız rastgele birini seçebilirsiniz. Daha sonra phpMyAdmin'in veritabanı üzerinde yapılandırma yapıp yapmayacağı sorulacak buna hayır diyerek kurulumu sonlandırıyoruz, kurulum bitmiş oluyor.

Kurulu olan phpMyAdmin ile websitenin servis edildiği kök dizin arasında (`/var/www/html`) sembolik bir bağlantı oluşturuyoruz ki `http://localhost/phpmyadmin` şeklinde linke ulaşabilelim:

	sudo ln -s /usr/share/phpmyadmin/ /var/www/html/
	
Var olan web sunucumuz olan Apache/Nginx/Lighttpd'i tekrar başlatıyoruz:

	sudo service [apache2|nginx|lighttpd] restart
