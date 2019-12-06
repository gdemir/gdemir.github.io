---
layout: post
title: Rails fastercsv ile CSV Çıktı
category: rails
tags: fastercsv csv
---


Rails'de Csv çıktıları için fastercsv gemi

<script src="http://gist.github.com/1681820.js" type="text/javascript"> </script>

örnekler : [JEG2/fastercsv](http://github.com/JEG2/faster_csv/tree/master/examples)

#### Kurulum

        sudo gem install fastercsv

#### `Gemfile` İçine Eklenti

        gem, 'fastercsv'

#### Ek Olarak İlgili Dosya Başına Eklenmesi

        require 'fastercsv'
