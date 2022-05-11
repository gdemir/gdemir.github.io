---
layout: post
title: Wordpress Kurulumu
category: linux
tags: wordpress nginx mysql
---

### Kurulum

Wordpress indirmek için aşağıdaki linkten istediğimiz versiyonları seçiyoruz:

	https://wordpress.org/download/release-archive/

### Wordpress için MySQL kullanıcı ve şifre yaratma

Veritabanını daha önceden kurduğumuz MySQL üzerinden yaratacağız. MySQL girişi için

	mysql -u root -p

Terminal size daha önceden belirlediğiniz şifreyi soracaktır. Şifreyi girip devam edelim. Giriş yaptıktan sonra wordpress adında bir veritabanı oluşturalım: (Veritabanı adını (wordpress), kullanıcı adını (wordpressuser) ve şifreyi (password) istediğiniz gibi değiştirebilirsiniz)

	CREATE DATABASE wordpress;

Kullanıcı adı oluşturmak için:

	CREATE USER wordpressuser@localhost;

Yeni kullanıcıya şifre koymak için:

	SET PASSWORD FOR wordpressuser@localhost= PASSWORD("password");

Son olarak kullanıcıya veritabanı üzerindeki tüm izinleri verelim:

	GRANT ALL PRIVILEGES ON wordpress.* TO wordpressuser@localhost IDENTIFIED BY 'password';

### Wordpress Yapılandırma Ayarları

WordPress’in `wp-config-sample.php` dosyasının `wp-config.php` adında kopyasını yaratıp içinde ayarlamamız gereken satırları düzenleyelim.

	cp ~/wordpress/wp-config-sample.php ~/wordpress/wp-config.php

	sudo EDITOR ~/wordpress/wp-config.php

Aşağıdaki satırlarda veritabanı ismini, kullanıcı adı ve şifresini bulup yukarıda belirlediklerinizle değiştirin:

	// ** MySQL settings - You can get this info from your web host ** //
	/** The name of the database for WordPress */
	define('DB_NAME', 'wordpress');

	/** MySQL database username */
	define('DB_USER', 'wordpressuser');

	/** MySQL database password */
	define('DB_PASSWORD', 'password');

Kaydedip kapatın.

### Web Klasörüne Kopyalamak

WordPress dosyalarını yeni klasöre kopyalayalım.

	sudo cp -r ~/wordpress/* /var/www/html/

### Nginx Sunucu Yapılandırma

WordPress için bir sanal sunucu yaratalım. Bunun için varsayılan nginx ayar dosyasını kopyalayacağız.

	sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/wordpress

WordPress ayar dosyasını açalım:

	sudo EDITOR /etc/nginx/sites-available/wordpress

Dosya içerisini aşağıdaki dosyayı yapıştıralım:

	server {
	    listen 80;

	    root /var/www/html/;
	    index index.php index.html;
	    server_name example.com www.example.com;

	    location / {
	      try_files $uri $uri/ /index.php?q=$request_uri;
	    }

	    error_page 404 /404.html;
	    error_page 500 502 503 504 /50x.html;
	    location = /50x.html {
	    root /usr/share/nginx/www;
	    }

	    location ~ .php$ {
	      try_files $uri = 404;
	      fastcgi_pass 127.0.0.1:9000;
	      fastcgi_index index.php;
	      fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
	      include fastcgi_params;
	    }
	}

veya aşağıdaki satırdan indirebilirsiniz:

		wget https://gdemir.github.io/file/nginx-wordpress

Ayarlar mevcut(`available`) olmasına rağmen henüz sitemiz nginx sunucusunda aktif(`enabled`) olarak gözükmüyor. Bunun için aşağıdaki kodu çalıştıralım:

		sudo ln -s /etc/nginx/sites-available/wordpress /etc/nginx/sites-enabled/wordpress

Ayrıca varsayılan bloğu silmek için:

	sudo rm /etc/nginx/sites-enabled/default

`php7.0-mysql` paketini yükleyelim.

		sudo apt-get install php7.0-mysql

Son olarak servisleri tekrar başlatalım:

		sudo service nginx restart

### Kaynak

- [https://huse.in/123/wordpress-kurulumu](https://huse.in/123/wordpress-kurulumu)
