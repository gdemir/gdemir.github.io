---
layout: post
title: Vim Kısayolları
category: linux
tags: vim
---

| KOMUTLAR | AÇIKLAMA |
| --- | --- |
| `G` + `G` | İmleci dosyanın başına getirir. | 
| `SHIFT` + `G` | İmleci dosyanın  sonuna getirir. |
| `i` | Dosyayı görüntüleme modundan çıkarıp düzenleme moduna geçmenize sağlar. |
| `ESC` | `Düzenleme modundan çıkıp görüntüleme moduna geçmenizi sağlar. |
| `0` | İmleci bulunduğu satırın en başına getirir. (Görüntüleme modunda iken) |
| `$` | İmleci bulunduğu satırın sonuna götürür. (Görüntüleme modunda iken) |
| `:w` | Dosya içerisindeki değişiklikleri kaydetmenizi sağlar. |
| `:q` | Dosyadan çıkmanızı sağlar. |
| `:q!` | Dosyadaki değişiklikleri kaydetmeyerek çıkmanızı sağlar. |
| `:wq` | Dosya içerisindeki değişiklikleri kaydedip çıkmanızı sağlar. |
| `u` | Görüntüleme modunda iseniz yapılan değişiklikleri geri almanıza sağlar. |
| `SHIFT` + `v` | İmlecin bulunduğu ilgili satırı seçer. (Aşağı-Yukarı ok tuşlarıyla seçilen satırları genişletebilirsiniz.) |
| `y` | İmlecin seçtiği satırları kopyalar. |
| `p` | Görüntüleme modunda iken kopyaladığınız satırları yapıştırmanızı sağlar. |
| `:'<,'>%s/SEARCH/REPLACE/g` | İlgili satırlarda **SEARCH** anahtarının değerini **REPLACE** ile değiştirir. |
| `:'<,'>%s/SEARCH/REPLACE/gc` | İlgili satırlarda **SEARCH** anahtarının değerini **REPLACE** ile değiştirirken adım adım sorar |
| `d` | Düzenleme modunda seçilen satırları, görüntüleme modunda da imlecin üstündeki satırı siler. |

### Kaynaklar

- [https://umutbey.com/vim-kisayollari-en-cok-kullanilan-16-kisayol/](https://umutbey.com/vim-kisayollari-en-cok-kullanilan-16-kisayol/)
