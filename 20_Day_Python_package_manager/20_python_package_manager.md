<div align="center">
  <h1> 30 Günde Python: 20. Gün - Python Paket Yöneticisi </h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Yazar:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small>İkinci Versiyon: Temmuz, 2021</small>
</sub>
</div>

[<< 19. Gün](../19_Day_File_handling/19_file_handling.md) | [21. Gün >>](../21_Day_Classes_and_objects/21_classes_and_objects.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 20. Gün](#-day-20)
  - [Python PIP - Python Paket Yöneticisi](#python-pip---python-package-manager)
    - [PIP nedir?](#what-is-pip-)
    - [PIP'i Yüklemek](#installing-pip)
    - [pip Kullanarak Paket Yüklemek](#installing-packages-using-pip)
    - [Paket Yüklemesini Silmeks](#uninstalling-packages)
    - [Paket Listesi](#list-of-packages)
    - [Paket Bilgisi Gösterme](#show-package)
    - [PIP Freeze](#pip-freeze)
    - [URL'den Okumak](#reading-from-url)
    - [Paket Oluşturmak](#creating-a-package)
    - [Paketlerle İlgili İleri Bilgiler](#further-information-about-packages)
  - [Alıştırmalar: 20. Gün](#exercises-day-20)

# 📘 20. Gün

## Python PIP - Python Paket Yöneticisi

### PIP nedir?

PIP, Preferred Installer Program (Tercih Edilen Yükleyici Program) anlamına gelir. Python’da farklı paketleri yüklemek için _pip_ kullanırız. Paket (package), bir veya birden fazla modül ya da başka paketler içerebilen bir Python modülüdür. Programlamada her yardımcı programı sıfırdan yazmamıza gerek yoktur; bunun yerine, hazır paketleri yükleyip uygulamalarımıza dahil ederiz.

### PIP'i Yüklemek

Daha önce pip yüklemediysen şimdi yükleyelim. Terminalini veya komut istemcini aç ve şunu kopyalayıp yapıştır:

```sh
asabeneh@Asabeneh:~$ pip install pip
```

pip kurulup kurulmadı mı kontrol etmek için şunu yaz

```sh
pip --version
```

```py
asabeneh@Asabeneh:~$ pip --version
pip 21.1.3 from /usr/local/lib/python3.7/site-packages/pip (python 3.9.6)
```

Gördüğün gibi ben pip version 21.1.3 kullanıyorum, eğer buna yakın bir sayı gördüysen pip'i başarıyla yükledin demek.

Python topluluğunda farklı amaçlar için kullanılan bazı paketlere bakalım. Şunu söylemeliyim ki: farklı uygulamalarda kullanılabilecek çok sayıda paket vardır.

### pip Kullanarak Paket Yüklemek

Şimdi NumPy (Numerical Python'ın kısaltması) adlı paketi kurmayı deneyelim. NumPy, makine öğrenimi ve veri bilimi alanlarında en popüler paketlerden biridir.

- NumPy, Python ile bilimsel hesaplama için temel bir pakettir. Şunları içerir:
  - Güçlü bir N-boyutlu array objesi
  - Gelişmiş yayılma (broadcasting) fonksiyonları
  - C/C++ ve Fortran kodlarıyla entegrasyon araçları
  - Doğrusal cebir, Fourier dönüşümü ve rastgele sayı üretme yetenekleri

```sh
asabeneh@Asabeneh:~$ pip install numpy
```

numpy kullanmaya başlayalım. Python interactive shelli aç python yaz ve numpy'ı şu şekilde import et:

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import numpy
>>> numpy.version.version
'1.20.1'
>>> lst = [1, 2, 3,4, 5]
>>> np_arr = numpy.array(lst)
>>> np_arr
array([1, 2, 3, 4, 5])
>>> len(np_arr)
5
>>> np_arr * 2
array([ 2,  4,  6,  8, 10])
>>> np_arr  + 2
array([3, 4, 5, 6, 7])
>>>
```

Pandas, açık kaynaklı ve BSD lisanslı bir kütüphanedir. Python programlama dili için yüksek performanslı, kullanımı kolay veri yapıları ve veri analizi araçları sağlar. Şimdi, NumPy’nin abisi olarak bilinen _pandas_ kütüphanesini kuralım::

```sh
asabeneh@Asabeneh:~$ pip install pandas
```

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import pandas
```

Bu bölüm NumPy veya Pandas hakkında değil — burada, paketlerin nasıl yükleneceğini ve içe aktarılacağını (import edileceğini) öğreniyoruz.
Farklı kütüphanelerden diğer bölümlerde bahsedeceğiz.

Şimdi, web tarayıcısı modülünü (webbrowser) içe aktaralım. Bu modül, herhangi bir web sitesini doğrudan Python üzerinden açmamıza yardımcı olur. Ayrıca bu modül, Python 3 ile önceden yüklü olarak gelir, yani kurulum yapmamıza gerek yoktur. Örneğin, istediğin anda bir veya birden fazla siteyi açmak ya da belirli bir zamanı planlamak istiyorsan, _webbrowser_ modülünü kullanabilirsin.

```py
import webbrowser # web sitelerini açmak için web browser modülü

# url listi: python
url_lists = [
    'http://www.python.org',
    'https://www.linkedin.com/in/asabeneh/',
    'https://github.com/Asabeneh',
    'https://twitter.com/Asabeneh',
]

# yukarıdaki listteki web sitelerini farklı sekmelerde açar
for url in url_lists:
    webbrowser.open_new_tab(url)
```

### Paket Yüklemesini Silmek

Yüklü paketleri cihazında tutmak istemiyorsan aşağıdaki komutla paketleri silebilirsin.

```sh
pip uninstall packagename
```

### Paket Listesi

Makinendeki tüm yüklü paketleri görmek için pip'i aşağıdaki gibi kullanabiliriz:

```sh
pip list
```

### Paket Bilgisi Gösterme

Bir paket hakkındaki bilgileri görmek için

```sh
pip show packagename
```

```sh
asabeneh@Asabeneh:~$ pip show pandas
Name: pandas
Version: 1.2.3
Summary: Powerful data structures for data analysis, time series, and statistics
Home-page: http://pandas.pydata.org
Author: None
Author-email: None
License: BSD
Location: /usr/local/lib/python3.7/site-packages
Requires: python-dateutil, pytz, numpy
Required-by:
```

Daha fazla detay için komuta --verbose ekleriz

```sh
asabeneh@Asabeneh:~$ pip show --verbose pandas
Name: pandas
Version: 1.2.3
Summary: Powerful data structures for data analysis, time series, and statistics
Home-page: http://pandas.pydata.org
Author: None
Author-email: None
License: BSD
Location: /usr/local/lib/python3.7/site-packages
Requires: numpy, pytz, python-dateutil
Required-by:
Metadata-Version: 2.1
Installer: pip
Classifiers:
  Development Status :: 5 - Production/Stable
  Environment :: Console
  Operating System :: OS Independent
  Intended Audience :: Science/Research
  Programming Language :: Python
  Programming Language :: Python :: 3
  Programming Language :: Python :: 3.5
  Programming Language :: Python :: 3.6
  Programming Language :: Python :: 3.7
  Programming Language :: Python :: 3.8
  Programming Language :: Cython
  Topic :: Scientific/Engineering
Entry-points:
  [pandas_plotting_backends]
  matplotlib = pandas:plotting._matplotlib
```

### PIP Freeze

Yüklü Python paketlerini sürümleriyle birlikte listeler ve çıktısı, requirements dosyasında kullanılabilecek formattadır. requirements.txt dosyası, bir Python projesinde kullanılan tüm yüklü paketlerin ve sürümlerinin yer aldığı bir dosyadır. Bu dosya, projeyi başka bir ortamda çalıştırmak isteyenlerin aynı paketleri kolayca yüklemesini sağlar.

```sh
asabeneh@Asabeneh:~$ pip freeze
docutils==0.11
Jinja2==2.7.2
MarkupSafe==0.19
Pygments==1.6
Sphinx==1.2.2
```

pip freeze kullanılan paketleri ve versiyonlarını verir. Bunu deployment (yayınlama/dağıtım) sırasında requirements.txt dosyasıyla birlikte kullanırız.

### URL'den Okumak

Artık yerel makinenizdeki bir dosyayı nasıl okuyacağını veya yazacağını biliyorsun. Bazen bir web sitesinden veya API’den veri okumak isteriz.
API (Application Program Interface), sunucular arasında genellikle JSON formatında yapılandırılmış veri alışverişi yapmamızı sağlayan bir arayüzdür.Bir ağ bağlantısı açmak için _requests_ paketini kullanırız. Bu paket, ağ bağlantısı kurmamıza ve CRUD (Create, Read, Update, Delete) operasyonlarını gerçekleştirmemize olanak tanır.

_requests_ yükleme:

```py
asabeneh@Asabeneh:~$ pip install requests
```

_requests_ modülünde _get_, _status_code_, _headers_, _text_ and _json_ metodlarını görüyor olacağız:
  - _get()_: Bir URL’den veri çekmek (ağ bağlantısı açmak) için kullanılır — bir response nesnesi döndürür.
  - _status_code_: Veriyi çektikten sonra işlemin durumunu kontrol etmek için kullanılır (başarılı mı, hata mı vb.)
  - _headers_: Gelen responseun başlık (header) bilgilerini görmek için kullanılır.
  - _text_: Response nesnesinden metin içeriğini almak için kullanılır.
  - _json_: JSON verisini almak için kullanılır.
https://www.w3.org/TR/PNG/iso_8859-1.txt sitesinden bir txt dosyası okuyalım.

```py
import requests # request modülünü import etme

url = 'https://www.w3.org/TR/PNG/iso_8859-1.txt' # web sitesinden bir metin dosyası

response = requests.get(url) # bağlantı açma ve veri çekme
print(response)
print(response.status_code) # status code, success:200
print(response.headers)     # header bilgisi
print(response.text) # sayfadaki tüm metinleri verir
```

```sh
<Response [200]>
200
{'date': 'Sun, 08 Dec 2019 18:00:31 GMT', 'last-modified': 'Fri, 07 Nov 2003 05:51:11 GMT', 'etag': '"17e9-3cb82080711c0;50c0b26855880-gzip"', 'accept-ranges': 'bytes', 'cache-control': 'max-age=31536000', 'expires': 'Mon, 07 Dec 2020 18:00:31 GMT', 'vary': 'Accept-Encoding', 'content-encoding': 'gzip', 'access-control-allow-origin': '*', 'content-length': '1616', 'content-type': 'text/plain', 'strict-transport-security': 'max-age=15552000; includeSubdomains; preload', 'content-security-policy': 'upgrade-insecure-requests'}
```

- Bir API'den okuma yapalım. API, Application Programming Interface (Uygulama Programlama Arayüzü) anlamına gelir. Sunucular arasında yapılandırılmış veriyi (çoğunlukla JSON formatında) değiş tokuş etmenin bir yoludur. Örnek API: https://restcountries.eu/rest/v2/all. _requests_ modülünü kullanarak bu API'yi okuyalım.

```py
import requests
url = 'https://restcountries.eu/rest/v2/all'  # ülke api'si
response = requests.get(url)  # bağlantı açma ve veri çekme
print(response) # response objesi
print(response.status_code)  # status code, success:200
countries = response.json()
print(countries[:1])  # sadece ilk ülkeyi aldık. Tüm ülkeleri görmek için bu slicingi kaldırın.
```

```sh
<Response [200]>
200
[{'alpha2Code': 'AF',
  'alpha3Code': 'AFG',
  'altSpellings': ['AF', 'Afġānistān'],
  'area': 652230.0,
  'borders': ['IRN', 'PAK', 'TKM', 'UZB', 'TJK', 'CHN'],
  'callingCodes': ['93'],
  'capital': 'Kabul',
  'cioc': 'AFG',
  'currencies': [{'code': 'AFN', 'name': 'Afghan afghani', 'symbol': '؋'}],
  'demonym': 'Afghan',
  'flag': 'https://restcountries.eu/data/afg.svg',
  'gini': 27.8,
  'languages': [{'iso639_1': 'ps',
                 'iso639_2': 'pus',
                 'name': 'Pashto',
                 'nativeName': 'پښتو'},
                {'iso639_1': 'uz',
                 'iso639_2': 'uzb',
                 'name': 'Uzbek',
                 'nativeName': 'Oʻzbek'},
                {'iso639_1': 'tk',
                 'iso639_2': 'tuk',
                 'name': 'Turkmen',
                 'nativeName': 'Türkmen'}],
  'latlng': [33.0, 65.0],
  'name': 'Afghanistan',
  'nativeName': 'افغانستان',
  'numericCode': '004',
  'population': 27657145,
  'region': 'Asia',
  'regionalBlocs': [{'acronym': 'SAARC',
                     'name': 'South Asian Association for Regional Cooperation',
                     'otherAcronyms': [],
                     'otherNames': []}],
  'subregion': 'Southern Asia',
  'timezones': ['UTC+04:30'],
  'topLevelDomain': ['.af'],
  'translations': {'br': 'Afeganistão',
                   'de': 'Afghanistan',
                   'es': 'Afganistán',
                   'fa': 'افغانستان',
                   'fr': 'Afghanistan',
                   'hr': 'Afganistan',
                   'it': 'Afghanistan',
                   'ja': 'アフガニスタン',
                   'nl': 'Afghanistan',
                   'pt': 'Afeganistão'}}]
```

We use _json()_ method from response object, if the we are fetching JSON data. For txt, html, xml and other file formats we can use _text_.

### Paket Oluşturmak

Çok sayıda dosyayı belirli kriterlere göre farklı klasörler ve alt klasörlerde organize ederiz, böylece onları kolayca bulabilir ve yönetebiliriz. Bildiğin gibi, bir modül birden fazla obje içerebilir; örneğin classlar, fonksiyonlar vb. Bir paket, bir veya daha fazla ilgili modül içerebilir.

Aslında bir paket, bir veya daha fazla modül dosyası içeren bir klasördür. Şimdi aşağıdaki adımları kullanarak mypackage adlı bir paket oluşturalım:

30GundePython klasörünün içinde mypackage adlı yeni bir klasör oluşturun.
mypackage klasöründe boş bir **__init__**.py dosyası oluşturun.
arithmetic.py ve greet.py modüllerini aşağıdaki kodlarla oluşturun:

```py
# mypackage/arithmetics.py
# arithmetics.py
def add_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total


def subtract(a, b):
    return (a - b)


def multiple(a, b):
    return a * b


def division(a, b):
    return a / b


def remainder(a, b):
    return a % b


def power(a, b):
    return a ** b
```

```py
# mypackage/greet.py
# greet.py
def greet_person(firstname, lastname):
    return f'{firstname} {lastname}, welcome to 30DaysOfPython Challenge!'
```

Paketinin klasör yapısı bu şekilde gözükmeli:

```sh
─ mypackage
    ├── __init__.py
    ├── arithmetic.py
    └── greet.py
```

Python interactive shelli açalım ve oluşturduğumuz paketi deneyelim:

```sh
asabeneh@Asabeneh:~/Desktop/30DaysOfPython$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> from mypackage import arithmetics
>>> arithmetics.add_numbers(1, 2, 3, 5)
11
>>> arithmetics.subtract(5, 3)
2
>>> arithmetics.multiple(5, 3)
15
>>> arithmetics.division(5, 3)
1.6666666666666667
>>> arithmetics.remainder(5, 3)
2
>>> arithmetics.power(5, 3)
125
>>> from mypackage import greet
>>> greet.greet_person('Asabeneh', 'Yetayeh')
'Asabeneh Yetayeh, welcome to 30DaysOfPython Challenge!'
>>>
```

Gördüğün gibi paketimiz mükemmel şekilde çalışıyor. Paket klasörü, **_init_**.py adında özel bir dosya içerir — bu dosya paketin içeriğini saklar. Bir klasörün içine **_init_**.py dosyasını koyduğumuzda, Python o klasörü bir paket olarak tanımaya başlar.

**_init_**.py dosyası, paket içindeki belirli modülleri veya kaynakları diğer Python dosyalarına aktarılabilir hâle getirir. Boş bir **_init_**.py dosyası, paket içe aktarıldığında tüm fonksiyonların kullanılabilir olmasını sağlar.
**_init_**.py dosyası, bir klasörün Python tarafından paket olarak tanınması için gereklidir

### Paketlerle İlgili İleri Bilgiler

- Veri tabanı
  - SQLAlchemy or SQLObject - Farklı veri tabanı sistemlerine nesne tabanlı erişim
    - _pip install SQLAlchemy_
- Web Geliştirme
  - Django - Yüksek seviye web frameworkü
    - _pip install django_
  - Flask - Werkzeug ve Jinja2 üzerine kurulmuş, BSD lisanslı bir Python mikro frameworkü
    - _pip install flask_
- HTML Parser
  - [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) - HTML/XML ayrıştırıcısıdır; özellikle web scraping gibi hızlı dönüş gerektiren projeler için tasarlanmıştır. Hatalı (bozuk) işaretlemeyi bile kabul eder.
    - _pip install beautifulsoup4_
  - PyQuery - Python içinde jQuery benzeri bir sözdizimi sağlar; BeautifulSoup’tan daha hızlı olduğu söylenir.

- XML İşleme (XML Processing)
  - ElementTree - Element tipi, hiyerarşik veri yapıları (örneğin basitleştirilmiş XML verileri) bellekte depolamak için tasarlanmış basit ama esnek bir kapsayıcı nesnedir. Not: Python 2.5 ve üzeri sürümlerde ElementTree, standart kütüphane ile birlikte gelir.
- Grafik Arayüz (GUI)
  - PyQt - Çapraz platform Qt frameworkü için Python bağlamalarıdır.
  - TkInter - Python’un geleneksel kullanıcı arayüzü araç kitidir.
- Veri Analizi, Veri Bilimi ve Makine Öğrenmesi
  - Numpy: Numpy(numeric python), Python’daki en popüler bilimsel hesaplama ve makine öğrenimi kütüphanelerinden biridir.
  - Pandas: Veri analizi, veri bilimi ve makine öğrenimi için yüksek seviyeli veri yapıları ve geniş analiz araçları sağlar.
  - SciPy: Uygulama geliştiriciler ve mühendisler için tasarlanmış bir makine öğrenimi kütüphanesidir. Optimizasyon, lineer cebir, integrasyon, görüntü işleme ve istatistik modülleri içerir.
  - Scikit-Learn: NumPy ve SciPy üzerine inşa edilmiştir. Karmaşık veri ile çalışmak için en güçlü kütüphanelerden biridir.
  - TensorFlow: Google tarafından geliştirilmiş açık kaynaklı bir makine öğrenimi kütüphanesidir.
  - Keras: Nöral ağlarını tanımlamak için kolay bir arayüz sağlar. Model derleme, veri işleme, grafik görselleştirme gibi birçok güçlü yardımcı aracı içerir.
- Ağ Programlama (Network):
  - requests: Sunucuya HTTP istekleri (GET, POST, DELETE, PUT) göndermek için kullanılan bir pakettir.
    - _pip install requests_

🌕 Gelişme kaydediyorsun. 20. günün challenge’larını tamamladın ve mükemmellik yolunda 20 adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## Alıştırmalar: 20. Gün

1. Bu URL’yi oku ve en sık geçen 10 kelimeyi bul: romeo_and_juliet = 'http://www.gutenberg.org/files/1112/1112.txt'
2. Cats API’sını oku: cats_api = 'https://api.thecatapi.com/v1/breeds' ve şunları bul:
   1. Kedilerin kilogram cinsinden ağırlığının min, max, ortalama (mean), medyan ve standart sapmasını
   2. Kedilerin ömür sürelerinin (yıl olarak) min, max, ortalama (mean), medyan ve standart sapmasını
   3. Ülke ve kedi ırkı için frekans tablosu oluştur
3. Countries API’sını oku: [countries API](https://restcountries.eu/rest/v2/all) ve şunları bul:
   1. En büyük 10 ülke
   2. En çok konuşulan 10 dil
   3. Countries API’daki toplam dil sayısı
4. UCI (veri bilimi / makine öğrenmesi için sık kullanılan veri kaynaklarından biri) sitesini oku:(https://archive.ics.uci.edu/ml/datasets.php). Ek kütüphaneler olmadan bu iş zor olabilir; bu yüzden BeautifulSoup4 kullanmayı deneyebilirsin.

🎉 TEBRİKLER ! 🎉

[<< 19. Gün](../19_Day_File_handling/19_file_handling.md) | [21. Gün >>](../21_Day_Classes_and_objects/21_classes_and_objects.md)
