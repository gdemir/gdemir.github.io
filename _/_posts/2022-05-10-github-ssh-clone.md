---
layout: post
title: GitHub SSH Clone
category: github
tags: clone

### Public ve Private Anahtarlarının Üretilmesi

    ssh-keygen

komut çalıştırıldığında  `id_rsa` konumu ve gerekli olan şifreyi(2 defa) sormaktadır, bunları giriyoruz.

```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/gdemir/.ssh/id_rsa):
Created directory '/home/gdemir/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/gdemir/.ssh/id_rsa.
Your public key has been saved in /home/gdemir/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:232/jCVq/32323gokhan.demir@TRF5020F95
The key's randomart image is:
+---[RSA 2048]----+
|                 |
|           .     |
|          . . E .|
|       . + .   = |
|   .  . S = . . o|
|  . .. + *.o   ..|
|   o...+*o+.    .|
|  . o=*oB= ..  o |
|    BO.=++*o.o+  |
+----[SHA256]-----+
```

### Public Anahtarımızın GitHub Sitesi İçine Kaydedilmesi

Bunlar girildikten sonra `~/home/gdemir/.ssh/` dizini altında  `id_rsa` ve `id_rsa.pub` anahtarları oluşmaktadır.
Oluşturulan bu `~/home/gdemir/.ssh/id_rsa.pub`  içerisindeki **key**imizi;

[GitHub](https://github.com/) → [Settings](https://github.com/settings)  → [SSH and GPG keys](https://github.com/settings/keys) → [Add new SSH keys](https://github.com/settings/ssh/new) içerisine,

belirlediğiniz bir **title** (gdemir@ubuntu gibi) girilerek **key**imizi yapıştırıyoruz.
Artık sahip olduğumuz repolarımızı clone etme imkanımız olmuş oluyor. Clone etmek isteğiniz repoyu aşağıdaki gibi çalıştırıyorsunuz.

    git clone git@github.com:gdemir/gdemir.github.io.git

Artık repo üzerindeki dosyalar üzerinde güncelleme yapıp

    git commit -am 'gerekli güncelleme yapıldı'

komutuyla `commit` atıp

    git push

komutuyla ilgili repomuz GitHub üzerinde güncellenmiş oluyoruz.


###

 - [https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/github-clone-with-ssh-keys](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/github-clone-with-ssh-keys)

