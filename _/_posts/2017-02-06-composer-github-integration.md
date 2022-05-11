---
layout: post
title: GitHub Üzerinden Composer'e Paket Entegrasyonu
category: php
tags: composer vendor plugins packages
---

Composer üzerine eklenen tüm paketler [https://packagist.org](https://packagist.org) üzerinden erişim sağlanabilmektedir. Buraya eklenecek paketler Bitbucket veya GitHub üzerindeki projenize ilgili API Token ile bağlantı sağlamakta ve erişilmektedir. Bitbucket or GitHub hesapları olamayanlar için manual kurulumu da anlatılmaktadır ilgili sitede anlatılmaktadır. (Bk.: [https://packagist.org/about](https://packagist.org/about))
Aşağıda bir Github projenizi nasıl [https://packagist.org](https://packagist.org) üzerinden servis edeceksiniz adım adım anlatacağım.

### Hesap Oluşturma

[https://packagist.org](https://packagist.org) üzerinde hesabımız yoksa [https://packagist.org/register/](https://packagist.org/register/) linkinden bir hesap açıyoruz.

### Packagist Üzerinden API Token Alma

[https://packagist.org](https://packagist.org) üzerinden Profile yani [https://packagist.org/profile/](https://packagist.org/profile/) linkine tıklıyoruz. Show API Token diyerek kendi Token'imizi kopyalıyoruz.

### GitHub Projenize Packagist Servisi Ekleme

GitHub üzerinden paket olarak ekliyeceğiniz proje için,

- İlgili projeye tıklıyoruz

- Settings kısmına tıklıyoruz

- Integrations & services kısmına tıklıyoruz

- Add Service > Packagist tıklıyoruz

Packagist profil sayfamızdaki,

- Kullanıcı Adınızı

- API Token bilginizi

- Projenin varsa bir web sayfasını

ekliyerek kaydetiyoruz. Buraya kadar her şey tamam, artık [https://packagist.org](https://packagist.org) projeniz servis edilmiş oluyor artık bu projenizi kullanmak isteyen arkadaşlar yapması gereken sadece aşağıdaki komut olacaktır.

    composer create-project {GitHub_Username}/{GitHub_Project} {Directory}

### Packagist'e Paket Gönderimi

Paket gönderimini yapmadan önce ilgili projenizin ana dizin içerisinde `composer.json` dosyası eklenmiş olması gerekmektedir. Burada örnek verecek olursak,

    {
        "name": "barak-framework/barak",
        "type": "project",
        "description": "Barak Framework",
        "keywords": ["barak", "turkmen", "framework"],
        "homepage": "https://github.com/barak-framework",
        "license": "MIT",
        "authors": [
            {
                "name": "Gökhan DEMİR",
                "email": "gdemir3327@gmail.com",
                "homepage": "https://gdemir.github.io",
                "role": "Developer"
            }
        ],
        "require": {
            "php": ">=5.4.0",
            "phpmailer/phpmailer": "~5.2"
        }
    }

şeklinde bir `composer.json` tanımlayabilirsiniz. Daha fazla detay için [https://getcomposer.org/doc/04-schema.md](https://getcomposer.org/doc/04-schema.md) sayfasına bakabilirsiniz. Ana dizinimizde artık `composer.json` dosyası olduğundan dolayı artık projeyi senkronize için gönderebiliriz. Göndermek için projenizin bulunduğu Bitbucket veya GitHub url linkini (`https://github.com/barak-framework/barak` gibi) [https://packagist.org/packages/submit](https://packagist.org/packages/submit) linkindeki ilgili yere check yapmanız yeterlidir. Eğer check sonrası henüz bir sonuç yoksa 1 gün sonra tekrar deneyin API bilgilerinin senkronize sağlaması geç sürebilir. 

### Örnek 

- [barak-framework/barak](https://packagist.org/packages/barak-framework/barak)

### Kaynak

- [https://packagist.org](https://packagist.org)

- [https://packagist.org/about#how-to-update-packages](https://packagist.org/about#how-to-update-packages)
