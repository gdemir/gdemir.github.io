---
layout: post
title: Crontab İle MySQL Veritabanı Yedeğinin Alınması
category: linux
tags: crontab, mysql
---

### Yedek Dosyalarımızı İçin Dizin Oluşturuyoruz

    mkdir /root/db_backups

### Yeni Cron Ekliyoruz

    crontab -e

komutuyla açılan içeriğin sonuna;

- DBNAME veritabanına ait  'USERNAME' isimli kullanıcının 'PASSWORD' parolasıyla 
- Her ayın ilk gününün saat 00:00 'da (01.06,2022 saat 00:00'da, 01.07,2022 saat 00:00'da ... gibi)

alınacak yedek dosyası için aşağıdaki gibi yedekleme komutumuzu yazıyoruz:

    0 0 1 * * mysqldump --user='USERNAME' --password='PASSWORD' DBNAME> /root/db_backup/backup_`date +\%Y-\%m-\%d_\%H:\%M`.sql

### Kaynaklar

 - [https://exchangetuts.com/mysqldump-doesnt-work-in-crontab-1639698246383336](https://exchangetuts.com/mysqldump-doesnt-work-in-crontab-1639698246383336)
 
 - [https://crontab.guru/](https://crontab.guru/)

