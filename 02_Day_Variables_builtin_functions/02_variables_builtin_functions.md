<div align="center">
  <h1> 30 Günde Python: 2. Gün - Değişkenler, Built-in Fonksiyonlar</h1>
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

[<< 1. Gün](../readme.md) | [3. Gün >>](../03_Day_Operators/03_operators.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 2. Gün](#-day-2)
  - [Built-in fonksiyonlar](#built-in-functions)
  - [Değişkenler](#variables)
    - [Bir Satırda Birden Fazla Değişken Tanımlama](#declaring-multiple-variable-in-a-line)
  - [Veri Tipleri](#data-types)
  - [Veri Tiplerini Kontrol Etmek ve Birbirine Dönüştürmek](#checking-data-types-and-casting)
  - [Sayılar](#numbers)
  - [💻 Alıştırmalar - 2. Gün](#-exercises---day-2)
    - [Alıştırmalar: Level 1](#exercises-level-1)
    - [Alıştırmalar: Level 2](#exercises-level-2)

# 📘 2. Gün

## Built-in Fonksiyonlar

Python'da çok sayıda built-in fonksiyon vardır. Built-in functions are globally available for your use that mean you can make use of the built-in functions without importing or configuring. En yaygın kullanılan built-in fonksiyonlardan bazıları: _print()_, _len()_, _type()_, _int()_, _float()_, _str()_, _input()_, _list()_, _dict()_, _min()_, _max()_, _sum()_, _sorted()_, _open()_, _file()_, _help()_, ve _dir()_. In the following table you will see an exhaustive list of Python built-in functions taken from [python documentation](https://docs.python.org/3.9/library/functions.html).

![Built-in Functions](../images/builtin-functions.png)

Python shell'i açalım ve en yaygın built-in fonksiyonlardan bazılarını kullanmaya başlayalım.

![Built-in functions](../images/builtin-functions_practice.png)

Farklı built-in fonksiyonlarla daha fazla pratik yapalım

![Help and Dir Built in Functions](../images/help_and_dir_builtin.png)

Yukarıdaki terminalde görebildiğiniz üzere Python'da bazı rezerve edilmiş kelimeler var. We do not use reserved words to declare variables or functions. Değişkenleri sonraki bölümde ele alacağız.

I believe, by now you are familiar with built-in functions. Let us do one more practice of built-in functions and we will move on to the next section.

![Min Max Sum](../images/builtin-functional-final.png)

## Değişkenler

Variables store data in a computer memory. Mnemonic variables are recommended to use in many programming languages. A mnemonic variable is a variable name that can be easily remembered and associated. A variable refers to a memory address in which data is stored.
Number at the beginning, special character, hyphen are not allowed when naming a variable. A variable can have a short name (like x, y, z), but a more descriptive name (firstname, lastname, age, country) is highly recommended.

Python Değişken İsmi Kuralları

- Değişken ismi harfle veya alt çizgi karakteriyle başlamak zorundadır
- Değişken ismi sayıyla başlayamaz
- Değişken isimleri sadece harfler, rakamlar ve alt çizgi içerebilir. (A-z, 0-9, and \_ )
- DEĞİŞKEN İSİMLERİ TÜRKÇE KARAKTER İÇEREMEZ. Sadece İngiliz alfabesi harfleri geçerlidir.
- Değişken isimleri büyük harf-küçük harf duyarlıdır (firstname, Firstname, FirstName ve FIRSTNAME) farklı değişkenlerdir)

Geçerli değişken isimlerine örnekler:

```shell
ad
soyad
yas
ulke
sehir
first_name
last_name
capital_city
_if # if we want to use reserved word as a variable
year_2021
year2021
current_year_2021
dogum_yili
num1
num2
```

Geçersiz değişken isimleri

```shell
first-name
first@name
first$name
num-1
1num
```

Biz, Python geliştiricilerinin tercih ettiği standart Python değişken isimlendirme stilini kullanacağız. Python developers use snake case(snake_case) variable naming convention. We use underscore character after each word for a variable containing more than one word(eg. first_name, last_name, engine_rotation_speed). Aşağıdaki örnek değişkenlerin standart isimlendirmesine iyi bir örnek. Birden fazla kelime içeren değişken adları için alt çizgi kullanılması gerekir.

Bir değişkene belli bir değer atadığımızda buna değişken tanımlama denir. For instance in the example below my first name is assigned to a variable first_name. The equal sign is an assignment operator. Assigning means storing data in the variable. The equal sign in Python is not equality as in Mathematics.

_Örnek:_

```py
# Python'da değişkenler
ad = 'Asabeneh'
soyad = 'Yetayeh'
ulke = 'Finland'
sehir = 'Helsinki'
yas = 250
evli_mi = True
beceriler = ['HTML', 'CSS', 'JS', 'React', 'Python']
kisi_biglileri = {
   'ad':'Asabeneh',
   'soyad':'Yetayeh',
   'ulke':'Finland',
   'sehir':'Helsinki'
   }
```

Şimdi _print()_ ve _len()_ built-in fonksiyonlarını kullanalım. Print fonksiyonu sınırsız sayıda argüman alır. An argument is a value which we can be passed or put inside the function parenthesis, see the example below.

**Örnek:**

```py
print('Merhaba, Dünya!') # Merhaba, Dünya! metni bir argümandır
print('Merhaba',',', 'Dünya','!') # Birden fazla argüman alabilir, 4 argüman girilmiş
print(len('Merhaba, Dünya!')) # Tek bir argüman almış
```

Let us print and also find the length of the variables declared at the top:

**Örnek:**

```py
# Printing the values stored in the variables

print('Ad:', ad)
print('Ad uzunluğu:', len(ad))
print('Soyad: ', soyad)
print('Soyad uzunluğu: ', len(soyad))
print('Ülke: ', ulke)
print('Şehir: ', sehir)
print('Yaş: ', yas)
print('Evli mi?: ', evli_mi)
print('Beceriler: ', beceriler)
print('Kişi bilgileri: ', kisi_bilgileri)
```

### Bir Satırda Birden Fazla Değişken Tanımlama

Birden fazla değişken tek bir satırda tanımlanabilir:

**Örnek:**

```py
ad, soyad, ulke, yas, evli_mi = 'Asabeneh', 'Yetayeh', 'Helsink', 250, True

print(ad, soyad, ulke, yas, evli_mi)
print('Ad:', ad)
print('Soyad: ', soyad)
print('Ülke: ', ulke)
print('Yaş: ', yas)
print('Evli mi?: ', evli_mi)
```

Getting user input using the _input()_ built-in function. Let us assign the data we get from a user into first_name and age variables.
**Örnek:**

```py
ad = input('Adınız ne?: ')
yas = input('Kaç yaşındasınız? ')

print(ad)
print(yas)
```

## Veri Tipleri

There are several data types in Python. To identify the data type we use the _type_ built-in function. I would like to ask you to focus on understanding different data types very well. When it comes to programming, it is all about data types. I introduced data types at the very beginning and it comes again, because every topic is related to data types. We will cover data types in more detail in their respective sections.

## Veri Tiplerini Kontrol Etmek ve Birbirine Dönüştürmek

- Check Data types: To check the data type of certain data/variable we use the _type_
  **Örnekler:**

```py
# Farklı Python veri tipleri
# Let's declare variables with various data types

first_name = 'Asabeneh'     # str
last_name = 'Yetayeh'       # str
country = 'Finland'         # str
city= 'Helsinki'            # str
age = 250                   # int, it is not my real age, don't worry about it

# Printing out types
print(type('Asabeneh'))          # str
print(type(first_name))          # str
print(type(10))                  # int
print(type(3.14))                # float
print(type(1 + 1j))              # complex
print(type(True))                # bool
print(type([1, 2, 3, 4]))        # list
print(type({'name':'Asabeneh'})) # dict
print(type((1,2)))               # tuple
print(type(zip([1,2],[3,4])))    # zip
```

- Casting: Converting one data type to another data type. We use _int()_, _float()_, _str()_, _list_, _set_
  When we do arithmetic operations string numbers should be first converted to int or float otherwise it will return an error. If we concatenate a number with a string, the number should be first converted to a string. We will talk about concatenation in String section.

  **Örnekler:**

```py
# int to float
num_int = 10
print('num_int',num_int)         # 10
num_float = float(num_int)
print('num_float:', num_float)   # 10.0

# float to int
gravity = 9.81
print(int(gravity))             # 9

# int to str
num_int = 10
print(num_int)                  # 10
num_str = str(num_int)
print(num_str)                  # '10'

# str to int or float
num_str = '10.6'
num_float = float(num_str)
print('num_float', float(num_str))  # 10.6
num_int = int(num_float)
print('num_int', int(num_int))      # 10

# str to list
first_name = 'Asabeneh'
print(first_name)               # 'Asabeneh'
first_name_to_list = list(first_name)
print(first_name_to_list)            # ['A', 's', 'a', 'b', 'e', 'n', 'e', 'h']
```

## Sayılar

Python'daki sayısal veri tipleri:

1. Integers: Tam sayılar(negatif, sıfır ve pozitif)
   Örnek:
   ... -3, -2, -1, 0, 1, 2, 3 ...

2. Floating Point Numbers(Ondalık sayılar)
   Örnek:
   ... -3.5, -2.25, -1.0, 0.0, 1.1, 2.2, 3.5 ...

3. Complex Numbers(Karmaşık sayılar)
   Örnek:
   1 + j, 2 + 4j, 1 - 1j

🌕 Harikasınız. Challenge'ın 2. gününü tamamladınız ve başarıya doğru ilerliyorsunuz. Now do some exercises for your brain and muscles.

## 💻 Alıştırmalar - 2. Gün

### Alıştırmalar: Level 1

1. 30GündePython klasörünün içinde gun_2 adlı bir klasör oluşturun. gun_2 klasöründe degiskenler.py adında bir python dosyası oluşturun.
2. '2. Gün : 30 Günde Python programlama'yazan bir Python yorumu yazın
3. Bir ad değişkeni tanımlayıp bir değer atayın
4. Bir soyad değişkeni tanımlayıp bir değer atayın
5. Bir tam ad değişkeni tanımlayıp bir değer atayın
6. Bir ülke değişkeni tanımlayıp bir değer atayın
7. Bir şehir değişkeni tanımlayıp bir değer atayın
8. Bir yaş değişkeni tanımlayıp bir değer atayın
9. Bir yıl değişkeni tanımlayıp bir değer atayın
10. Declare a variable is_married and assign a value to it
11. Declare a variable is_true and assign a value to it
12. Declare a variable is_light_on and assign a value to it
13. Bir satırda birden çok değişken tanımlayın

### Alıştırmalar: Level 2

1. Built-in type() fonksiyonunu kullanarak tüm değişkenlerinizin veri tipini kontrol edin
1. Built-in _len()_ fonksiyonunu kullanarak adınızın uzunluğunu bulun
1. Compare the length of your first name and your last name
1. Declare 5 as num_one and 4 as num_two
1. num_one ve num_two değişkenlerini toplayıp sonucu toplam değişkenine atayın
1. num_one değişkeninden num_two değişkenini çıkarıp sonucu fark değişkenine atayın
1. num_one ve num_two değişkenlerini çarpıp sonucu carpim değişkenine atayın
1. Divide num_one by num_two and assign the value to a variable division
1. Mod alma operatörünü kullanrak num_one değişkeninin num_two değişkenine bölümünden kalanı bulun ve kalan değişkenine atayın
1. Calculate num_one to the power of num_two and assign the value to a variable exp
1. Find floor division of num_one by num_two and assign the value to a variable floor_division
1. Bir dairenin yarıçapı 30 metredir.
    1. Bu dairenin alanını hesaplayıp _daire_alani_ adlı bir değişkene atayın
    2. Bu dairenin çevresini hesaplayıp _daire_cevresi_ adlı bir değişkene atayın
    3. Take radius as user input and calculate the area.
1. Kullanıcıdan ad, soyad, ülke ve yaş değerlerini almak için built-in input fonksiyonlarını kullanın ve değerleri ilgili değişkenlere atayın
1. Run help('keywords') in Python shell or in your file to check for the Python reserved words or keywords

🎉 TEBRİKLER ! 🎉

[<< 1. Gün](../readme.md) | [3. Gün >>](../03_Day_Operators/03_operators.md)
