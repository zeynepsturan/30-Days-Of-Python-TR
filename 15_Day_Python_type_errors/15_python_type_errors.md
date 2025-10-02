<div align="center">
  <h1> 30 Günde Python: 15. Gün - Python'da Hatalar </h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

  <sub>Yazar:
  <a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
  <small> Second Edition: Temmuz, 2021</small>
  </sub>
</div>
</div>

[<< 14. Gün](../14_Day_Higher_order_functions/14_higher_order_functions.md) | [16. Gün >>](../16_Day_Python_date_time/16_python_datetime.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)
- [📘 15. Gün](#-day-15)
  - [Python'da Hatalar](#python-error-types)
    - [Sözdizimi Hatası(SyntaxError)](#syntaxerror)
    - [İsim Hatası(NameError)](#nameerror)
    - [İndeks Hatası(IndexError)](#indexerror)
    - [ModuleNotFoundError](#modulenotfounderror)
    - [AttributeError](#attributeerror)
    - [KeyError](#keyerror)
    - [Veri Tipi Hatası(TypeError)](#typeerror)
    - [ImportError](#importerror)
    - [Değer Hatası(ValueError)](#valueerror)
    - [Sıfıra Bölme Hatası(ZeroDivisionError)](#zerodivisionerror)
  - [💻 Alıştırmalar: 15. Gün](#-exercises-day-15)

# 📘 15. Gün

## Python'da Hatalar

Kod yazarken, yazım hatası (typo) veya diğer yaygın hataları yapmak sıkça görülür. Eğer kodumuz çalışmazsa, Python yorumlayıcısı bir mesaj gösterir; bu mesajda sorunun nerede meydana geldiği ve hata türü hakkında bilgi bulunur. Bazen ayrıca olası bir çözüm önerisi de verir. Programlama dillerindeki farklı hata türlerini anlamak, kodumuzu hızlıca hata ayıklamamıza yardımcı olur ve yaptığımız işte daha iyi olmamızı sağlar.

Şimdi en yaygın hata türlerini teker teker inceleyelim. Öncelikle Python interactive shelli açalım. Bilgisayarının terminaline git ve python yaz. Python interactive shell açılacaktır.

### Sözdizimi Hatası(SyntaxError)

**Örnek 1: SyntaxError**

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> print 'hello world'
  File "<stdin>", line 1
    print 'hello world'
                      ^
SyntaxError: Missing parentheses in call to 'print'. Did you mean print('hello world')?
>>>
```

Gördüğün gibi bir _syntaxError_ döndü çünkü parantezi kapamayı unuttuk ve Python hemen çözüm önerisini sundu. Hatayı düzeltelim.

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> print 'hello world'
  File "<stdin>", line 1
    print 'hello world'
                      ^
SyntaxError: Missing parentheses in call to 'print'. Did you mean print('hello world')?
>>> print('hello world')
hello world
>>>
```

Bu bir _SyntaxError'dı_. Düzeltmeden sonra kodumuz sorunsuz bir şekilde çalıştı. Şimdi diğer hata türlerine bakalım.

### İsim Hatası(NameError)

**Örnek 1: NameError**

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> print(age)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'age' is not defined
>>>
```

Yukarıdaki mesajdan da görebileceğin gibi, age isimli değişken tanımlı değil. Evet, bir age değişkeni tanımlamamıştık ama sanki tanımlamışız gibi yazdırmaya çalışıyorduk. Şimdi bunu, değişkeni tanımlayıp bir değer atayarak düzelteceğiz.

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> print(age)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'age' is not defined
>>> age = 25
>>> print(age)
25
>>>
```

Hata türü ise _NameError_ idi. Hatanın ayıklamasını, değişken adını tanımlayarak yaptık.

### İndeks Hatası(IndexError)

**Örnek 1: IndexError**

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> numbers = [1, 2, 3, 4, 5]
>>> numbers[5]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
>>>
```

Yukarıdaki örnekte, Python bir _IndexError_ verdi çünkü listenin yalnızca 0’dan 4’e kadar indeksleri vardı, yani sınırların dışındaydı.

### ModuleNotFoundError

**Örnek 1: ModuleNotFoundError**

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import maths
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'maths'
>>>
```

Yukarıdaki örnekte, kasıtlı olarak math’e fazladan bir s ekledim ve bu nedenle _ModuleNotFoundError_ oluştu. Fazladan s’yi kaldırarak bunu düzeltebiliriz.

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import maths
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'maths'
>>> import math
>>>
```

Düzeltmeyi yaptık, şimdi math modülündeki bazı fonksiyonları kullanabiliriz.

### AttributeError

**Örnek 1: AttributeError**

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import maths
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'maths'
>>> import math
>>> math.PI
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: module 'math' has no attribute 'PI'
>>>
```

Gördüğün gibi, yine bir hata yaptım! pi yerine maths modülünden bir PI fonksiyonunu çağırmaya çalıştım. Bu bir _AttributeError’a_ yol açtı, yani modülde böyle bir fonksiyon yok. Bunu PI’yi pi ile değiştirerek düzeltebiliriz.

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import maths
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'maths'
>>> import math
>>> math.PI
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: module 'math' has no attribute 'PI'
>>> math.pi
3.141592653589793
>>>
```

math modülünden pi'yi çağırdık ve sonucu aldık.

### KeyError

**Örnek 1: KeyError**

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> users = {'name':'Asab', 'age':250, 'country':'Finland'}
>>> users['name']
'Asab'
>>> users['county']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'county'
>>>
```

Gördüğün gibi, dictionary valuesini almak için kullanılan keyin yazımında bir hata vardı. Bu bir _KeyError’dır_ ve çözümü oldukça basittir. Hadi bunu düzeltelim!

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> user = {'name':'Asab', 'age':250, 'country':'Finland'}
>>> user['name']
'Asab'
>>> user['county']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'county'
>>> user['country']
'Finland'
>>>
```

Hatayı debug ettik, kodumuz çalıştı ve çıktımızı aldık.

### Veri Tipi Hatası(TypeError)

**Örnek 1: TypeError**

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 4 + '3'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
>>>
```

Yukarıdaki örnekte bir _TypeError_ döndü çünkü bir sayıya string ekleyemeyiz. İlk çözüm, string’i int veya float’a dönüştürmek olur. Bir diğer çözüm ise sayıyı string’e çevirmektir (sonuç bu durumda '43' olur). Şimdi sorunu çözelim.

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 4 + '3'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
>>> 4 + int('3')
7
>>> 4 + float('3')
7.0
>>>
```

Hata ortadan kaldırıldı ve beklediğimiz sonucu elde ettik.

### ImportError

**Örnek 1: ImportError**

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> from math import power
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ImportError: cannot import name 'power' from 'math'
>>>
```

Math modülünde power adlı bir fonksiyon yok. Doğrusu _pow_. Düzeltilmiş hali:

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> from math import power
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ImportError: cannot import name 'power' from 'math'
>>> from math import pow
>>> pow(2,3)
8.0
>>>
```

### Değer Hatası(ValueError)

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> int('12a')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '12a'
>>>
```

Bu durumda, verilen string’i bir sayıya dönüştüremeyiz çünkü içinde 'a' harfi bulunuyor.

### Sıfıra Bölme Hatası(ZeroDivisionError)

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 1/0
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
>>>
```

Bir sayıyı sıfıra bölemeyiz.

Python hata türlerinden bazılarını işledik. Eğer daha fazlasını öğrenmek istiyorsanız Python dokümantasyonundan Python hatalarını inceleyin. 
Hata türlerini okumada iyiysen, aynı zamanda iyi bir programcı olacaksın.

🌕 Çok iyi ilerliyorsunuz. Challenge'ın 15. gününü tamamladınız ve başarıya giden yolun yarısını tamamladınız.You made it to half way to your way to greatness. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 15. Gün

1. Python interactive shell'inizi açın ve bu bölümde işlenen tüm hataları deneyin.

🎉 TEBRİKLER ! 🎉

[<< 14. Gün](../14_Day_Higher_order_functions/14_higher_order_functions.md) | [16. Gün >>](../16_Day_Python_date_time/16_python_datetime.md)
