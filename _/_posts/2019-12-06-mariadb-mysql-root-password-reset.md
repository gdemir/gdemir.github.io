---
layout: post
title: MariaDB ile MySQL Root Parolasını Sıfırlama
category: linux
tags: mariadb mysql root password
---

#### MySQL Devre Dışı Bırakma

    sudo systemctl stop mysql

#### MySQL Güvenli Modda Çalıştırılma

    sudo mysqld_safe --skip-grant-tables &

eğer tekrardan çalıştırmak istersek ve "error mysqld_safe - a mysqld process already exists." yanılgısı alırsak 2 adım izlenecek:

    killall mysqld mysqld_safe

ve

    killall -9 mysqld mysqld_safe

#### MySQL'e Girişi Tekrar Test Etmek

    mysql -u root -p

### Kaynaklar

- [https://stackoverflow.com/questions/28068155/access-denied-for-user-rootlocalhost-using-password-yes-after-new-instal](https://stackoverflow.com/questions/28068155/access-denied-for-user-rootlocalhost-using-password-yes-after-new-instal)

