---
layout: post
title: Crontab Komutu ve Örnek Crontab Uygulanması
category: linux
tags: crontab
---

Linux üzerinde hazır yüklü gelen ve `/etc/crontab` dosya yolunda barınan bir betiktir.

Örneğin bir shell betiği(`test.sh`) hazırlayıp bu betiği sunucu üzerinde belirli periyotlarda çalıştırmak isteyelim.

### `test.sh` Betiğimizi Oluşturalım

```sh
#! /bin/bash
echo "Merhaba\n" >> hello.log
```
(Bu betiğimiz "Merhaba" kelimesini `hello.log` dosyası üzerine ekleme görevi üstlenmektedir.)

### `test.sh` Betiğinin `crontab` Tarafından Çalıştırılabilmesi İçin İzin Haklarını Verilmesi

    chmod 700 test.sh

### `crontab`a Yeni Cron Eklenmesi Komutu Kullanılması

    crontab -e

`crontab -e` komutu ile açılan dosya sonuna aşağıdaki gibi **her dakika** çalışan içeriğin eklenmesi

```sh
* * * * * /root/test.sh
```
Buradaki zaman periyotlarını düzenlemek için aşağıdaki zaman görev kalıbı incelenebilir:

```sh
  *      *      *      *      *      COMMAND(s)
 −−−    −−−    −−−    −−−    −−−
  |      |      |      |      ⋱−−→  Day of week (0 - 7) (Sunday=0 or 7)
  |      |      |      ⋱−−−−−−−−−→  Month (1 - 12)
  |      |      ⋱−−−−−−−−−−−−−−−−→  Day of month (1 - 31)
  |      ⋱−−−−−−−−−−−−−−−−−−−−−−−→   Hour (0 - 23)
  ⋱−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−→   Minute (0 - 59)
```

artık **her dakika** da bir  "Merhaba" yazısı `hello.log` dosyası üzerine yazılmaktadır. Dikkat edin dosya patlamasın 😉

### Çalışan Cron Komutlarını Görmek İçin

    crontab -l

### Cron Komutlarını Silmek İçin

    crontab -r

### Kaynaklar

 - [https://dev.to/boobo94/how-to-back-up-postgres-database-on-linux-using-cronjob-2d3a](https://dev.to/boobo94/how-to-back-up-postgres-database-on-linux-using-cronjob-2d3a)
 
 - [https://crontab.guru/](https://crontab.guru/)
