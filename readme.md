# 🐍 30 Günde Python

  <strong> Yaklaşan [<em>CODING BOOTCAMP</em>](https://docs.google.com/forms/d/e/1FAIpQLSf0oNIYR9XU1DCctfl-pY36KbWse-SQX5aQaUgetqSinFYnmQ/viewform) 'e katılarak Asebeneh ile öğren </strong>

|# Gün | Konular                                                    |
|------|:---------------------------------------------------------:|
| 01  |  [Giriş](./readme.md)|
| 02  |  [Değişkenler, Built-in Fonksiyonlar](./02_Day_Variables_builtin_functions/02_variables_builtin_functions.md)|
| 03  |  [Operatörler](./03_Day_Operators/03_operators.md)|
| 04  |  [Stringler](./04_Day_Strings/04_strings.md)|
| 05  |  [Listler](./05_Day_Lists/05_lists.md)|
| 06  |  [Tuplelar](./06_Day_Tuples/06_tuples.md)|
| 07  |  [Setler](./07_Day_Sets/07_sets.md)|
| 08  |  [Dictionaryler](./08_Day_Dictionaries/08_dictionaries.md)|
| 09  |  [Koşullu İfadeler](./09_Day_Conditionals/09_conditionals.md)|
| 10  |  [Döngüler](./10_Day_Loops/10_loops.md)|
| 11  |  [Fonksiyonlar](./11_Day_Functions/11_functions.md)|
| 12  |  [Modüller](./12_Day_Modules/12_modules.md)|
| 13  |  [List Oluşturma Kısayolu](./13_Day_List_comprehension/13_list_comprehension.md)|
| 14  |  [Yüksek Mertebe Fonksiyonlar](./14_Day_Higher_order_functions/14_higher_order_functions.md)|
| 15  |  [Python Veri Tipi Hataları](./15_Day_Python_type_errors/15_python_type_errors.md)|
| 16 |  [Python'da Tarih ve Zaman](./16_Day_Python_date_time/16_python_datetime.md) |
| 17 |  [İstisna Yakalama](./17_Day_Exception_handling/17_exception_handling.md)|
| 18 |  [Düzenli İfadeler](./18_Day_Regular_expressions/18_regular_expressions.md)|
| 19 |  [Dosya İşlemleri](./19_Day_File_handling/19_file_handling.md)|
| 20 |  [Python Paket Yöneticisi](./20_Day_Python_package_manager/20_python_package_manager.md)|
| 21 |  [Classlar ve Objeler](./21_Day_Classes_and_objects/21_classes_and_objects.md)|
| 22 |  [Web Scraping](./22_Day_Web_scraping/22_web_scraping.md)|
| 23 |  [Sanal Ortam](./23_Day_Virtual_environment/23_virtual_environment.md)|
| 24 |  [İstatistik](./24_Day_Statistics/24_statistics.md)|
| 25 |  [Pandas](./25_Day_Pandas/25_pandas.md)|
| 26 |  [Python web](./26_Day_Python_web/26_python_web.md)|
| 27 |  [MongoDB ile Python](./27_Day_Python_with_mongodb/27_python_with_mongodb.md)|
| 28 |  [API](./28_Day_API/28_API.md)|
| 29 |  [API Oluşturma](./29_Day_Building_API/29_building_API.md)|
| 30 |  [Kapanış](./30_Day_Conclusions/30_conclusions.md)|

  <strong> Yaklaşan [<em>CODING BOOTCAMP</em>](https://docs.google.com/forms/d/e/1FAIpQLSf0oNIYR9XU1DCctfl-pY36KbWse-SQX5aQaUgetqSinFYnmQ/viewform) 'e katılarak Asebeneh ile öğren </strong>

🧡🧡🧡 İYİ KODLAMALAR 🧡🧡🧡

<div>
<small>Daha fazla eğitim içeriği için <strong>yazara</strong> destek ol.</small> <br />  
<a href = "https://www.paypal.me/asabeneh"><img src='./images/paypal_lg.png' alt='Paypal Logo' style="width:10%"/></a>
</div>

<div align="center">
  <h1> 30 Günde Python: 1. Gün - Giriş</h1>
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

🇧🇷 [Portuguese](./Portuguese/README.md)
🇨🇳 [中文](./Chinese/README.md)

[2. Gün >>](./02_Day_Variables_builtin_functions/02_variables_builtin_functions.md)

![30DaysOfPython](./images/30DaysOfPython_banner3@2x.png)

- [🐍 30 Günde Python](#-30-days-of-python)
- [📘 1. Gün](#-day-1)
  - [Hoşgeldin](#welcome)
  - [Giriş](#introduction)
  - [Neden Python?](#why-python-)
  - [Geliştirme Ortamının Kurulumu](#environment-setup)
    - [Python'u Yükleme](#installing-python)
    - [Python Shell](#python-shell)
    - [Visual Studio Code'u yükleme](#installing-visual-studio-code)
      - [Visual Studio Code nasıl kullanılır?](#how-to-use-visual-studio-code)
  - [Python Temelleri](#basic-python)
    - [Python Sözdizimi](#python-syntax)
    - [Python Girintileri](#python-indentation)
    - [Yorumlar](#comments)
    - [Veri Tipleri](#data-types)
      - [Sayılar](#number)
      - [String](#string)
      - [Boolean](#booleans)
      - [List](#list)
      - [Dictionary](#dictionary)
      - [Tuple](#tuple)
      - [Set](#set)
    - [Veri Tiplerini Kontrol Etme](#checking-data-types)
    - [Python Dosyası Oluşturma](#python-file)
  - [💻 Alıştırmalar - 1. Gün](#-exercises---day-1)
    - [Alıştırma: 1. Seviye](#exercise-level-1)
    - [Alıştırma: 2. Seviye](#exercise-level-2)
    - [Alıştırma: 3. Seviye](#exercise-level-3)

# 📘 1. Gün

## Hoşgeldin

_30 günde Python_ programlama challenge'a katılmaya karar verdiğin için **tebrikler!** Bu challenge'da Python programcısı olmak için gerekli olan her şeyi ve programlamanın temel konseptlerini öğreneceksin. Challenge sonunda, _30GündePython_ programlama challenge sertifikasını edineceksin.

Eğer challenge’a aktif şekilde dahil olmak ve etkileşimde bulunmak istersen [30DaysOfPython challenge](https://t.me/ThirtyDaysOfPython) telegram grubuna katılabilirsin. 

Bu GitHub repository'sinin orijinal dili İngilizce'dir ve [zeynepsturan](https://github.com/zeynepsturan) tarafından Türkçeye çevirilmiştir. Bu yüzden challenge'daki kaynakların ve örnek kodların tamamı İngilizce içeriklidir. 

## Giriş

Python, genel amaçlı programlama için kullanılan yüksek seviyeli (high-level) bir programlama dilidir. Python Hollandalı programcı Guido van Rossum tarafından yaratılan açık kaynak, yorumlanan (interpreted), nesne yönelimli bir yazılım dilidir. Dilin adı, Britanya yapımı bir skeç komedi dizisi olan *Monty Python's Flying Circus*'tan türetilmiştir ve ilk versiyonu 20 Şubat 1991'de yayımlanmıştır. 30 günde Python challenge Python'un en yeni versiyonu Python 3'ü adım adım öğrenmene yardımcı olacak. Konu başlıkları 30 güne bölünmüştür ve her bir gün; kolay anlaşılır açıklamalar, gerçek dünya örnekleri, uygulamalı alıştırmalar ve projeler içeren birden fazla bölümden oluşur.

Bu challenge python programlama dilini öğrenmek isteyen yeni başlayanlar ve profesyoneller için tasarlandı. Challenge’ı tamamlamak 30 ila 100 gün sürebilir. Telegram grubuna aktif olarak katılan kişilerin challenge’ı tamamlama olasılığı oldukça yüksektir.

Bu challenge, okuması kolay, sohbet tarzı bir dille yazılmış, ilgi çekici, motive edici ve aynı zamanda oldukça zorlayıcıdır. Bu challenge'ı tamamlamak için oldukça bolca zaman ayırmalısın. Eğer görsel bir öğreniciysen, video dersine şu adresten ulaşabilirsin: <a href="https://www.youtube.com/channel/UC7PNRuno1rzYPb1xLa4yktw"> Washera</a> YouTube kanalı. Bu videodan başlayabilirsin: [Sıfırdan Başlayanlar için Python video](https://youtu.be/OCCWZheOesI). Kanalı abone ol, YouTube videolarına yorumlar yap ve sorular sorup aktif ol; yazar sonunda seni fark edecektir.

Yazar, bu challenge hakkındaki görüşlerini duymaktan memnuniyet duyar.
30GündePython challenge'ı hakkında düşüncelerini paylaşarak yazara destek ol. Görüşlerini/deneyimlerini bu [bağlantı](https://www.asabeneh.com/testimonials) ile iletebilirsin.

## Neden Python?

Konuşma diline çok yakın bir dil olduğu için öğrenmesi ve uygulaması kolay bir dildir. Python çeşitli endüstriler ve şirketlerde (Google dahil olmak üzere) sıkça kullanılır. Web uygulamaları, masaüstü uygulamaları, sistem yönetimi ve makine öğrenimi kütüphanelerini geliştirmek için kullanılmıştır. Python veri bilimi ve makine öğrenmesi topluluklarında iyice benimsenmiş bir dildir. Umarım bu bilgiler seni Python öğrenmeye ikna etmiştir. Python dünyayı ele geçiriyor ve sen, Python seni ele geçirmeden onu etkili bir şekilde kullanıyorsun.

## Geliştirme Ortamının Kurulumu

### Python'u Yükleme

Bir Python kodunu çalıştırabilmek için önce Python'u yüklemelisin. Hadi Python'u [yükleyelim](https://www.python.org/).
Windows kullanıcısı isen kırmızı içine alınan butona tıkla.

[![installing on Windows](./images/installing_on_windows.png)](https://www.python.org/)

macOS kullanıcısı isen kırmızı içine alınan butona tıkla.

[![installing on Windows](./images/installing_on_macOS.png)](https://www.python.org/)

Python’un cihazında yüklü olup olmadığını kontrol etmek için, terminaline aşağıdaki komutu yaz.

```shell
python --version
```

![Python Version](./images/python_versio.png)

Terminalde de göründüğü üzere şu an _Python 3.7.5_ sürümünü kullanıyorum. Senin versiyonun benimkinden farklı olabilir ama 3.6 veya daha üstü olmalı. Python versiyonunu görebildiysen tebrikler, Python makinene yüklendi. Sonraki bölüme geçebilirsin.

### Python Shell

Python yorumlanan (interpreted) bir dildir ve derlenmeye ihtiyaç duymaz. Yani kodu satır satır yorumlayıp çalıştırır. Python, _Python Shell (Python Interactive Shell)_ ile gelir. Python Shell, tek satırlık bir Python kodunu çalıştırıp sonucu elde etmek için kullanılır.

Python Shell kullanıcıdan Python kodu girmesini bekler. Kodu girdiğinde, kodu yorumlar ve sonucu sonraki satırda gösterir.
Terminalini ya da komut satırını (cmd) açıp bunu yaz:

```shell
python
```

![Python Scripting Shell](./images/opening_python_shell.png)

Python interactive shell açıldı ve Python kodunu (Python script) yazmanı bekliyor. >>> sembolünün yanına Python script'ini yazıp Enter'a basarak kodunu çalıştırmalısın.
Şimdi Python Shell'deki ilk kodumuzu yazalım.

![Python script on Python shell](./images/adding_on_python_shell.png)

Tebrikler, Python Interactive Shell'deki ilk kodunu yazdın. Peki Python interactive shell nasıl kapatılır?
Shell'i kapamak için >> sembolünün yanına **exit()** komutunu yazıp Enter'a bas.

![Exit from python shell](./images/exit_from_shell.png)

Artık Python Shell'i açmayı ve kapamayı biliyorsun.

Python, kodu doğru biçimde yazdığında sonucunu döner. Aksi takdirde ise hatalar döner. Şimdi kasıtlı bir hata yapalım ve Python'un ne döneceğini görelim.

![Invalid Syntax Error](./images/invalid_syntax_error.png)

Dönen hatada gördüğün üzere Python bir hata yaptığımızı ve bunun _Syntax Error: invalid syntax_ olduğunu anlayacak kadar zekidir. Çarpma için x kullanmak Python'da bir söz dizimi hatasıdır çünkü (x) Python'da geçerli bir fonksiyon değildir. Çarpma için (**x**) yerine yıldız işareti (*) kullanırız. Dönen hata, neyin düzeltilmesi gerektiğini açıkça gösterir.

Bir programdaki hataları tespit edip ortadan kaldırmaya _debugging (hata ayıklama)_ denir. Şimdi **x** yerine * koyarak hatamızı debug edelim.

![Fixing Syntax Error](./images/fixing_syntax_error.png)

Hatamız düzeldi, kod çalıştı ve beklediğimiz sonucu aldık. Bir programcı olarak bu tür hataları günlük hayatta göreceksin. Hataları debug etmeyi bilmek önemlidir. Debugging'de iyi olmak için ne tarz hatalarla yüzleştiğini anlayabilmelisin. Karşılaşabileceğin bazı hatalar  _Sözdizimi Hatası(SyntaxError)_, _İndeks Hatası(IndexError)_, _İsim Hatası(NameError)_, _Modül Bulunamadı Hatası(ModuleNotFoundError)_, _Key Hatası(KeyError)_, _İçe Aktarma Hatası(ImportError)_, _Özellik Hatası(AttributeError)_, _Veri Tipi Hatası(TypeError)_, _Değer Hatası(ValueError)_, _Sıfıra Bölme Hatası(ZeroDivisionError)_ vb. İleriki bölümlerde farklı Python **_hatalarını_** detaylı göreceğiz. 

Şimdi Python interactive shell'i kullanmak için biraz daha pratik yapalım. Terminalini veya komut istemcini (cmd) aç ve **python** kelimesini yaz.

![Python Scripting Shell](./images/opening_python_shell.png)

Python interactive shell açıldı. Şimdi herhangi bir Python kodu yazmadan önce basit matematik işlemleri (toplama, çıkarma, çarpma, bölme, mod alma, üs alma) yapalım:

- 2 + 3 5'tir
- 3 - 2 1'dir
- 3 \* 2 6'dır
- 3 / 2 1.5'tir
- 3 ** 2 ile 3 * 3 aynı şeydir

Python'da bu ekstra operasyonlar mevcut:

- 3 % 2 = 1 => kalanı bulmak için kullanılır
- 3 // 2 = 1 => kalanı atarak bölme için kullanılır (tam bölme)

Şimdi yukarıdaki işlemleri Python koduna çevirelim. Önce shell'in başına bir yorum yazalım.

_Yorumlar_ kodun bir parçasıdır ve python tarafından çalıştırılmaz. Yani kodumuzun daha okunaklı olması için açıklayıcı yorumlar bırakabiliriz. Python yorumları görmezden gelir. Python'da yorumlar # sembolüyle başlar.
Python'da yorumlar işte bu şekilde yazılır

```shell
 # yorumlar # işareti ile başlar
 # bu bir python yorumu çünkü (#) işareti ile başlıyor
```

![Maths on python shell](./images/maths_on_python_shell.png)

Sonraki bölüme geçmeden önce, Python interactive shell'de biraz alıştırma yapalım. Shell'i kapamak için _exit()_ komutunu yaz ve sonrasında tekrar aç. Şimdi Python shell'de metin yazma pratiği yapalım.

![Writing String on python shell](./images/writing_string_on_shell.png)

### Visual Studio Code'u yükleme

Python interactive shell ufak kodları denemek için uygundur ama büyük projeler için kullanılmaz. Gerkçek iş ortamlarında, geliştiriciler kod yazmak için farklı kod editörleri kullanır. 30 günde Python programlama challenge'ında Visual Studio Code kullanıyor olacağız. Visual Studio Code çok popüler, açık kaynak bir text editor'dür. Ben de bir VS Code hayranıyım ve Visual Studio Code'u [indirmeni](https://code.visualstudio.com/) öneririm ama farklı editörler kullanmak istiyorsan kendi editörünle de devam edebilirsin.

[![Visual Studio Code](./images/vscode.png)](https://code.visualstudio.com/)

Visual Studio Code'u indirdiysen nasıl kullanıldığına bakalım.
Videolu anlatımı tercih ediyorsan bu Python için Visual Studio Code [Video öğreticiyi](https://www.youtube.com/watch?v=bn7Cx4z-vSo) takip edebilirsin.

#### Visual Studio Code nasıl kullanılır?

Visual Studio ikonuna çift tıklayarak programı açtığında bu tarz bir arayüz göreceksin. Simgelere tıklayarak arayüzü öğrenmeyi dene.

![Visual studio Code](./images/vscode_ui.png)

Masaüstünde 30GundePython adlı bir klasör oluştur ve Visual Studio Code kullanarak klasörü aç.

![Opening Project on Visual studio](./images/how_to_open_project_on_vscode.png)

![Opening a project](./images/opening_project.png)

Klasörü açtıktan sonra dosya ve klasör oluşturmak için kısayollar göreceksin. Aşağıda da gördüğün gibi ilk dosyamı,helloworld.py, oluşturdum. Sen de aynısını yapabilirsin.

![Creating a python file](./images/helloworld.png)

Kodlamayla dolu uzun bir günden sonra editörü kapatmak isteyeceksin, değil mi? Açık proje böyle kapatılır:

![Closing project](./images/closing_opened_project.png)

Tebrikler, geliştirme ortamını kurmayı tamamladın. Şimdi kodlamaya başlayalım.

## Python Temelleri

### Python Sözdizimi

Bir Python script'i, Python interactive shell'de veya bir kod editöründe yazılabilir. Python dosyalarının .py uzantısı vardır.

### Python Girintileri

Girinti (Indentation), bir metindeki boşluktur. Birçok programlama dilinde girinti, kod okunabilirliğini artırmak için kullanılır; ancak Python’da kod blokları oluşturmak için girinti kullanılır.
Diğer programlama dillerinde kod blokları oluşturmak için girinti yerine genellikle küme parantezler {} kullanılır. Python kodu yazarken en yaygın hatalardan biri yanlış girinti kullanımıdır.

![Indentation Error](./images/indentation.png)

### Yorumlar

Yorumlar (Comments), kodun okunabilirliğini artırmada ve geliştiricilerin kod içinde notlar bırakabilmesinde önemli bir rol oynar.
Python’da # (hash) işareti ile başlayan herhangi bir metin, yorum olarak kabul edilir ve kod çalıştırıldığında görmezden gelinir.

**Örnek: Tek Satırlık Yorumlar**

```shell
    # Bu birinci yorum
    # Bu ikinci yorum
    # Python is eating the world
```

**Örnek: Çok Satırlı Yorumlar**

Üçlü tırnak (''' veya """), bir değişkene atanmadığı sürece çok satırlı yorum olarak kullanılabilir.

```shell
"""Bu bir çok satırlı
yorum. Birden çok satırı kapsıyor.
python is eating the world
"""
```

### Veri Tipleri

Python’da birden fazla veri tipi (data type) vardır. Farklı veri türleri diğer bölümlerde detaylı olarak ele alınacaktır. Şu anda hepsini tam olarak anlamak zorunda değilsiniz.
Şimdilik sadece farklı veri türlerine göz atalım ve onlarla tanışalım. Hadi en yaygın olanlarla başlayalım.

#### Sayılar

- Integer: Tam sayılar(negatif, sıfır ve pozitif tam sayılar)
    Örnek:
    ... -3, -2, -1, 0, 1, 2, 3 ...
- Float: Ondalıklı sayılar
    Örnek:
    ... -3.5, -2.25, -1.0, 0.0, 1.1, 2.2, 3.5 ...
- Complex
    Örnek
    1 + j, 2 + 4j

#### String

Tek veya çift tırnak içinde bir veya daha fazla karakterin bir araya gelmiş hâlidir. Eğer bir string birden fazla satır içeriyorsa, üçlü tırnak kullanılır.

**Örnek:**

```py
'Asabeneh'
'Finland'
'Python'
'Öğretmeyi seviyorum'
'Umarım 30DaysOfPython Challenge ilk günden keyif alıyorsunuzdur'
```

#### Booleanlar

Boolean veri tipi, yalnızca True (Doğru) veya False (Yanlış) değerini alabilir. T ve F her zaman büyük harf ile yazılmalıdır.
**Örnek:**

```python
    True  #  Işık açık mı? Açıksa değer True
    False #  Işık açık mı? Kapalıysa değer False
```

#### List

Python'da list, sıralı bir veri koleksiyondur ve farklı veri tiplerinden öğeleri saklamaya olanak tanır. Bir list, JavaScript’teki dizi (array) ile benzerdir.

**Örnek:**

```py
[0, 1, 2, 3, 4, 5]  # hepsi aynı veri tipi - sayılar listesi
['Banana', 'Orange', 'Mango', 'Avocado'] # hepsi aynı veri tipi - string listesi (meyveler)
['Finland','Estonia', 'Sweden','Norway'] # hepsi aynı veri tipi - string listesi (ülkeler)
['Banana', 10, False, 9.81] # farklı veri tipleri içeren list - string, integer, boolean ve float
```

#### Dictionary

Python dictionary, anahtar-değer (key-value) formatında sırasız bir veri koleksiyonudur.

**Örnek:**

```py
{
'first_name':'Asabeneh',
'last_name':'Yetayeh',
'country':'Finland', 
'age':250, 
'is_married':True,
'skills':['JS', 'React', 'Node', 'Python']
}
```

#### Tuple

Tuple, listler gibi farklı veri tiplerinden oluşan sıralı bir koleksiyondur ancak oluşturulduktan sonra değiştirilemezler. Yani **immutable'dır (değiştirilemez).**

**Örnek:**

```py
('Asabeneh', 'Pawel', 'Brook', 'Abraham', 'Lidiya') # isimler
```

```py
('Earth', 'Jupiter', 'Neptune', 'Mars', 'Venus', 'Saturn', 'Uranus', 'Mercury') # gezegenler
```

#### Set

Set, list ve tuple’a benzer bir veri koleksiyonudur. Liste ve tuple’dan farklı olarak, set sıralı bir koleksiyon değildir. Matematikteki kümeler gibi, Python’daki set yalnızca benzersiz (unique) öğeleri saklar.

İlerleyen kısımlarda bütün Python veri tiplerini detaylıca göreceğiz.

**Örnek:**

```py
{2, 4, 3, 5}
{3.14, 9.81, 2.7} # set'te sıra önemli değil
```

### Veri Tiplerini Kontrol Etme

Bir verinin/değişkenin veri tipini kontrol etmek için **type** fonksiyonunu kullanırız. Aşağıdaki terminalde farklı python veri tipleri göreceksin:

![Checking Data types](./images/checking_data_types.png)

### Python Dosyası Oluşturma

Öncelikle 30GundePython klasörünü aç. Klasör henüz yoksa 30GundePython adında bir klasör oluştur. Klasörün içinde helloworld.py adlı bir dosya oluştur. Şimdi şu ana kadar Shell'de yaptıklarımızı Visual Studio Code kullanarak yapalım.

Python interactive shell, print kullanmadan çıktı verebiliyordu; ancak Visual Studio Code’da sonucu görmek için built-in print() fonksiyonunu kullanmamız gerekir.
print() fonksiyonu, bir veya daha fazla argümanı şu şekilde alır: print('argument1', 'argument2', 'argument3')

**Örnek:**

Dosya adı: helloworld.py

```py
# 1. Gün - 30GündePython Challenge

print(2 + 3)             # toplama(+)
print(3 - 1)             # çıkarma(-)
print(2 * 3)             # çarpma(*)
print(3 / 2)             # bölme(/)
print(3 ** 2)            # üs alma(**)
print(3 % 2)             # mod alma(%)
print(3 // 2)            # Floor division operator(//)

# Veri tiplerini kontrol etme
print(type(10))          # Int
print(type(3.14))        # Float
print(type(1 + 3j))      # Complex (karmaşık sayı)
print(type('Asabeneh'))  # String
print(type([1, 2, 3]))   # List
print(type({'name':'Asabeneh'})) # Dictionary
print(type({9.8, 3.14, 2.7}))    # Set
print(type((9.8, 3.14, 2.7)))    # Tuple
```

Python dosyasını çalıştırmak için aşağıdaki görsele bak. Dosyayo Visual Studio Code’daki yeşil butona tıklayarak veya terminalde _python helloworld.py_ yazarak çalıştırabilirsin.
![Running python script](./images/running_python_script.png)

🌕  Harikasın. Challenge'ın ilk gününü tamamladın ve başarıya doğru ilerliyorsun. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar - 1. Gün

### Alıştırma: 1. Seviye

1. Kullandığın python versiyonunu kontrol et
2. 
3. Python interactive shell'i aç ve aşağıdaki operasyonları 3 ve 4 sayıları için uygula.
   - toplama(+)
   - çıkarma(-)
   - çarpma(\*)
   - mod alma(%)
   - bölme(/)
   - üs alma(\*\*)
   - tam(kalansız) bölme(//)
   - 
4. Aşağıdaki stringleri python interactive shell'de yaz.
   - Adın
   - Soyadın
   - Ülken
   - I am enjoying 30 days of python
   - 
5. Aşağıdaki verilerin veri tiplerini kontrol et.
   - 10
   - 9.8
   - 3.14
   - 4 - 4j
   - ['Asabeneh', 'Python', 'Finland']
   - Adın
   - Soyadın
   - Ülken

### Alıştırma: 2. Seviye

1. 30GundePython klasörünün içinde gun_1 adlı bir klasör oluştur. gun_1 klasöründe helloworld.py adında bir python dosyası oluştur ve 1, 2, 3 and 4. soruları tekrarla. Python dosyasında çalışırken print() fonksiyonunu kullanmayı unutma. Dosyanı kaydettiğin klasörü aç ve çalıştır

### Alıştırma: 3. Seviye

1. Farklı Python veri tipleri için örnekler yaz (Integer, Float, Complex, String, Boolean, List, Tuple, Set ve Dictionary)
2. (2, 3) ve (10, 8) arasındaki [Öklid uzaklığını](https://en.wikipedia.org/wiki/Euclidean_distance#:~:text=In%20mathematics%2C%20the%20Euclidean%20distance,being%20called%20the%20Pythagorean%20distance.) bul

🎉 TEBRİKLER ! 🎉

[2. Gün >>](./02_Day_Variables_builtin_functions/02_variables_builtin_functions.md)
