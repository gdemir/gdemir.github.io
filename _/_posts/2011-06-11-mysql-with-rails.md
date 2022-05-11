---
layout: post
title: Ruby on Rails ile MySQL
category: rails
tags: mysql
---

Normal RoR kurulumundan farklı olarak kurarken

	rails new my_app -d mysql

bu şekilde rails'de default olarak gelen sqlite3 yerine MySQL olarak inmiş oluyor.

Ek olarak `mysql` gemini kurmak gerekiyor :

	sudo gem install mysql2 # mysql2 kuruyoruz

Varsayılan rails kurulumunu yaptıysanız versiyon `0.2.6`'yı kurun:

	sudo gem install mysql2 -v 0.2.11


### MySQL gem'i kurulumunda karşılaşılan hatalar ve çözümleri

#### extconf.rb failed

Kurulumda clientlerin çalışmamasından dolayı hata alıyorsnuz şu kütüphaneyi yükleyin:

	sudo apt-get install libmysqlclient-dev

#### Could not find gem 'mysql2 (~> 0.2.6, runtime)' in any of the gem sources listed in your Gemfile. Run `bundle install` to install missing gems.

Rails sürümünüz `Gemfile` da `mysql2`nin versiyon olarak `0.2.6`dan yukarı olmasını istiyor şu gemi yükleyin:

	sudo gem install mysql2 -v 0.2.6
