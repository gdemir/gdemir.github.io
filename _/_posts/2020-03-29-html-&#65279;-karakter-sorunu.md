---
layout: post
title: Html &amp;#65279; Karakter Sorunu
category: linux
tags: error
---

Bu sorun genelde UTF desteklemeyen bir editör(Notepad gibi) ile kod düzenlemerinde ortaya çıkmaktadır. Editör ile açıldığında da görünmemektedir.

Hangi dosyalarda sorun olduğunu anlamak için aşağıdaki kod çalıştırılır:

```sh
grep -rl $'\xEF\xBB\xBF' .
```

Sorunu düzelmek için aşağıdaki kod çalıştırılır:

```sh
sudo sed -i 's/\xEF\xBB\xBF//g' FILE
```

Kaynaklar

- https://stackoverflow.com/questions/9691771/why-is-65279-appearing-in-my-html

- https://stackoverflow.com/questions/3255993/how-do-i-remove-%C3%AF-from-the-beginning-of-a-file
