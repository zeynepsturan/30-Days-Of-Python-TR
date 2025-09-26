# 🐍 30 Günde Python

  <strong> Yaklaşan [<em>CODING BOOTCAMP</em>](https://docs.google.com/forms/d/e/1FAIpQLSf0oNIYR9XU1DCctfl-pY36KbWse-SQX5aQaUgetqSinFYnmQ/viewform)'e katılarak Asebeneh ile öğren </strong>

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
| 09  |  [Conditionals](./09_Day_Conditionals/09_conditionals.md)|
| 10  |  [Döngüler](./10_Day_Loops/10_loops.md)|
| 11  |  [Fonksiyonlar](./11_Day_Functions/11_functions.md)|
| 12  |  [Modüller](./12_Day_Modules/12_modules.md)|
| 13  |  [List Oluşturma Kısayolu](./13_Day_List_comprehension/13_list_comprehension.md)|
| 14  |  [Yüksek Mertebe Fonksiyonlar](./14_Day_Higher_order_functions/14_higher_order_functions.md)|
| 15  |  [Python Veri Tipi Hataları](./15_Day_Python_type_errors/15_python_type_errors.md)|
| 16 |  [Python'da Tarih ve Zaman](./16_Day_Python_date_time/16_python_datetime.md) |
| 17 |  [Exception Handling](./17_Day_Exception_handling/17_exception_handling.md)|
| 18 |  [Regular Expressions](./18_Day_Regular_expressions/18_regular_expressions.md)|
| 19 |  [Dosya İşlemleri](./19_Day_File_handling/19_file_handling.md)|
| 20 |  [Python Package Manager](./20_Day_Python_package_manager/20_python_package_manager.md)|
| 21 |  [Classlar ve Objeler](./21_Day_Classes_and_objects/21_classes_and_objects.md)|
| 22 |  [Web Scraping](./22_Day_Web_scraping/22_web_scraping.md)|
| 23 |  [Virtual Environment](./23_Day_Virtual_environment/23_virtual_environment.md)|
| 24 |  [İstatistik](./24_Day_Statistics/24_statistics.md)|
| 25 |  [Pandas](./25_Day_Pandas/25_pandas.md)|
| 26 |  [Python web](./26_Day_Python_web/26_python_web.md)|
| 27 |  [MongoDB ile Python](./27_Day_Python_with_mongodb/27_python_with_mongodb.md)|
| 28 |  [API](./28_Day_API/28_API.md)|
| 29 |  [API Oluşturma](./29_Day_Building_API/29_building_API.md)|
| 30 |  [Kapanış](./30_Day_Conclusions/30_conclusions.md)|

  <strong> Yaklaşan [<em>CODING BOOTCAMP</em>](https://docs.google.com/forms/d/e/1FAIpQLSf0oNIYR9XU1DCctfl-pY36KbWse-SQX5aQaUgetqSinFYnmQ/viewform)'e katılarak Asebeneh ile öğren </strong>

🧡🧡🧡 HAPPY CODING 🧡🧡🧡

<div>
<small>Daha fazla eğitim içeriği için <strong>yazara</strong> destek olun.</small> <br />  
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
  <small> Second Edition: Temmuz, 2021</small>
  </sub>
</div>

🇧🇷 [Portuguese](./Portuguese/README.md)
🇨🇳 [中文](./Chinese/README.md)

[2. Gün >>](./02_Day_Variables_builtin_functions/02_variables_builtin_functions.md)

![30DaysOfPython](./images/30DaysOfPython_banner3@2x.png)

- [🐍 30 Günde Python](#-30-days-of-python)
- [📘 1. Gün](#-day-1)
  - [Hoşgeldiniz](#welcome)
  - [Giriş](#introduction)
  - [Neden Python?](#why-python-)
  - [Geliştirme Ortamının Kurulumu](#environment-setup)
    - [Python'u Yükleme](#installing-python)
    - [Python Shell](#python-shell)
    - [Visual Studio Code'u yükleme](#installing-visual-studio-code)
      - [Visual Studio Code nasıl kullanılır?](#how-to-use-visual-studio-code)
  - [Basic Python](#basic-python)
    - [Python Sözdizimi](#python-syntax)
    - [Python Indentation](#python-indentation)
    - [Yorumlar](#comments)
    - [Veri Tipleri](#data-types)
      - [Sayılar](#number)
      - [String](#string)
      - [Booleans](#booleans)
      - [List](#list)
      - [Dictionary](#dictionary)
      - [Tuple](#tuple)
      - [Set](#set)
    - [Veri Tiplerini Kontrol Etme](#checking-data-types)
    - [Python File](#python-file)
  - [💻 Exercises - Day 1](#-exercises---day-1)
    - [Exercise: Level 1](#exercise-level-1)
    - [Exercise: Level 2](#exercise-level-2)
    - [Exercise: Level 3](#exercise-level-3)

# 📘 1. Gün

## Hoşgeldiniz

_30 günde Python_ programlama challenge'a katılmaya karar verdiğiniz için **tebrikler!** . Bu challenge'da Python programcısı olmak için gerekli olan her şeyi ve programlamanın temel konseptlerini öğreneceksiniz. Challenge sonunda, _30GündePython_ programlama challenge sertifikasını edineceksiniz.

Eğer challenge’a aktif şekilde dahil olmak ve etkileşimde bulunmak isterseniz [30DaysOfPython challenge](https://t.me/ThirtyDaysOfPython) telegram grubuna katılabilirsiniz.  

## Giriş

Python, genel amaçlı programlama için kullanılan yüksek seviyeli(high-level) bir programlama dilidir. Python Hollandalı programcı Guido van Rossum tarafından yaratılan açık kaynak, yorumlanan(interpreted), nesne yönelimli bir yazılım dilidir. Dilin adı, Britanya yapımı bir skeç komedi dizisi olan *Monty Python's Flying Circus*'tan türetilmiştir ve ilk versiyonu 20 Şubat 1991'de yayımlanmıştır. 30 günde Python challenge Python'un en yeni versiyonu Python 3'ü adım adım öğrenmenize yardımcı olacak. Konu başlıkları 30 güne bölünmüştür ve her bir gün; kolay anlaşılır açıklamalar, gerçek dünya örnekleri, uygulamalı alıştırmalar ve projeler içeren birden fazla bölümden oluşur.

Bu challenge python programlama dilini öğrenmek isteyen yeni başlayanlar ve profesyoneller için tasarlandı. Challenge’ı tamamlamak 30 ila 100 gün sürebilir. Telegram grubuna aktif olarak katılan kişilerin challenge’ı tamamlama olasılığı oldukça yüksektir.

Bu challenge, okuması kolay, sohbet tarzı bir dille yazılmış, ilgi çekici, motive edici ve aynı zamanda oldukça zorlayıcıdır. Bu challengeı tamamlamak için oldukça bolca zaman ayırmalısınız. Eğer görsel bir öğreniciyseniz, video dersine şu adresten ulaşabilirsiniz: <a href="https://www.youtube.com/channel/UC7PNRuno1rzYPb1xLa4yktw"> Washera</a> YouTube kanalı. You may start from [Python for Absolute Beginners video](https://youtu.be/OCCWZheOesI). Kanalı abone olun, YouTube videolarına yorumlar yapın ve sorular sorup aktif olun; yazar sonunda sizi fark edecektir.

Yazar, bu challenge hakkındaki görüşlerinizi duymaktan memnuniyet duyar.
30GündePython challengeı hakkında düşüncelerinizi paylaşarak yazara destek olun. Görüşlerinizi/deneyimlerinizi bu [bağlantı](https://www.asabeneh.com/testimonials) ile iletebilirsiniz.

## Neden Python?

Konuşma diline çok yakın bir dil olduğu için öğrenmesi ve uygulaması kolay bir dildir. Python çeşitli endüstriler ve şirketlerde(Google dahil olmak üzere) sıkça kullanılır.
It has been used to develop web applications, desktop applications, system administration, and machine learning libraries. Python is a highly embraced language in the data science and machine learning community. Umarım bu bilgiler sizi Python öğrenmeye ikna etmiştir. Python is eating the world and you are killing it before it eats you.

## Geliştirme Ortamının Kurulumu

### Python'u Yükleme

Bir Python kodunu çalıştırabilmek için Python'u yüklemelisiniz. Hadi Python'u [yükleyelim](https://www.python.org/).
Windows kullanıcısı iseniz kırmızı içine alınan butona tıklayınız.

[![installing on Windows](./images/installing_on_windows.png)](https://www.python.org/)

macOS kullanıcısı iseniz kırmızı içine alınan butona tıklayınız.

[![installing on Windows](./images/installing_on_macOS.png)](https://www.python.org/)

Python’un cihazınıza yüklü olup olmadığını kontrol etmek için, terminalinize aşağıdaki komutu yazın.

```shell
python --version
```

![Python Version](./images/python_versio.png)

Terminalde de göründüğü üzere şu an _Python 3.7.5_ sürümünü kullanıyorum. Sizin versiyonunuz benimkinden farklı olabilir ama 3.6 veya daha üstü olmalı. Python versiyonunu görebildiyseniz tebrikler, Python makinenize yüklendi. Sonraki bölüme geçebilirsiniz.

### Python Shell

Python yorumlanan(interpreted) bir dildir ve derlenmeye ihtiyaç duymaz. Yani kodu satır satır yorumlayıp çalıştırır. Python, _Python Shell (Python Interactive Shell)_ ile gelir. Python Shell, tek satırlık bir Python kodunu çalıştırıp sonucu elde etmek için kullanılır.

Python Shell kullanıcıdan Python kodu girmesini bekler. Kodu girdiğinizde, kodu yorumlar ve sonucu sonraki satırda gösterir.
Terminalinizi ya da komut satırınızı(cmd) açıp bunu yazın:

```shell
python
```

![Python Scripting Shell](./images/opening_python_shell.png)

Python interactive shell açıldı ve Python kodunuzu(Python script) yazmanızı bekliyor. >>> sembolünün yanına Python script'inizi yazıp Enter'a basarak kodunuzu çalıştırmalısınız.
Şimdi Python Shell'deki ilk kodumuzu yazalım.

![Python script on Python shell](./images/adding_on_python_shell.png)

Tebrikler, Python Interactive Shell'deki ilk kodunuzu yazdınız. How do we close the Python interactive shell ?
Shell'i kapamak için >> sembolünün yanına **exit()** komutunu yazıp Enter'a basın.
![Exit from python shell](./images/exit_from_shell.png)

Now, you know how to open the Python interactive shell and how to exit from it.

Python will give you results if you write scripts that Python understands, if not it returns errors. Let's make a deliberate mistake and see what Python will return.

![Invalid Syntax Error](./images/invalid_syntax_error.png)

As you can see from the returned error, Python is so clever that it knows the mistake we made and which was _Syntax Error: invalid syntax_. Using x as multiplication in Python is a syntax error because (x) is not a valid syntax in Python. Instead of (**x**) we use asterisk (*) for multiplication. The returned error clearly shows what to fix.

The process of identifying and removing errors from a program is called _debugging_. Let us debug it by putting * in place of **x**.

![Fixing Syntax Error](./images/fixing_syntax_error.png)

Our bug was fixed, the code ran and we got a result we were expecting. As a programmer you will see such kind of errors on daily basis. It is good to know how to debug. To be good at debugging you should understand what kind of errors you are facing. Some of the Python errors you may encounter are _SyntaxError_, _IndexError_, _NameError_, _ModuleNotFoundError_, _KeyError_, _ImportError_, _AttributeError_, _TypeError_, _ValueError_, _ZeroDivisionError_ etc. We will see more about different Python **_error types_** in later sections.

Let us practice more how to use Python interactive shell. Go to your terminal or command prompt and write the word **python**.

![Python Scripting Shell](./images/opening_python_shell.png)

Python interactive shell açıldı. Şimdi herhangi bir Python kodu yazmadan önce basit matematik işlemleri (toplama, çıkarma, çarpma, bölme, mod alma, üs alma) yapalım:

- 2 + 3 5'tir
- 3 - 2 1'dir
- 3 \* 2 6'dır
- 3 / 2 1.5'tir
- 3 ** 2 ile 3 * 3 aynı şeydir

In python we have the following additional operations:

- 3 % 2 = 1 => which means finding the remainder
- 3 // 2 = 1 => which means removing the remainder

Şimdi yukarıdaki işlemleri Python koduna çevirelim. The Python shell has been opened and let us write a comment at the very beginning of the shell.

_Yorumlar_ is a part of the code which is not executed by python. Yani kodumuzun daha okunaklı olması için açıklayıcı yorumlar bırakabiliriz. Python does not run the comment part. Python'da yorumlar # sembolüyle başlar.
Python'da yorumlar işte bu şekilde yazılır

```shell
 # yorumlar # işareti ile başlar
 # bu bir python yorumu çünkü (#) işareti ile başlıyor
```

![Maths on python shell](./images/maths_on_python_shell.png)

Sonraki bölüme geçmeden önce, Python interactive shell'de biraz alıştırma yapalım. Shell'i kapamak için _exit()_ komutunu yazın ve sonrasında tekrar açın. let us practice how to write text on the Python shell.

![Writing String on python shell](./images/writing_string_on_shell.png)

### Visual Studio Code'u yükleme

Python interactive shell ufak kodları denemek için uygundur ama büyük projeler için kullanılmaz. Gerkçek iş ortamlarında, geliştiriciler kod yazmak için farklı kod editörleri kullanır. 30 günde Python programlama challenge'ında Visual Studio Code kullanıyor olacağız. Visual studio code is a very popular open source text editor. I am a fan of vscode and I would recommend to [download](https://code.visualstudio.com/) visual studio code, but farklı editörler kullanmak istiyorsanız kendi editörünüzle de devam edebilirsiniz.

[![Visual Studio Code](./images/vscode.png)](https://code.visualstudio.com/)

If you installed visual studio code, let us see how to use it.
If you prefer a video, you can follow this Visual Studio Code for Python [Video tutorial](https://www.youtube.com/watch?v=bn7Cx4z-vSo)

#### Visual Studio Code nasıl kullanılır?

Open the visual studio code by double clicking the visual studio icon. When you open it you will get this kind of interface. Try to interact with the labeled icons.

![Visual studio Code](./images/vscode_ui.png)

Create a folder named 30DaysOfPython on your desktop. Then open it using visual studio code.

![Opening Project on Visual studio](./images/how_to_open_project_on_vscode.png)

![Opening a project](./images/opening_project.png)

After opening it dosya ve klasör oluşturmak için kısayollar göreceksiniz. inside of 30GündePython project's directory. As you can see below, I have created the very first file, helloworld.py. You can do the same.

![Creating a python file](./images/helloworld.png)

Kodlamayla dolu uzun bir günden sonra editörü kapatmak isteyeceksiniz, değil mi? This is how you will close the opened project.

![Closing project](./images/closing_opened_project.png)

Congratulations, you have finished setting up the development environment. Let us start coding.

## Python Temelleri

### Python Sözdizimi

A Python script can be written in Python interactive shell or in the code editor. A Python file has an extension .py.

### Python Indentation

An indentation is a white space in a text. Indentation in many languages is used to increase code readability; however, Python uses indentation to create blocks of code. In other programming languages, curly brackets are used to create code blocks instead of indentation. One of the common bugs when writing Python code is incorrect indentation.

![Indentation Error](./images/indentation.png)

### Yorumlar

Comments play a crucial role in enhancing code readability and allowing developers to leave notes within their code. In Python, any text preceded by a hash (#) symbol is considered a comment and is not executed when the code runs.

**Example: Single Line Comment**

```shell
    # Bu birinci yorum
    # Bu ikinci yorum
    # Python is eating the world
```

**Example: Çok Satırlı Yorumlar**

Triple quote can be used for multiline comment if it is not assigned to a variable

```shell
"""Bu bir çok satırlı
yorum. Birden çok satırı kapsıyor.
python is eating the world
"""
```

### Veri Tipleri

In Python there are several types of data types. Let us get started with the most common ones. Different data types will be covered in detail in other sections. For the time being, let us just go through the different data types and get familiar with them. You do not have to have a clear understanding now.

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

A collection of one or more characters under a single or double quote. If a string is more than one sentence then we use a triple quote.

**Örnek:**

```py
'Asabeneh'
'Finland'
'Python'
'Öğretmeyi seviyorum'
'Umarım 30DaysOfPython Challengeın ilk gününden keyif alıyorsunuzdur '
```

#### Booleans

A boolean data type is either a True or False value. T and F should be always uppercase.

**Örnek:**

```python
    True  #  Işık açık mı? Açıksa, then the value is True
    False # Işık açık mı? Kapalıysa, then the value is False
```

#### List

Python list is an ordered collection which allows to store different data type items. A list is similar to an array in JavaScript.

**Örnek:**

```py
[0, 1, 2, 3, 4, 5]  # all are the same data types - a list of numbers
['Banana', 'Orange', 'Mango', 'Avocado'] # all the same data types - a list of strings (fruits)
['Finland','Estonia', 'Sweden','Norway'] # all the same data types - a list of strings (countries)
['Banana', 10, False, 9.81] # different data types in the list - string, integer, boolean and float
```

#### Dictionary

A Python dictionary object is an unordered collection of data in a key value pair format.

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

A tuple is an ordered collection of different data types like list but tuples can not be modified once they are created. They are immutable.

**Örnek:**

```py
('Asabeneh', 'Pawel', 'Brook', 'Abraham', 'Lidiya') # Names
```

```py
('Earth', 'Jupiter', 'Neptune', 'Mars', 'Venus', 'Saturn', 'Uranus', 'Mercury') # gezegenler
```

#### Set

A set is a collection of data types similar to list and tuple. Unlike list and tuple, set is not an ordered collection of items. Like in Mathematics, set in Python stores only unique items.

İlerleyen kısımlarda bütün Python veri tiplerini detaylıca göreceğiz.

**Örnek:**

```py
{2, 4, 3, 5}
{3.14, 9.81, 2.7} # order is not important in set
```

### Veri Tiplerini Kontrol Etme

Bir verinin/değişkenin veri tipini kontrol etmek için **type** fonksiyonunu kullanırız. In the following terminal you will see different python data types:

![Checking Data types](./images/checking_data_types.png)

### Python File

Öncelikle 30GündePython klasörünüzü açın. If you don't have this folder, 30GündePython adında bir klasör oluşturun. Inside this folder, create a file called helloworld.py. Now, let's do what we did on python interactive shell using visual studio code.

The Python interactive shell was printing without using **print** but on visual studio code to see our result we should use a built in function _print(). The _print()_ built-in function takes one or more arguments as follows _print('arument1', 'argument2', 'argument3')_. See the examples below.

**Örnek:**

The file name is helloworld.py

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

To run the python file check the image below. You can run the python file either by running the green button on Visual Studio Code or by typing _python helloworld.py_ in the terminal .

![Running python script](./images/running_python_script.png)

🌕  Harikasınız. Challenge'ın ilk gününü tamamladınız ve başarıya doğru ilerliyorsunuz. Now do some exercises for your brain and muscles.

## 💻 Exercises - 1. Gün

### Alıştırma: Level 1

1. Check the python version you are using
2. Open the python interactive shell and do the following operations. The operands are 3 and 4.
   - addition(+)
   - subtraction(-)
   - multiplication(\*)
   - modulus(%)
   - division(/)
   - exponential(\*\*)
   - floor division operator(//)
3. Write strings on the python interactive shell. The strings are the following:
   - Your name
   - Your family name
   - Your country
   - I am enjoying 30 days of python
4. Check the data types of the following data:
   - 10
   - 9.8
   - 3.14
   - 4 - 4j
   - ['Asabeneh', 'Python', 'Finland']
   - Your name
   - Your family name
   - Your country

### Alıştırma: Level 2

1. 30GündePython klasörünün içinde gün_1 adlı bir klasör oluşturun . gün_1 klasöründe helloworld.py adında bir python dosyası oluşturun ve repeat questions 1, 2, 3 and 4. Remember to use _print()_ when you are working on a python file. Navigate to the directory where you have saved your file, ve çalıştırın.

### Alıştırma: Level 3

1. Farklı Python veri tipleri için örnekler yazın (Integer, Float, Complex, String, Boolean, List, Tuple, Set ve Dictionary).
2. Find an [Euclidian distance](https://en.wikipedia.org/wiki/Euclidean_distance#:~:text=In%20mathematics%2C%20the%20Euclidean%20distance,being%20called%20the%20Pythagorean%20distance.) (2, 3) ve (10, 8) arasındaki 

🎉 TEBRİKLER ! 🎉

[2. Gün >>](./02_Day_Variables_builtin_functions/02_variables_builtin_functions.md)
