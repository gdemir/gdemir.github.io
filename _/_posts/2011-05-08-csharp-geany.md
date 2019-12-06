---
layout: post
title: C# Kodunu Geany'de Çalıştırmak
category: linux
tags: editor geany csharp
---

Geanyde .cs uzantılı bir dosya açıyoruz ve geany'nin üstteki seçeneklerden  `İnşa Et > Dahili Seçenekleri ve Argümanları Ayarla` kısmına giriyoruz. Resimdeki gibi 

![csharp-in-geany](http://gdemir.github.io/file/csharp-in-geany.png)

Derle kısmına :

	  gmcs -nowarn:0219 /t:winexe "%f" /r:System,System.Drawing

Çalıştır kısmına :

	  gmcs -nowarn:0219 /t:winexe "%f" /r:System,System.Drawing ; mono "%e.exe"

yazıyoruz, sonra tamam deyip kaydediyoruz, bu kadar. Not : csharp kurmak için :

          sudo apt-get install monodevelop

Derlemek için :

          mono-csc t.cs

Çalıştırmak için :

          ./t.exe
