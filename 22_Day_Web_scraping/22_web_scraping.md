<div align="center">
  <h1> 30 Günde Python: 22. Gün - Web Scraping </h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Yazar:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> İkinci Versiyon: Temmuz, 2021</small>
</sub>
</div>

[<< 21. Gün](../21_Day_Classes_and_objects/21_classes_and_objects.md) | [23. Gün >>](../23_Day_Virtual_environment/23_virtual_environment.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 22. Gün](#-day-22)
  - [Python Web Scraping](#python-web-scraping)
    - [Web Scrapping Nedir?](#what-is-web-scrapping)
  - [💻 Alıştırmalar: 22. Gün](#-exercises-day-22)

# 📘 22. Gün

## Python Web Scraping

### Web Scrapping Nedir?

İnternet, farklı amaçlar için kullanılabilecek büyük miktarda veriyle doludur. Bu verileri toplamak için, bir web sitesinden veri kazımanın (scraping) nasıl yapıldığını bilmemiz gerekir.

Web scraping, web sitelerinden veri çıkarma ve toplama, ardından bu verileri yerel makineye veya bir veri tabanına kaydetme işlemidir.

Bu bölümde, scraping için BeautifulSoup ve requests paketlerini kullanacağız. Kullandığımız BeautifulSoup sürümü BeautifulSoup 4’tür.

Web sitelerinden veri kazımaya başlamak için _requests_, _BeautifulSoup4_ ve bir _web sitesi_ gereklidir.

```sh
pip install requests
pip install beautifulsoup4
```

Web sitelerinden veri kazımak için, HTML tagleri ve CSS selectorları hakkında temel bir anlayışa sahip olmak gerekir. Bir web sitesindeki içeriği hedeflemek için HTML taglerini, classları ve/veya idleri kullanırız.
Şimdi requests ve BeautifulSoup modüllerini içe aktaralım.

```py
import requests
from bs4 import BeautifulSoup
```

Scraping işlemini yapacağımız web sitesi için bir url değişkeni tanımlayalım.

```py

import requests
from bs4 import BeautifulSoup
url = 'https://archive.ics.uci.edu/ml/datasets.php'

# urlden veri çekmek için requests get metodunu kullanalım

response = requests.get(url)
# başarı statusünü kontrol edelim
status = response.status_code
print(status) # 200 başarılı demek
```

```sh
200
```

Sayfadaki içeriği BeautifulSoup kullanarak parse etme işlemini yapalım.

```py
import requests
from bs4 import BeautifulSoup
url = 'https://archive.ics.uci.edu/ml/datasets.php'

response = requests.get(url)
content = response.content # sitedeki tüm içeriği alma
soup = BeautifulSoup(content, 'html.parser') # beautiful soup parse etmeyi sağlayacak
print(soup.title) # <title>UCI Machine Learning Repository: Data Sets</title>
print(soup.title.get_text()) # UCI Machine Learning Repository: Data Sets
print(soup.body) # tüm sayfayı verir
print(response.status_code)

tables = soup.find_all('table', {'cellpadding':'3'})
# Hücre aralığı (cellpadding) özelliği 3 olan tabloyu hedefliyoruz.
# Seçimi id, class veya HTML tagi kullanarak yapabiliriz. Daha fazla bilgi için BeautifulSoup dokümanına (docs) göz atın.
table = tables[0] # sonuç list olarak döner, veriyi burdan alıyoruz
for td in table.find('tr').find_all('td'):
    print(td.text)
```

Bu kodu çalıştırırsan, veri çıkarma işleminin yarısının tamamlandığını görebilirsin.
Bu işlemi kendin devam ettirebilirsin çünkü bu 1. alıştırmanın bir parçasıdır.
Referans olarak [BeautifulSoup belgelerine](https://www.crummy.com/software/BeautifulSoup/bs4/doc/#quick-start) bakabilirsin.

🌕 Çok iyisin, gün gün ilerliyorsun. Mükemellik yolunda sadece 8 günün kaldı. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 22. Gün

1. Bu web sitesinden veriyi kazı ve veriyi JSON dosyası olarak kaydet: (url = 'http://www.bu.edu/president/boston-university-facts-stats/').
1. Bu URL’deki tabloyu çıkar ve tabloyu JSON dosyası olarak dönüştür: (https://archive.ics.uci.edu/ml/datasets.php)
2. ABD başkanlarının tablosunu kazı ve JSON dosyası olarak kaydet: (https://en.wikipedia.org/wiki/List_of_presidents_of_the_United_States). Tablo çok düzenli değil, bu yüzden kazıma işlemi uzun sürebilir.

🎉 TEBRİKLER ! 🎉

[<< 21. Gün](../21_Day_Web_scraping/21_class_and_object.md) | [23. Gün >>](../23_Day_Virtual_environment/23_virtual_environment.md)
