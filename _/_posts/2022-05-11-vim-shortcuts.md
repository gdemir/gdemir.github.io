---
layout: post
title: Vim Kısayolları
category: linux
tags: editor vim
---

| KOMUTLAR | AÇIKLAMA |
| --- | --- |
| `g` + `g` | İmleçi dosyanın başına getirir. | 
| `SHIFT` + `g` | İmleçi dosyanın  sonuna getirir. |
| `i` | Dosyayı görüntüleme modundan çıkarıp düzenleme moduna geçmenize sağlar. |
| `ESC` | Düzenleme modundan çıkıp görüntüleme moduna geçmenizi sağlar. |
| `0` | İmleçi bulunduğu satırın en başına getirir. (Görüntüleme modunda iken) |
| `$` | İmleçi bulunduğu satırın sonuna götürür. (Görüntüleme modunda iken) |
| `:w` | Dosya içerisindeki değişiklikleri kaydetmenizi sağlar. |
| `:q` | Dosyadan çıkmanızı sağlar. |
| `:q!` | Dosyadaki değişiklikleri kaydetmeyerek çıkmanızı sağlar. |
| `:wq` | Dosya içerisindeki değişiklikleri kaydedip çıkmanızı sağlar. |
| `u` | Görüntüleme modunda iseniz yapılan değişiklikleri geri almanıza sağlar. |
| `SHIFT` + `v` | İmleçin bulunduğu ilgili satırı seçer. (Aşağı-Yukarı ok tuşlarıyla seçilen satırları genişletebilirsiniz.) |
| `y` | İmleçin seçtiği satırları kopyalar. |
| `p` | Görüntüleme modunda iken kopyaladığınız satırları yapıştırmanızı sağlar. |
| `:'<,'>%s/SEARCH/REPLACE/g` | İlgili satırlarda **SEARCH** anahtarının değerini **REPLACE** ile değiştirir. |
| `:'<,'>%s/SEARCH/REPLACE/gc` | İlgili satırlarda **SEARCH** anahtarının değerini **REPLACE** ile değiştirirken adım adım sorar |
| `d` | Düzenleme modunda seçilen satırları, görüntüleme modunda da imleçin üstündeki satırı siler. |
| `/SEARCH` | Görüntüleme modunda ilgili **SEARCH** anahtarının değerinin ilk eşleşmesini bulur, üstündeki imleçte getirir. |
| `*` | Görüntüleme modunda da imleç kelime üzerindeyken her basıldığında imleçin sonraki aynı kelimeyi bulur ve imleçte üstüne gider. |

### Kaynak

- [https://umutbey.com/vim-kisayollari-en-cok-kullanilan-16-kisayol/](https://umutbey.com/vim-kisayollari-en-cok-kullanilan-16-kisayol/)
