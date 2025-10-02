<div align="center">
  <h1> 30 Günde Python: 14. Gün - Yüksek Mertebe Fonksiyonlar</h1>
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
</div>

[<< 13. Gün](../13_Day_List_comprehension/13_list_comprehension.md) | [15. Gün>>](../15_Day_Python_type_errors/15_python_type_errors.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)
- [📘 14. Gün](#-day-14)
  - [Yüksek Mertebe Fonksiyonlar](#higher-order-functions)
    - [Parametre Olarak Fonksiyon](#function-as-a-parameter)
    - [Dönüş Değeri Olarak Fonksiyon](#function-as-a-return-value)
  - [Python Kapanışlar (Closures)](#python-closures)
  - [Python Dekoratörleri](#python-decorators)
    - [Dekoratör Oluşturma](#creating-decorators)
    - [Tek Bir Fonksiyona Birden Fazla Dekoratör Uygulama](#applying-multiple-decorators-to-a-single-function)
    - [Dekoratör Fonksiyonlarda Parametre Kabul Etme](#accepting-parameters-in-decorator-functions)
  - [Built-in Yüksek Mertebe Fonksiyonlar](#built-in-higher-order-functions)
    - [Python - Map Fonksiyonu](#python---map-function)
    - [Python - Filter Fonksiyonu](#python---filter-function)
    - [Python - Reduce Fonksiyonu](#python---reduce-function)
  - [💻 Alıştırmalar: 14. Gün](#-exercises-day-14)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)
    - [Alıştırmalar: 3. Seviye](#exercises-level-3)

# 📘 14. Gün

## Yüksek Mertebe Fonksiyonlar

Python’da fonksiyonlar üst sınıf vatandaş kabul edilir. Bu, fonksiyonlar üzerinde şu işlemleri yapabileceğimiz anlamına gelir:

- Bir fonksiyon, parametre olarak bir veya daha fazla fonksiyon alabilir
- Bir fonksiyon, başka bir fonksiyonun sonucu olarak geri döndürülebilir
- Bir fonksiyon değiştirilebilir
- Bir fonksiyon bir değişkene atanabilir

Bu bölümde şunları ele alacağız:

1. Fonksiyonları parametre olarak kullanma
2. Bir fonksiyonu başka bir fonksiyondan dönüş değeri olarak döndürme
3. Python closures (kapanışlar) ve dekoratörleri kullanma

### Parametre Olarak Fonksiyon

```py
def sum_numbers(nums):  # normal fonksiyon
    return sum(nums)    # built-in sum'ı üzüyor :( :<

def higher_order_function(f, lst):  # parametre olarak fonksiyon
    summation = f(lst)
    return summation
result = higher_order_function(sum_numbers, [1, 2, 3, 4, 5])
print(result)       # 15
```

### Dönüş Değeri Olarak Fonksiyon

```py
def square(x):          # kare fonksiyonu
    return x ** 2

def cube(x):            # küp fonksiyonu
    return x ** 3

def absolute(x):        # mutlak değer fonksiyonu
    if x >= 0:
        return x
    else:
        return -(x)

def higher_order_function(type): # fonksiyon döndüren yüksek mertebe bir fonksiyon
    if type == 'square':
        return square
    elif type == 'cube':
        return cube
    elif type == 'absolute':
        return absolute

result = higher_order_function('square')
print(result(3))       # 9
result = higher_order_function('cube')
print(result(3))       # 27
result = higher_order_function('absolute')
print(result(-3))      # 3
```

Yukarıdaki örnekte görebileceğin gibi, üst seviye (higher order) fonksiyon, kendisine verilen parametreye bağlı olarak farklı fonksiyonlar döndürüyor.

## Python Kapanışlar (Closures)

Python, iç içe fonksiyonlar tanımlamamıza ve içteki fonksiyonun dıştaki fonksiyonun kapsamına (scope’una) erişmesine izin verir. Buna Closure (kapanış) denir. Closure, bir fonksiyonun başka bir fonksiyonun içinde tanımlanması ve o iç fonksiyonun, kapsayıcı (outer) fonksiyon tarafından return edilmesiyle oluşur. Örneğe bakalım:

**Örnek:**

```py
def add_ten():
    ten = 10
    def add(num):
        return num + ten
    return add

closure_result = add_ten()
print(closure_result(5))  # 15
print(closure_result(10))  # 20
```

## Python Dekoratörleri

Dekoratör, Python’da mevcut bir nesneye yapısını değiştirmeden yeni işlevsellik eklemeyi sağlayan bir tasarım yoludur. Dekoratörler genellikle dekore etmek istediğiniz fonksiyonun tanımından önce çağrılır.

### Dekoratör Oluşturma

Dekoratör fonksiyonu oluşturmak için, içinde bir wrapper (sarmalayıcı) fonksiyon bulunan bir dış fonksiyona ihtiyacımız vardır.

**Example:**

```py
# Normal fonksiyon
def greeting():
    return 'Welcome to Python'
def uppercase_decorator(function):
    def wrapper():
        func = function()
        make_uppercase = func.upper()
        return make_uppercase
    return wrapper
g = uppercase_decorator(greeting)
print(g())          # WELCOME TO PYTHON

## Yukarıdaki örneği dekoratör ile tekrar yazalım

'''Bu dekoratör fonksiyon, bir fonksiyonu parametre olarak alan
yüksek mertebeli (higher-order) bir fonksiyondur.'''

def uppercase_decorator(function):
    def wrapper():
        func = function()
        make_uppercase = func.upper()
        return make_uppercase
    return wrapper
@uppercase_decorator
def greeting():
    return 'Welcome to Python'
print(greeting())   # WELCOME TO PYTHON

```

### Tek Bir Fonksiyona Birden Fazla Dekoratör Uygulama

```py

'''Bu dekoratör fonksiyonları, fonksiyonları parametre
olarak alan yüksek mertebeli (higher order) fonksiyonlardır.'''

# İlk Decorator
def uppercase_decorator(function):
    def wrapper():
        func = function()
        make_uppercase = func.upper()
        return make_uppercase
    return wrapper

# İkinci decorator
def split_string_decorator(function):
    def wrapper():
        func = function()
        splitted_string = func.split()
        return splitted_string

    return wrapper

@split_string_decorator
@uppercase_decorator     # Dekoratörlerde sıranın önemli olduğunu unutmayın — bu durumda .upper() fonksiyonu listlerle çalışmaz.
def greeting():
    return 'Welcome to Python'
print(greeting())   # WELCOME TO PYTHON
```

### Dekoratör Fonksiyonlarda Parametre Kabul Etme

Çoğu zaman fonksiyonlarımızın parametre almasını isteriz, bu yüzden parametre kabul eden bir dekoratör tanımlamamız gerekebilir.

```py
def decorator_with_parameters(function):
    def wrapper_accepting_parameters(para1, para2, para3):
        function(para1, para2, para3)
        print("I live in {}".format(para3))
    return wrapper_accepting_parameters

@decorator_with_parameters
def print_full_name(first_name, last_name, country):
    print("I am {} {}. I love to teach.".format(
        first_name, last_name, country))

print_full_name("Asabeneh", "Yetayeh",'Finland')
```

## Built-in Yüksek Mertebe Fonksiyonlar

Bu bölümde ele aldığımız built-in yüksek mertebe fonksiyonlardan bazıları _map_, _filter_ ve _reduce_’tır.
Lambda fonksiyonları bir parametre olarak geçirilebilir ve lambda fonksiyonlarının en iyi kullanım alanı, map, filter ve reduce gibi fonksiyonlardır.

### Python - Map Fonksiyonu

map() fonksiyonu, bir built-in fonksiyon olup iki parametre alır: bir fonksiyon ve bir iterable (örneğin liste, tuple).

```py
    # sözdizimi
    map(function, iterable)
```

**Örnek:1**

```py
numbers = [1, 2, 3, 4, 5] # iterable
def square(x):
    return x ** 2
numbers_squared = map(square, numbers)
print(list(numbers_squared))    # [1, 4, 9, 16, 25]
# Lets apply it with a lambda function
numbers_squared = map(lambda x : x ** 2, numbers)
print(list(numbers_squared))    # [1, 4, 9, 16, 25]
```

**Örnek:2**

```py
numbers_str = ['1', '2', '3', '4', '5']  # iterable
numbers_int = map(int, numbers_str)
print(list(numbers_int))    # [1, 2, 3, 4, 5]
```

**Örnek:3**

```py
names = ['Asabeneh', 'Lidiya', 'Ermias', 'Abraham']  # iterable

def change_to_upper(name):
    return name.upper()

names_upper_cased = map(change_to_upper, names)
print(list(names_upper_cased))    # ['ASABENEH', 'LIDIYA', 'ERMIAS', 'ABRAHAM']

# lambda fonksiyonu yazalım
names_upper_cased = map(lambda name: name.upper(), names)
print(list(names_upper_cased))    # ['ASABENEH', 'LIDIYA', 'ERMIAS', 'ABRAHAM']
```

Map’in yaptığı şey aslında bir liste üzerinde yineleme (iteration) yapmaktır. Örneğin, isimleri büyük harfe çevirir ve yeni bir liste döndürür.

### Python - Filter Fonksiyonu

_filter()_ fonksiyonu, verilen iterabledaki (örneğin bir liste) her item için belirtilen fonksiyonu çağırır ve fonksiyon iterabledaki her item için bir boolean değer döndürür. Daha sonra fonksiyon, filtreleme kriterlerini karşılayan itemleri döndürür.

```py
    # sözdizimi
    filter(function, iterable)
```

**Örnek:1**

```py
# Lets filter only even nubers
numbers = [1, 2, 3, 4, 5]  # iterable

def is_even(num):
    if num % 2 == 0:
        return True
    return False

even_numbers = filter(is_even, numbers)
print(list(even_numbers))       # [2, 4]
```

**Örnek:2**

```py
numbers = [1, 2, 3, 4, 5]  # iterable

def is_odd(num):
    if num % 2 != 0:
        return True
    return False

odd_numbers = filter(is_odd, numbers)
print(list(odd_numbers))       # [1, 3, 5]
```

```py
# Filter long name
names = ['Asabeneh', 'Lidiya', 'Ermias', 'Abraham']  # iterable
def is_name_long(name):
    if len(name) > 7:
        return True
    return False

long_names = filter(is_name_long, names)
print(list(long_names))         # ['Asabeneh']
```

### Python - Reduce Fonksiyonu

_reduce()_ fonksiyonu functools modülünde tanımlıdır ve bu modülden import etmemiz gerekir. map ve filter gibi iki parametre alır: bir fonksiyon ve bir iterable (üstünde iterasyon yapılabilen bir veri tipi). Ancak _reduce_, diğerleri gibi bir iterable döndürmez; bunun yerine tek bir değer döndürür.

**Örnek:1**

```py
numbers_str = ['1', '2', '3', '4', '5']  # iterable
def add_two_nums(x, y):
    return int(x) + int(y)

total = reduce(add_two_nums, numbers_str)
print(total)    # 15
```

## 💻 Alıştırmalar: 14. Gün

```py
countries = ['Estonia', 'Finland', 'Sweden', 'Denmark', 'Norway', 'Iceland']
names = ['Asabeneh', 'Lidiya', 'Ermias', 'Abraham']
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### Alıştırmalar: 1. Seviye

1. map, filter ve reduce arasındaki farkı açıkla.
2. Yüksek mertebeli fonksiyon (higher order function), closure ve decorator arasındaki farkı açıkla.
3. map, filter veya reduce kullanmaya geçmeden önce bir fonksiyon tanımla, örneklerini göster.
4. countries listi içindeki her ülkeyi for döngüsü ile yazdır.
5. names listi içindeki her ismi for döngüsü ile yazdır.
6. numbers listi içindeki her sayıyı for döngüsü ile yazdır.

### Alıştırmalar: 2. Seviye

1. map kullanarak, countries listindeki her ülkeyi büyük harfe çevirip yeni bir list oluştur.
2. map kullanarak, numbers listindeki her sayıyı karesine çevirip yeni bir list oluştur.
3. map kullanarak, names listindeki her ismi büyük harfe çevir.
4. filter kullanarak, içinde 'land' geçen ülkeleri filtrele.
5. filter kullanarak, tam olarak 6 karakter uzunluğundaki ülkeleri filtrele.
6. filter kullanarak, 6 harf veya daha fazla harften oluşan ülkeleri filtrele.
7. filter kullanarak, 'E' harfi ile başlayan ülkeleri filtrele.
8. Chain two or more list iterators (eg. arr.map(callback).filter(callback).reduce(callback))
9. Declare a function called get_string_lists which takes a list as a parameter and then returns a list containing only string items.
10. reduce kullanarak, numbers listesindeki tüm sayıların toplamını bul.
11. reduce fonksiyonunu kullanarak tüm ülkeleri birleştir ve şu cümleyi üret: "Estonia, Finland, Sweden, Denmark, Norway, and Iceland are north European countries"
12. Bazı ortak harf gruplarını içerenk ülkeleri dönen categorize_countries fonksiyonunu oluştur.([countries list](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/countries.py)  'land', 'ia', 'island', 'stan' gibi).
13. Dictionary dönen bir fonksiyon oluştur. Keyler, ülkelerin isimlerinin baş harfleri olsun. Valueler, o harfle başlayan ülke sayısını göstersin.
14. get_first_ten_countries adında bir fonksiyon tanımla – bu fonksiyon countries.js listesindeki ilk on ülkeyi döndürsün.
15. get_last_ten_countries adında bir fonksiyon tanımla – bu fonksiyon countries listesindeki son on ülkeyi döndürsün.

### Alıştırmalar: 3. Seviye

1. countries_data.py (https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/countries-data.py) dosyasını kullanarak aşağıdaki alıştırmaları yap:
   - Ülkeleri adlarına, başkentlerine, nüfuslarına göre sırala.
   - Konumlarına göre en çok konuşulan 10 dili sırala.
   - En çok nüfusa sahip 10 ülkeyi sırala.

🎉 TEBRİKLER ! 🎉

[<< 13. Gün](../13_Day_List_comprehension/13_list_comprehension.md) | [15. Gün>>](../15_Day_Python_type_errors/15_python_type_errors.md)
