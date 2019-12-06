---
layout: post
title: Sublime Text Üzerinde Python Kodu Çalıştırma
category: linux
tags: sublime editor
---

#### "Control.sublime-package" Dosyasının Oluşturulması
Sublime'da `Preferences(Tercihler) > Browse Packages(Paketleri Araştır)` kısmına tıklayın. Bulunduğunuz klasörden `Back Button(Geri Tuş)` basın. `Installed Packages/`  dizinin içine [Install Package Control](https://sublime.wbond.net/installation#st2) sitesinden Sublime Text3 metnini kopyalayıp `Control.sublime-package` dosyası adında kaydedin. Sublime'i tekrardan başlatın.

#### Kullanıcı Ayarlarının Default Olarak Ayarlanması

`Preferences > Settings - Default` kısmındaki dosyanın içeriğinin tümünü kopyalayın ve `Preferences > Settings - User` kısmındaki dosyanın içine yapıştırın. (Önceden bir ayar varsa hepsini silin). Sublime'i tekrardan başlatın.

#### Çalıştırma

Çalıştırmak için `CTRL + B` tuşuna basmanız yeterlidir. Kod çıktısını görmek için `View > Show Console` kısmına tıklayarak takip edebilirsiniz.

#### Kaynak

[How to Run Python Code on SublimeREPL](http://stackoverflow.com/questions/19732006/how-to-run-python-code-on-sublimerepl)
