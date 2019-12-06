---
layout: post
title: MySQL'e Giriş ve Bazı İşlemler
category: linux
tags: mysql automysqlbackup
---

#### MySQL Kurulumu

Paketleri kur:

	sudo apt-get install mysql-server mysql-client

Kurulumda bizden `mysql-server` için root şifresi istiyor, bunları girip kurulumu bitiriyoruz ve kurulum sonrası test ediyoruz.

	sudo ps aux | grep mysqld
	mysql  3799 0.5 3.6 145392 18484 ?     Ssl 10:42 0:00 /usr/sbin/mysqld
	hummer 3891 0.0 0.1   3208   808 pts/0 S+  10:43 0:00 grep --color=auto mysqld

#### MySQL'e Bağlanma ve db Oluşturma

	mysql -u <user ismi> <database ismi> -p

buradaki `-u` user, `-p` ise password sor manasında. İlk kez bağlanıyorsanız,

	mysql -u root  -p < "create database dbname;"

diyerek root olarak databese oluşturabilirsiniz.

#### MySQL'de Tablo Oluşturma

MySQL'e bağlı oldugumuzu düşünelim,

	CREATE TABLE kul (
	id int(11) NOT NULL auto%1Fincrement,
	ad varchar(20) NOT NULL default '',
	parola varchar(12) NOT NULL default '',
	PRIMARY KEY  (id)
	) TYPE=MyISAM;

diyerek kul isimli tablo olurmuş oluyoruz.

#### MySQL'den Veri Yedeğini Alma ve MySQL'e Yedeği Aktarma (manual)

Konsoldan,

	mysqldump -u <user ismi> <database ismi> -p > yedek.sql

komutuyla &lt;user ismi&gt;li kullanıcı &lt;database ismi&gt;li db'i `yedek.sql` olarak üretir.
Veya,

	mysql -u <user ismi> <database ismi> -p < yedek.sql

diyerek `yedek.sql` ile `MySQL`e aktarır.

#### MySQL'den Otomatik Veri Yedeği Alma (auto)

sudo apt-get install automysqlbackup

ve şu şekilde çalıştırıyoruz. Konsoldan, bir kereliğine

automysqlbackup

diyerek çalıştırıyoruz. Veri yedeklerimizi de şu dizin altından görüntüleyebiliyoruz :

	ls /var/lib/automysqlbackup/

burada günlük, aylık, yıllık olarak otamatikmen kaydoluyor.

#### MySQL'de Hata Akışına Bakma

Konsoldan,

	tail -f /var/log/nginx/error.log

diyerek arkadaşınızın önerilerini dinleyebilirsiniz :-)
