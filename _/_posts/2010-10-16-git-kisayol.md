---
layout: post
title: GitHub Komutlarını Kısaltma
category: github
tags: git gitconfig
---

Herzaman github ile uğraşıyorsak bazı kısayollara ihtiyacımız var;  
- git br = git branch  
- git ci = git commit  
- git co = git checkout  
- git di = git diff  
- git me = git merge  
- git pl = git pull  
- git pu = git push  
- git st = git status  
- git up = git pull  
yerine kullanabiliriz. Bunu için [github-ayar](http://gdemir.github.com/file/github-ayar) dosyasını ev dizinine indirin.  

	mv ~/github-ayar ~/.gitconfig

olarak dosyanın adını değiştirin.

	$EDITOR ~/.gitconfig

komutuyla dosyayı açın,  

`[user]` ve `[github]` kısmlarını kendi kişisel bilgilerinize göre düzenleyin bu kadar.  
