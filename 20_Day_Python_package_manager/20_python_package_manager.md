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
    - [Further Information About Packages](#further-information-about-packages)
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

As you can see our package works perfectly. The package folder contains a special file called **__init__**.py - it stores the package's content. If we put **__init__**.py in the package folder, python start recognizes it as a package.
The **__init__**.py exposes specified resources from its modules to be imported to other python files. An empty **__init__**.py file makes all functions available when a package is imported. The **__init__**.py is essential for the folder to be recognized by Python as a package.

### Further Information About Packages

- Database
  - SQLAlchemy or SQLObject - Object oriented access to several different database systems
    - _pip install SQLAlchemy_
- Web Development
  - Django - High-level web framework.
    - _pip install django_
  - Flask - micro framework for Python based on Werkzeug, Jinja 2. (It's BSD licensed)
    - _pip install flask_
- HTML Parser
  - [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) - HTML/XML parser designed for quick turnaround projects like screen-scraping, will accept bad markup.
    - _pip install beautifulsoup4_
  - PyQuery - implements jQuery in Python; faster than BeautifulSoup, apparently.

- XML Processing
  - ElementTree - The Element type is a simple but flexible container object, designed to store hierarchical data structures, such as simplified XML infosets, in memory. --Note: Python 2.5 and up has ElementTree in the Standard Library
- GUI
  - PyQt - Bindings for the cross-platform Qt framework.
  - TkInter - The traditional Python user interface toolkit.
- Data Analysis, Data Science and Machine learning
  - Numpy: Numpy(numeric python) is known as one of the most popular machine learning library in Python.
  - Pandas: is a data analysis, data science and a machine learning library in Python that provides data structures of high-level and a wide variety of tools for analysis.
  - SciPy: SciPy is a machine learning library for application developers and engineers. SciPy library contains modules for optimization, linear algebra, integration, image processing, and statistics.
  - Scikit-Learn: It is NumPy and SciPy. It is considered as one of the best libraries for working with complex data.
  - TensorFlow: is a machine learning library built by Google.
  - Keras: is considered as one of the coolest machine learning libraries in Python. It provides an easier mechanism to express neural networks. Keras also provides some of the best utilities for compiling models, processing data-sets, visualization of graphs, and much more.
- Network:
  - requests: is a package which we can use to send requests to a server(GET, POST, DELETE, PUT)
    - _pip install requests_

🌕 You are always progressing and you are a head of 20 steps to your way to greatness. Now do some exercises for your brain and muscles.

## Alıştırmalar: 20. Gün

1. Read this url and find the 10 most frequent words. romeo_and_juliet = 'http://www.gutenberg.org/files/1112/1112.txt'
2. Read the cats API and cats_api = 'https://api.thecatapi.com/v1/breeds' and find :
   1. the min, max, mean, median, standard deviation of cats' weight in metric units.
   2. the min, max, mean, median, standard deviation of cats' lifespan in years.
   3. Create a frequency table of country and breed of cats
3. Read the [countries API](https://restcountries.eu/rest/v2/all) and find
   1. the 10 largest countries
   2. the 10 most spoken languages
   3. the total number of languages in the countries API
4. UCI is one of the most common places to get data sets for data science and machine learning. Read the content of UCL (https://archive.ics.uci.edu/ml/datasets.php). Without additional libraries it will be difficult, so you may try it with BeautifulSoup4

🎉 TEBRİKLER ! 🎉

[<< 19. Gün](../19_Day_File_handling/19_file_handling.md) | [21. Gün >>](../21_Day_Classes_and_objects/21_classes_and_objects.md)
