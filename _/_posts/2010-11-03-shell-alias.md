---
layout: post
title: Shell Komutlarını Kısaltma
category: linux
tags: alias
---

alias komutu ile linux konsolunda sık kullandığınız komutların kısayolunu oluşturmamıza yarayan **takma ad**'dır. Örneğin `ls -al` ifadesini konsolda durmadan yazmak yerine,  

### `vim` ile `.bashrc`yi acıyoruz :

        vim ~/.bashrc
	
en alt satıra 

        alias li="ls -al"

yazıyoruz ve konsolu kapatıp tekrar açıyoruz. Konsolda `li` dediğimiz zaman, `ls -al` görevi görmüş oluyor.

