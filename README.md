# YSelenium <!-- omit in toc -->

![GitHub last commit](https://img.shields.io/github/last-commit/yedhrab/YSelenium.svg?label=Son%20G%C3%BCncelleme&style=popout)
![GitHub](https://img.shields.io/github/license/yedhrab/YSelenium.svg?label=Lisans&style=popout)
![GitHub repo size](https://img.shields.io/github/repo-size/yedhrab/YSelenium.svg?label=Boyut&style=popout)

## İçerikler <!-- omit in toc -->

- [İnternetten Veri Çekme Kuralı](#i%CC%87nternetten-veri-%C3%A7ekme-kural%C4%B1)
- [Sistem Yapısı](#sistem-yap%C4%B1s%C4%B1)
- [GettyImage](#gettyimage)
  - [Operatör Sabitleri](#operat%C3%B6r-sabitleri)
  - [Sayfa Sabitleri](#sayfa-sabitleri)
- [Selenium Notları](#selenium-notlar%C4%B1)
- [TODO](#todo)
- [Lisans ve Teferruatlar](#lisans-ve-teferruatlar)

## İnternetten Veri Çekme Kuralı

![kural](res/scraping_flowchart.png)

## Sistem Yapısı

Her bir selenium script'ini `controller` üzerinden çalıştırabilirsiniz

- [Getty Images](controllers/gettyimages.py)
- [Kariyer](controllers/kariyer.py)
- [Berkeley](controllers/berkeley.py)

## GettyImage

Gettyimages üzerindeki resimleri toplu olarak indirmeyi sağlar

### Operatör Sabitleri

| Değişken     | Açıklama                             |
| ------------ | ------------------------------------ |
| `DOWNLOAD`   | Bulunan urlleri indirir              |
| `WRITE_FILE` | Bulunan url'leri dosyaya yazar       |
| `DEBUG`      | Ekrana bilgilendirme çıktıları basar |

### Sayfa Sabitleri

| Değişken   | Açıklama                                      |
| ---------- | --------------------------------------------- |
| `PAGE`     | Kaç sayfa tekrar edeceğini bildirir           |
| `PAGE_URL` | Sayfa değerinin olduğu kısmın `{}` olduğu url |

## Selenium Notları

<!-- TODO Selenium notlarını arttık, YSelenium dökümanına ekle -->

- Colab üzerinde (GUI'siz platformlarda) kullanılmak istenirse GUI kapatılmalıdır.
  - `config.py` içerisindeki `HIDE_BROWSER` `True` olmalı
- Javascript'ler *minify* edilmek zorunda aksi halde çalışmaz.
- Javascript'ler her sekme için ayrıca dahil edilmelidir.
- Global fonksiyonlar `window.` formatında olmalıdır
  - Python içerisinde kullanımda `window` yazmaya gerek yoktur
  - Örn: `window.temp = 5`, pythonda kullanım `driver.execute_script('return temp')`
- `driver` objesi 1 sekmeyi temsil etmekte
  - `driver.close` denirse o sekme kapanır
  - `driver.switch_to.window(driver.window_handles[1])` ile sekme arası yolculuk

## TODO

- [ ] Config için açıklama dökümanı ekle

## Lisans ve Teferruatlar

Bu yazı **MIT** lisanslıdır. Lisanslar hakkında bilgi almak için [buraya](https://choosealicense.com/licenses/) bakmanda fayda var.

- [Github](https://github.com/yedhrab)
- [Website](https://yemreak.com)
- [LinkedIn](https://www.linkedin.com/in/yemreak/)

> Yardım veya destek için [iletişime](mailto::yedhrab@gmail.com?subject=YSelenium%20%7C%20Github) geçebilrsiniz 🤗

~ Yunus Emre Ak
