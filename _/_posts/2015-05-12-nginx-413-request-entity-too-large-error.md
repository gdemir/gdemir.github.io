---
layout: post
title: Nginx '413 Reuqest Entity Too Large' Hatası
category: nginx
tags: error
---

Resim yüklerken çok yüksek `MB`lı resimlerde bu hatayı alıyordum. Sorunun çözümü için `/etc/nginx/sites-available/default` dosyasının içine aşağıdaki satırı yazmak yeterli olacaktır.

	client_max_body_size    100m;

#### Kaynak

[413 Reuqest Entity Too Large](http://makaleci.com/nginx-upload-limiti-sorununa-cozum-413-request-entity-too-large.html)
