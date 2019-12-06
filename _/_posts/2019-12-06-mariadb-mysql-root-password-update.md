---
layout: post
title: MariaDB MySQL Root Parola Değiştirme
category: linux
tags: mariadb, mysql, root, password
---

#### Root Kullanıcısı İçin Gerekli Parola Atamasının Yapılması

    GRANT ALL PRIVILEGES on *.* to 'root'@'localhost' IDENTIFIED BY '<password>';
    FLUSH PRIVILEGES;

#### Ek Olarak MariaDB İçerisinde Kök Dizin Olarak Bu Parolanın Kullanılmasının Sağlanması

    UPDATE mysql.user SET plugin = 'mysql_native_password' WHERE user = 'root' AND plugin = 'unix_socket';
    FLUSH PRIVILEGES;

#### MySQL Servisinin Yeniden Başlatılması

    sudo service mysql restart

### Kaynaklar

- https://linuxize.com/post/how-to-reset-a-mysql-root-password/