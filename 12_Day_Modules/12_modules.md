<div align="center">
  <h1> 30 Günde Python: 12. Gün - Modüller </h1>
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
</div>

[<< 11. Gün](../11_Day_Functions/11_functions.md) | [13. Gün>>](../13_Day_List_comprehension/13_list_comprehension.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 12. Gün](#-day-12)
  - [Modüller](#modules)
    - [Modül Nedir?](#what-is-a-module)
    - [Modül Oluşturma](#creating-a-module)
    - [Modül Import Etme](#importing-a-module)
    - [Modülden Fonksiyon Import Etme](#import-functions-from-a-module)
    - [Import Functions from a Module and Renaming](#import-functions-from-a-module-and-renaming)
  - [Built-in Modülleri Import Etme](#import-built-in-modules)
    - [OS Modülü](#os-module)
    - [Sys Modülü](#sys-module)
    - [Statistics Modülü](#statistics-module)
    - [Math Modülü](#math-module)
    - [String Modülü](#string-module)
    - [Random Modülü](#random-module)
  - [💻 Alıştırmalar: 12. Gün](#-exercises-day-12)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)
    - [Alıştırmalar: 3. Seviye](#exercises-level-3)

# 📘 12. Gün

## Modüller

### Modül Nedir?

Bir modül, bir uygulamaya dahil edilebilecek bir dizi kod veya fonksiyon içeren bir dosyadır. Bir modül, tek bir değişken, tek bir fonksiyon veya büyük bir kod tabanı içeren bir dosya olabilir.

### Modül Oluşturma

To create a module we write our codes in a python script and we save it as a .py file. Create a file named mymodule.py inside your project folder. Let us write some code in this file.

```py
# mymodule.py file
def generate_full_name(firstname, lastname):
    return firstname + ' ' + lastname
```

Create main.py file in your project directory and import the mymodule.py file.

### Modül Import Etme

To import the file we use the _import_ keyword and the name of the file only.

```py
# main.py file
import mymodule
print(mymodule.generate_full_name('Asabeneh', 'Yetayeh')) # Asabeneh Yetayeh
```

### Import Functions from a Module

We can have many functions in a file and we can import all the functions differently.

```py
# main.py file
from mymodule import generate_full_name, sum_two_nums, person, gravity
print(generate_full_name('Asabneh','Yetayeh'))
print(sum_two_nums(1,9))
mass = 100;
weight = mass * gravity
print(weight)
print(person['firstname'])
```

### Import Functions from a Module and Renaming

During importing we can rename the name of the module.

```py
# main.py file
from mymodule import generate_full_name as fullname, sum_two_nums as total, person as p, gravity as g
print(fullname('Asabneh','Yetayeh'))
print(total(1, 9))
mass = 100;
weight = mass * g
print(weight)
print(p)
print(p['firstname'])
```

## Built-in Modülleri Import Etme

Diğer programlama dillerinde olduğu gibi, Python’da da bir dosya veya fonksiyonu _import_ anahtar kelimesiyle içe aktarabiliriz. Şimdi en çok kullanacağımız ortak modülleri içe aktaralım. Bazı yaygın built-in modüller: _math_, _datetime_, _os_, _sys_, _random_, _statistics_, _collections_, _json_, _re_

### OS Modülü

Python’un _os_ modülünü kullanarak birçok işletim sistemi görevini otomatik olarak gerçekleştirmek mümkündür. Python’daki OS modülü, dizin (klasör) oluşturma, mevcut çalışma dizinini değiştirme ve silme, dizin içeriğini alma, mevcut dizini değiştirme ve tanımlama gibi işlevler sağlar.

```py
# modülü import etme
import os
# dizin oluşturma
os.mkdir('directory_name')
# mevcut dizini değiştirme
os.chdir('path')
# mevcut dizini dönme
os.getcwd()
# klasör silme
os.rmdir()
```

### Sys Modülü

sys modülü, Python çalışma ortamının farklı bölümlerini yönetmek için kullanılan fonksiyonlar ve değişkenler sağlar. sys.argv fonksiyonu, bir Python scriptine komut satırından geçirilen argümanların bir listesini döndürür. Bu listedeki 0. indeksteki öğe her zaman scriptin adıdır, 1. indeksteki item ise komut satırından geçirilen argümandır.

Bir script.py dosyasına örnek:

```py
import sys
#print(sys.argv[0], argv[1],sys.argv[2])  #şunu yazdırır: filename argument1 argument2
print('Welcome {}. Enjoy  {} challenge!'.format(sys.argv[1], sys.argv[2]))
```

Bu scriptin nasıl çalıştığını görmek için komut satırında şunu yazdım:

```sh
python script.py Asabeneh 30DaysOfPython
```

Sonuç:

```sh
Welcome Asabeneh. Enjoy  30DayOfPython challenge! 
```

Bazı faydalı sys komutları:

```py
# sys'den çıkmak için
sys.exit()
# En büyük tamsayı değişkenini öğrenmek için alır
sys.maxsize
# şu anki dosya yolunu elde etmek için
sys.path
# kullanılan python versiyonunu öğrenmek için
sys.version
```

### Statistics Modülü

Statistics modülü, sayısal verilerin matematiksel istatistiklerini hesaplamak için fonksiyonlar sağlar. Bu modülde tanımlı popüler istatistiksel fonksiyonlar: _mean_, _median_, _mode_, _stdev_ vb.

```py
from statistics import * # statistics modülünün tümünü import etme
ages = [20, 20, 4, 24, 25, 22, 26, 20, 23, 22, 26]
print(mean(ages))       # ~22.9
print(median(ages))     # 23
print(mode(ages))       # 20
print(stdev(ages))      # ~2.3
```

### Math Modülü

Matematiksel işlemler ve sabitler içeren bir modül.

```py
import math
print(math.pi)           # 3.141592653589793, pi sabiti
print(math.sqrt(2))      # 1.4142135623730951, karekök
print(math.pow(2, 3))    # 8.0, üs alma fonksiyonu
print(math.floor(9.81))  # 9, tabana yuvarlama
print(math.ceil(9.81))   # 10, tavana yuvarlama
print(math.log10(100))   # 2, 10 tabanlı logaritma
```

Şimdi, matematiksel hesaplamalar yapmamıza yardımcı olacak birçok fonksiyon içeren *math* modülünü içe aktardık. Modülün hangi fonksiyonlara sahip olduğunu görmek için _help(math)_ veya _dir(math)_ kullanabiliriz. Bu, modülde mevcut olan fonksiyonları gösterir. Sadece belirli bir fonksiyonu modülden almak istersek, şu şekilde import edebiliriz:

```py
from math import pi
print(pi)
```

Aynı anda birden fazla fonksiyonu import etmek de mümkün:

```py

from math import pi, sqrt, pow, floor, ceil, log10
print(pi)                 # 3.141592653589793
print(sqrt(2))            # 1.4142135623730951
print(pow(2, 3))          # 8.0
print(floor(9.81))        # 9
print(ceil(9.81))         # 10
print(math.log10(100))    # 2

```

math modülündeki tüm fonksiyonları import etmek için \* kullanabiliriz.

```py
from math import *
print(math.pi)           # 3.141592653589793, pi sabiti
print(math.sqrt(2))      # 1.4142135623730951, karekök
print(math.pow(2, 3))    # 8.0, üs alma fonksiyonu
print(math.floor(9.81))  # 9, tabana yuvarlama
print(math.ceil(9.81))   # 10, tavana yuvarlama
print(math.log10(100))   # 2, 10 tabanlı logaritma
```

Import ettiğimiz fonksiyonun adını değiştirebiliriz:

```py
from math import pi as  PI
print(PI) # 3.141592653589793
```

### String Modülü

String modülü, birçok amaç için faydalı bir modüldür. Aşağıdaki örnek, string modülünün bazı kullanım biçimlerini göstermektedir:

```py
import string
print(string.ascii_letters) # abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
print(string.digits)        # 0123456789
print(string.punctuation)   # !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
```

### Random Modülü

Modül import etmeye aşina oldun. Şimdi bir modül daha import ederek bunu pekiştirelim. _random_ modülünü import edelim; bu modül 0 ile 0.9999… arasında rastgele bir sayı verir. _random_ modülünün birçok fonksiyonu vardır, fakat bu bölümde sadece _random_ ve _randint_ fonksiyonlarını kullanacağız.

```py
from random import random, randint
print(random())   # argüman almaz; 0 ve 0.9999 arası bir değer döner
print(randint(5, 20)) # [5, 20] aralığında rastgele bir integer değer döner
```

🌕 Çok yol kat ettin, devam et! 12. günün challenge’larını tamamladın ve mükemmellik yolunda 12 adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 12. Gün

### Alıştırmalar: 1. Seviye

1. Rastgele altı karakterli bir kullanıcı ID’si üreten random_user_id fonksiyonunu yaz.
   ```py
     print(random_user_id());
     '1ee33d'
   ```
2. Önceki alıştırmayı değiştir. user_id_gen_by_user adında bir fonksiyon tanımla. Fonksiyon parametre almaz, ama input() ile iki argüman alır: birinci argüman, oluşturulacak ID’lerin karakter sayısı; ikinci argüman ise oluşturulacak ID sayısı.
   
```py
print(user_id_gen_by_user()) # kullanıcı girdisi: 5 5
#çıktı:
#kcsy2
#SMFYb
#bWmeq
#ZXOYh
#2Rgxf
   
print(user_id_gen_by_user()) # 16 5
#1GCSgPLMaBAVQZ26
#YD7eFwNQKNs7qXaT
#ycArC5yrRupyG00S
#UbGxOFI7UXSWAyKN
#dIV0SSUTgAdKwStr
```

3. rgb_color_gen isimli bir fonksiyon yaz. Fonksiyon rgb renkler üretecek (0'dan 255'e olan 3 değer).
   
```py
print(rgb_color_gen())
# rgb(125,244,255) - çıktı bu şekilde olmalı
```

### Alıştırmalar: 2. Seviye

1. list_of_hexa_colors fonksiyonunu yaz. Fonksiyon, istenilen sayıda sayıda hexadecimal renk döndürsün. (Hexadecimal renkler, # işaretinden sonra gelen altı onaltılık rakam/harftir. Onaltılık sayı sistemi 16 sembolden oluşur: 0-9 ve alfabenin ilk 6 harfi, a-f. Çıktı örnekleri için görev 6’ya bakabilirsin)
2. list_of_rgb_colors fonksiyonunu yaz. Bu fonksiyon, istediğiniz sayıda RGB rengi bir arrayde döndürsün.
3. generate_colors fonksiyonunu. Bu fonksiyon, istenen sayıda hexa veya rgb renk üretebilsin.

```py
   generate_colors('hexa', 3) # ['#a3e12f','#03ed55','#eb3d2b'] 
   generate_colors('hexa', 1) # ['#b334ef']
   generate_colors('rgb', 3)  # ['rgb(5, 55, 175','rgb(50, 105, 100','rgb(15, 26, 80'] 
   generate_colors('rgb', 1)  # ['rgb(33,79, 176)']
   ```

### Alıştırmalar: 3. Seviye

1. shuffle_list fonksiyonunu yazıp çağır. Bu fonksiyon bir listi parametre olarak alır ve karıştırılmış (shuffle edilmiş) bir list döndürür.
2. Bir fonksiyon yaz: Bu fonksiyon, 0-9 aralığında yedi rastgele sayıdan oluşan bir array döndürsün. Tüm sayılar birbirinden farklı olmalıdır.

🎉 TEBRİKLER ! 🎉

[<< 11. Gün](../11_Day_Functions/11_functions.md) | [13. Gün>>](../13_Day_List_comprehension/13_list_comprehension.md)
