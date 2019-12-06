---
layout: post
title: Yüklemede Kaldığı Yerden Devam - rsync
category: linux
tags: rsync
---

Bazen scp ile büyük boyutlu bir dosyayı upload etmek gerekiyor. Bu işlemin takılı kalması ("stalled") ihtimali var. Takıldığında al baştan yapmanız gerekiyor. Bu nedenle büyük boyutlu dosyaları rsync ile aşağıdaki gibi upload etmekte yarar var, işlem takılırsa komutu tekrar çalıştırmanız yeterli:

	partial --progress --rsh=ssh kullanici@makine:uzak_dosya yerel_dosya
