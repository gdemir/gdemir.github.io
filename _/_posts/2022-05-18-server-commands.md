---
layout: post
title: Sunucu Komutları
category: linux
tags: server os uptime
---

Sunucunun hangi **işletim sistemi** ve **işletim sistemi versiyonunu** kullandığını öğrenmek `/etc/issue` dosyasının içerisine bakabilirsiniz.

    cat /etc/issue

Örnek;

    root@hummer:~# cat /etc/issue
    Ubuntu 16.04.6 LTS \n \l

Sunucunun ne kadar süre çalıştığını(ayakta kaldığını) örğrenmek için `uptime` komutunu kullanabilirsiniz.

    uptime

Örnek;

    root@hummer:~# uptime
    07:01:57 up 519 days, 10:39,  1 user,  load average: 0.02, 0.05, 0.03

### Kaynak

- [https://linuxconfig.org/check-what-debian-version-you-are-running-on-your-linux-system](https://linuxconfig.org/check-what-debian-version-you-are-running-on-your-linux-system)
