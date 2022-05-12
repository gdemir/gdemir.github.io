---
layout: post
title: GitHub Remote Komutu
category: github 
tags: remote
---

git remote komutu bir uzak dizine bağlanmasını(kanca atmasını) sağlar.

### Uzak Repoları Listeleme

Tanımlı uzak repolarının isimlerini(**NAME**) listeler:

    git remote

Tanımlı uzak repolarının isimlerini(**NAME**) ve linklerini(**URL**) listeler:

    git remote -v

### Uzak Repo Ekleme

    git remote add <NAME> <URL>

NAME için 2 seçenek mevcuttur:

- `origin` : Forklayıp oluşturduğunuz kendi reponuzdur.

- `upstream` : Forkladığınız asıl(uzak repoya) atıfta bulunur. (Uzak repodaki değişiklikleri almak için)

Örnek `origin` için **URL** `SSH` olmalıdır:

    git remote add origin git@github.com:gdemir/gdemir.github.io.git

Örnek `upstream` için **URL** `HTTPS` olmalıdır:

    git remote add upstream https://github.com/koy-odasi/core.git

### Uzak Repo Sorgulama

Uzak ve yakın repo tanımlıysa ilgili **URL** linkini gösterir:

    git config remote.<NAME>.url

Örnek `origin` için;

    git config remote.origin.url

Örnek `upstream` için;

    git config remote.upstream.url

### Uzak Repo Silme

İlgili uzak repo ismi ile bağlantı silinir:

    git remote rm <NAME>

### Uzak Repo Güncellemelerini Al

İlgili uzak repoda güncelleme varsa alınlamasını sağlar:

    git pull <NAME> master

Örnek `origin` için;

    git pull

veya

    git pull origin master

Örnek `upstream` için;

    git pull upstream master

### Uzak Repo Adını Değiştirme

İlgili uzak repoda tanımlı olan repo ismini değiştirmenizi sağlar.

    git remote rename <SEARCHNAME> <REPLACENAME>

Örnek;

    git remote rename origin upstream

### Kaynak

- [https://stackoverflow.com/questions/9257533/what-is-the-difference-between-origin-and-upstream-on-github](https://stackoverflow.com/questions/9257533/what-is-the-difference-between-origin-and-upstream-on-github)

- [https://linuxize.com/post/how-to-remove-git-remotes/](https://linuxize.com/post/how-to-remove-git-remotes/)
