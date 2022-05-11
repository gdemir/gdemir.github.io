---
layout: post
title: GitHub Push Hatası
category: github
tags: git push error
---

#### Git Push Hatası
`GitHub`a cv-creator dizinime push ederken bir kesinti oldu ve bilgisayar kapandı. Tekrardan açtığımda yarıda kalan `git push` komutunun çalışmadığını gördüm

	gdemir@hummer:~/workspace/cv-creator$ git push
	error: object file .git/objects/3a/648d4feca2e03cdcfdbe70f150fd4dab1b8697 is empty
	fatal: loose object 3a648d4feca2e03cdcfdbe70f150fd4dab1b8697 (stored in .git/objects/3a/648d4feca2e03cdcfdbe70f150fd4dab1b8697) is corrupt

#### Git Commit Id'isinin Bulunması ve Commit Id'sine Geçiş Yapılması

ne olur, ne olmaz `.git` dizinimizi kopyalayalım

	gdemir@hummer:~/workspace/cv-creator$ cp -a .git/ .git-old

hata veren `commit id`sini bulalım

	gdemir@hummer:~/workspace/cv-creator$ tail -n 2 .git/logs/refs/heads/master
	0000000000000000000000000000000000000000 0346e42c8b49cb07d31dbbd8b2322b995fb02baf gdemir <gdemir3327@gmail.com> 1429775482 +0300	clone: from git@github.com:gdemir/cv-creator.git

`git push` hatası aldığımız `commit id`si `0346e42c8b49cb07d31dbbd8b2322b995fb02baf` olan dosya değişimlerini görüntüleyelim

	gdemir@hummer:~/workspace/cv-creator$ git show 0346e42c8b49cb07d31dbbd8b2322b995fb02baf
	commit 0346e42c8b49cb07d31dbbd8b2322b995fb02baf
	Author: gdemir <gdemir@hummer.(none)>
	Date:   Mon Mar 16 09:39:07 2015 +0200

	    update:email

	diff --git a/_config.yml b/_config.yml
	index 7a12c39..85cfb48 100644
	--- a/_config.yml
	+++ b/_config.yml
	@@ -12,7 +12,7 @@ personal:
	   account: gdemir
	   domain: gdemir.github.io
	   site: https://gdemir.github.io
	-  email: mail@gdemir.me
	+  email: gdemir3327@gmail.com
	   photo: default.png
	   phone: +90(541) 3936946
	   birthday: 12.01.1990
	diff --git a/cv/cv.erb.pdf b/cv/cv.erb.pdf
	index de6774f..e9b5658 100644
	Binary files a/cv/cv.erb.pdf and b/cv/cv.erb.pdf differ

`HEAD` noktasından `commit id`imize geçiş yapalım

	gdemir@hummer:~/workspace/cv-creator$ git update-ref HEAD 0346e42c8b49cb07d31dbbd8b2322b995fb02baf

#### Reponun Resetlenmesi ve Hata Kontrolü Yapılması

`.git` dizinimizin `index` dosyasını silelim

	gdemir@hummer:~/workspace/cv-creator$ rm .git/index

resetleme işlemini yapıyoruz

	gdemir@hummer:~/workspace/cv-creator$ git reset
	Unstaged changes after reset:
	M	README.md
	M	_config.yml
	M	cv/cv.erb.pdf

`git fsck` ile kontrol ediyoruz sıkıntı var mı?

	gdemir@hummer:~/workspace/cv-creator$ git fsck --full
	Checking object directories: 100% (256/256), done.
	Checking objects: 100% (195/195), done.

#### Yarıda Kalan Git Push işleminin Bitirilmesi

sıkıntımız olmadığına göre `.git-old` dizinimizi siliyoruz

	gdemir@hummer:~/workspace/cv-creator$ sudo rm -rf .git-old

şimdi gönderemediğimiz değişikliklerimizi tekrardan görüyor mu bakalım

	gdemir@hummer:~/workspace/cv-creator$ git status 
	On branch master
	Your branch is up-to-date with 'origin/master'.

	Changes not staged for commit:
	  (use "git add <file>..." to update what will be committed)
	  (use "git checkout -- <file>..." to discard changes in working directory)

		modified:   README.md
		modified:   _config.yml
		modified:   cv/cv.erb.pdf

	no changes added to commit (use "git add" and/or "git commit -a")

`git commit` ile yarıda kalan işlemimize yorum yazıyoruz

	gdemir@hummer:~/workspace/cv-creator$ git commit -am '.'
	[master 09a7b83] .
	 3 files changed, 22 insertions(+), 4 deletions(-)

`git push` ile ana depoya gönderiyoruz

	gdemir@hummer:~/workspace/cv-creator$ git push
	Counting objects: 11, done.
	Delta compression using up to 2 threads.
	Compressing objects: 100% (5/5), done.
	Writing objects: 100% (6/6), 68.58 KiB | 0 bytes/s, done.
	Total 6 (delta 3), reused 0 (delta 0)
	To git@github.com:gdemir/cv-creator.git
	   0346e42..09a7b83  master -> master

### Kaynak

- [how to fix GIT error: object file is empty?](http://stackoverflow.com/questions/11706215/how-to-fix-git-error-object-file-is-empty?answertab=votes#tab-top)
