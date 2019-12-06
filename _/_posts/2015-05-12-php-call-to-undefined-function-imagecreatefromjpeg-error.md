---
layout: post
title: Php Call To Undefined Function Imagecreatefromjpeg Hatası
category: php
tags: error
---

Php projemde  `Imagecreatefromjpeg()` fonksiyonunu kullanırken bu hatayı alıyordum çözümü için aşağıdaki paketi kurmak yeterlidir.

	sudo apt-get install php5-gd

#### Kaynak

[imagecreatefromjpeg and similar functions are not working in PHP](http://stackoverflow.com/questions/13338339/imagecreatefromjpeg-and-similar-functions-are-not-working-in-php)