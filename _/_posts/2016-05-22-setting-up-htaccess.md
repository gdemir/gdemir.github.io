---
layout: post
title: Apache .htaccess Dosyasını Çalıştırma
category: apache
tags: htaccess
---

`apache` yapılandırma dosyasını açıyoruz:

	sudo $EDITOR /etc/apache2/apache2.conf

aşağıdaki satırının başında yorum satırı (`#`) var ise yorum satırı işaretini siliyoruz:

	AccessFileName .htaccess

aşağıdaki satırı bulup `AllowOverride None` kısmını `AllowOverride All` yapıyoruz:

	<Directory /var/www>
	        Options Indexes FollowSymLinks
	        AllowOverride All
	        Require all granted
	</Directory>

`.htaccess` dosyamızı oluşturuyoruz ve gerekli erişim izinlerini veriyoruz:

	sudo touch /var/www/html/.htaccess
	sudo chmod 644 /var/www/html/.htaccess