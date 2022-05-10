---
layout: post
title: Dosya İçerisindeki Tekil(Tekrar Etmeyen) IP'lerin Sayılarını Öğrenme
category:  linux
tags: bash 
---

`unique_ip_count_on_file.sh` betiğinin içeriği aşağıdaki gibidir;

```sh
#! /bin/bash

log_filename=$1

grep -o "[0-9]\+\.[0-9]\+\.[0-9]\+\.[0-9]\+" $log_filename | sort -u | wc -l
```

Çalıştırmak için;

    bash unique_ip_count_on_file.sh production_2022-05-10.log
