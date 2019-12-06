---
layout: post
title: diff ve patch
category: linux
tags: diff patch
---


Diff iki dosya arasındaki farkı, verdiğiniz seçeneğer göre gösteren bir programdır.

#### Diff Kullanım

	diff [seçenekler] orjinal_dosya/orjinal_dizin  güncellenmiş_dosya/güncellenmiş_dizin


Patch diff'den aldıgı bir yama dosyasını, orginal dosyası ile birleştiren programdır.

#### Patch Kullanım

	patch [seçenekler] [patch_dosyası]

Şimdi bir yama ile orjinal dosyamızı yamalıyalım. Örneğin surum1.c ve surum2.c adında 2 dosyamız olsun. surum1.c dosyasında aşagıdaki kod var :

#include <stdio.h>
#define MAXLINE 128

int main() {
	char s[MAXLINE];
	int c, i;

	for (i = 0; i < MAXLINE; s[i] = 0, i++)
		; /*void*/
	s[i] = '\0';

	for (i = 0; i < MAXLINE; i++)
		if (s[i] != 0) printf(" %c\t=>\t%d\n", i, s[i]);

	return 0;
}

surum2.c dosyasında aşagıdaki kod var :

#include <stdio.h>
#define MAXLINE 128

int main() {
	char s[MAXLINE];
	int c, i;

	for (i = 0; i < MAXLINE; s[i] = 0, i++)
		; /*void*/
	s[i] = '\0';

	for (; (c = getchar()) != EOF; s[c] += 1)
		;/*void*/

	for (i = 0; i < MAXLINE; i++)
		if (s[i] != 0) printf(" %c\t=>\t%d\n", i, s[i]);

	return 0;
}

dosyalar birbirinden farklı mı diye bakıyoruz :

	diff -q surum1.c surum2.c

sorun yok ise yukarıdaki komut boş dönecektir. surum1.c kodunu surum2.c arasındaki farkı görmek için :

	diff -Naur surum1.c surum2.c

farkı yama yapıp surum1.c'yi güncellemek için ise :

	diff -Naur surum1.c surum2.c > surum1.patch
	patch -p0 < surum1.patch

veya daha kısası olarak pipe(borulama) :

	diff -Naur surum1.c surum2.c | patch -p0

olarak kullanılabilir.

Not : patch komutu surum1.patch yamasını dosya1'ye(surum1.c) uygulayacagını anlaması için; dosya2(surum2.c) isminin en az dosya1'den eşit ya da uzun olması gerek, ya da `patch -p0 surum1.c < surum1.patch` şekilde nereye patch yapacağının bildirilmesi gerekir.
