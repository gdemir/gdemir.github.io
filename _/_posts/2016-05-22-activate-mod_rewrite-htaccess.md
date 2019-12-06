---
layout: post
title: Apache .htaccess Dosyasında mod_rewrite Modülünü Aktif Yapma
category: apache
tags: htaccess mod_rewrite
---

`mod_rewrite` modülünü aktif yapıyoruz:

	sudo a2enmod rewrite

`apache` servisini tekrar başlatıyoruz:

	sudo service apache2 restart

#### Kaynak

- [http://stackoverflow.com/questions/24743674/htaccess-file-not-working-on-ubuntu-14-04-with-apache2](http://stackoverflow.com/questions/24743674/htaccess-file-not-working-on-ubuntu-14-04-with-apache2)

- [https://www.digitalocean.com/community/tutorials/how-to-set-up-mod_rewrite-for-apache-on-ubuntu-14-04](https://www.digitalocean.com/community/tutorials/how-to-set-up-mod_rewrite-for-apache-on-ubuntu-14-04)