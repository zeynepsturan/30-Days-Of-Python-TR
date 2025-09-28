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
<small> İkinci Versiyon: Temmuz, 2021</small>
</sub>

</div>

[<< 1. Gün](../readme.md) | [3. Gün >>](../03_Day_Operators/03_operators.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 2. Gün](#-day-2)
  - [Built-in Fonksiyonlar](#built-in-functions)
  - [Değişkenler](#variables)
    - [Bir Satırda Birden Fazla Değişken Tanımlama](#declaring-multiple-variable-in-a-line)
  - [Veri Tipleri](#data-types)
  - [Veri Tiplerini Kontrol Etmek ve Birbirine Dönüştürmek](#checking-data-types-and-casting)
  - [Sayılar](#numbers)
  - [💻 Alıştırmalar - 2. Gün](#-exercises---day-2)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)

# 📘 2. Gün

## Built-in Fonksiyonlar

Python'da çok sayıda built-in fonksiyon vardır. Built-in fonksiyonlar, kullanımın için global olarak erişilebilir durumdadır; yani bu fonksiyonları herhangi bir modül içe aktarmadan (import) veya ek bir ayar yapmadan kullanabilirsin. En yaygın kullanılan built-in fonksiyonlardan bazıları: _print()_, _len()_, _type()_, _int()_, _float()_, _str()_, _input()_, _list()_, _dict()_, _min()_, _max()_, _sum()_, _sorted()_, _open()_, _file()_, _help()_, ve _dir()_. Aşağıdaki tabloda, Python’un built-in fonksiyonlarının kapsamlı bir listesini göreceksin. Bu liste, [python dokümantasyonu](https://docs.python.org/3.9/library/functions.html)'ndan alınmıştır.

![Built-in Functions](../images/builtin-functions.png)

Python shell'i açalım ve en yaygın built-in fonksiyonlardan bazılarını kullanmaya başlayalım.

![Built-in functions](../images/builtin-functions_practice.png)

Farklı built-in fonksiyonlarla daha fazla pratik yapalım

![Help and Dir Built in Functions](../images/help_and_dir_builtin.png)

Yukarıdaki terminalde görebildiğin üzere Python'da bazı rezerve edilmiş kelimeler var. Bu rezerve edilmiş kelimeleri değişken ve fonksiyon ismi olarak kullanamayız. Değişkenleri sonraki bölümde ele alacağız.

Built-in fonksiyonlara aşinalık edindiğine inanıyorum. Bir alıştırma daha yapıp sonraki bölüme geçelim.

![Min Max Sum](../images/builtin-functional-final.png)

## Değişkenler

Değişkenler, verileri bilgisayarın belleğinde saklar. Birçok programlama dilinde hatırlatıcı (mnemonic) değişkenler kullanılması önerilir.
Hatırlatıcı değişken, kolayca hatırlanabilen ve anlamıyla ilişkilendirilebilen değişken adıdır. Bir değişken, verinin saklandığı bellek adresine karşılık gelir.

Değişken isimlendirilirken başta sayı, özel karakter veya tire (-) kullanılamaz.
Bir değişken kısa bir isme (x, y, z gibi) sahip olabilir, ancak firstname, lastname, age, country gibi daha açıklayıcı adlar kullanılması şiddetle tavsiye edilir.

Python Değişken İsmi Kuralları

- Değişken ismi harfle veya alt çizgi karakteriyle başlamak zorundadır
- Değişken ismi sayıyla başlayamaz
- Değişken isimleri sadece harfler, rakamlar ve alt çizgi içerebilir. (A-z, 0-9, and \_ )
- DEĞİŞKEN İSİMLERİ TÜRKÇE KARAKTER İÇEREMEZ. Sadece İngiliz alfabesi harfleri geçerlidir.
- Değişken isimleri büyük harf-küçük harf duyarlıdır (firstname, Firstname, FirstName ve FIRSTNAME) farklı değişkenlerdir)

Geçerli değişken isimlerine örnekler:

```shell
name
lastname
year
country
city
first_name
last_name
capital_city
_if # rezerve edilmiş bir kelimeyi değişken adı olarak kullanmak istiyorsak
year_2021
year2021
current_year_2021
birth_year
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

Biz ise, Python geliştiricilerinin tercih ettiği standart Python değişken isimlendirme stilini kullanacağız. Python geliştiricileri snake case(snake_case) denen değişken isimlendirme yöntemini kullanır. Birden fazla kelime içeren değişkenlerde araya alt çizgi (_) koyarız (first_name, last_name, engine_rotation_speed vs.). Aşağıdaki örnek değişkenlerin standart isimlendirmesine iyi bir örnek. Birden fazla kelime içeren değişken adları için alt çizgi kullanılması gerekir.

Bir değişkene belli bir değer atadığımızda buna değişken tanımlama denir. Örneğin, aşağıdaki örnekte ismim, first_name adlı bir değişkene atanmıştır. Eşittir işareti (=) bir atama (assignment) operatörüdür. Atama, verinin bir değişkende saklanması anlamına gelir. Python’daki eşittir işareti (=), matematikteki eşitlik anlamına gelmez.

_Örnek:_

```py
# Python'da değişkenler
first_name = 'Asabeneh'
last_name = 'Yetayeh'
country = 'Finland'
city = 'Helsinki'
age = 250
is_married = True
skills = ['HTML', 'CSS', 'JS', 'React', 'Python']
person_info = {
   'first_name':'Asabeneh',
   'last_name':'Yetayeh',
   'country':'Finland',
   'city':'Helsinki'
   }
```

Şimdi _print()_ ve _len()_ built-in fonksiyonlarını kullanalım. Print fonksiyonu sınırsız sayıda argüman alır. Argüman, bir fonksiyonun parantezinin içine aktarılabilen (geçirilebilen) bir değerdir. Aşağıdaki örneğe bakalım.

**Örnek:**

```py
print('Hello, World!') # Hello, World! metni bir argümandır
print('Hello',',', 'World','!') # Birden fazla argüman alabilir, 4 argüman girilmiş
print(len('Hello, World!')) # Tek bir argüman almış
```

Şimdi yukarıdaki değişkenleri yazdıralım ve uzunluklarını bulalum:

**Örnek:**

```py
# Printing the values stored in the variables

print('First name:', first_name)
print('Length of the first name: ', len(first_name))
print('Last name: ', last_name)
print('Length of the last name: ', len(last_Name))
print('Country: ', country)
print('City: ', city)
print('Age: ', age)
print('Is Married?: ', is_married)
print('Skills: ', skills)
print('Person info: ', person_info)
```

### Bir Satırda Birden Fazla Değişken Tanımlama

Birden fazla değişken tek bir satırda tanımlanabilir:

**Örnek:**

```py
first_name, last_name, country, age, is_married = 'Asabeneh', 'Yetayeh', 'Helsink', 250, True

print(first_name, last_name, country, age, is_married)
print('First name:', first_name)
print('Last name: ', last_name)
print('Country: ', country)
print('Age: ', age)
print('Is Married?: ', is_married)
```

Kullanıcıdan girdi almak için  _input()_ built-in fonksiyonu kullanılır. Kullanıcıdan aldığımız veriyi first_name ve age değişkenlerine atayalım.
**Örnek:**

```py
first_name = input('What is your first name?: ')
age = input('How old are you?: ')

print(first_name)
print(age)
```

## Veri Tipleri

Python’da birkaç farklı veri tipi vardır. Bir verinin tipini belirlemek için _type_ built-in fonksiyonunu kullanırız. Farklı veri tiplerini çok iyi anlamaya odaklanmanı özellikle rica ediyorum çünkü programlamanın temeli aslında veri tipleridir. Veri tiplerini başta tanıtmıştım ve burada tekrar karşımıza çıkıyor çünkü ele aldığımız her konu veri tipleriyle ilişkilidir. İlgili bölümlerde veri tiplerini daha ayrıntılı olarak ele alacağız.

## Veri Tiplerini Kontrol Etmek ve Birbirine Dönüştürmek

- Veri Tipi Kontrolü: Verilerin ve değişkenlerin veri tiplerini kontrol etmek için _type_ kullanırız
  **Örnekler:**

```py
# Farklı Python veri tipleri
# Farklı veri tiplerine sahip değişkenler tanımlayalım!

first_name = 'Asabeneh'     # str
last_name = 'Yetayeh'       # str
country = 'Finland'         # str
city= 'Helsinki'            # str
age = 250                   # int, gerçek yaşım bu değil endişelenme

# Veri tiplerini yazdırma
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

- Casting: Bir veri tipini diğerine dönüştürmek. Bunun için _int()_, _float()_, _str()_, _list_, _set_ fonkdiyonlarını kullanırız.
  Aritmetik işlemler yaparken, string (metin) sayıların önce int veya float tipine dönüştürülmesi gerekir;
aksi halde hata döner. Bir sayıyı bir string ile birleştirmek (concatenate) istersek,
sayının önce string tipine dönüştürülmesi gerekir. Birleştirme (concatenation) konusunu String bölümünde ayrıntılı olarak ele alacağız.
  **Örnekler:**

```py
# int -> float
num_int = 10
print('num_int',num_int)         # 10
num_float = float(num_int)
print('num_float:', num_float)   # 10.0

# float -> int
gravity = 9.81
print(int(gravity))             # 9

# int -> str
num_int = 10
print(num_int)                  # 10
num_str = str(num_int)
print(num_str)                  # '10'

# str -> int -> float
num_str = '10.6'
num_float = float(num_str)
print('num_float', float(num_str))  # 10.6
num_int = int(num_float)
print('num_int', int(num_int))      # 10

# str -> list
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

🌕 Harikasın. Challenge'ın 2. gününü tamamladın ve başarıya doğru ilerliyorsun. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar - 2. Gün

### Alıştırmalar: 1. Seviye

1. 30GündePython klasörünün içinde gun_2 adlı bir klasör oluştur. gun_2 klasöründe degiskenler.py adında bir python dosyası oluştur.
2. '2. Gün : 30 Günde Python programlama'yazan bir Python yorumu yaz
3. Bir ad değişkeni tanımlayıp bir değer ata
4. Bir soyad değişkeni tanımlayıp bir değer ata
5. Bir tam ad değişkeni tanımlayıp bir değer ata
6. Bir ülke değişkeni tanımlayıp bir değer ata
7. Bir şehir değişkeni tanımlayıp bir değer ata
8. Bir yaş değişkeni tanımlayıp bir değer ata
9. Bir yıl değişkeni tanımlayıp bir değer ata
10. Declare a variable is_married and assign a value to it
11. Declare a variable is_true and assign a value to it
12. Declare a variable is_light_on and assign a value to it
13. Bir satırda birden çok değişken tanımla

### Alıştırmalar: 2. Seviye

1. Built-in type() fonksiyonunu kullanarak tüm değişkenlerinizin veri tipini kontrol et
2. Built-in _len()_ fonksiyonunu kullanarak adınızın uzunluğunu bul
3. Adın ve soyadının uzunluklarını karşılaştır
4. num_one değişkenini 5, num_two değişkenini 4 olarak tanımla
5. num_one ve num_two değişkenlerini toplayıp sonucu total değişkenine ata
6. num_one değişkeninden num_two değişkenini çıkarıp sonucu diff değişkenine ata
7. num_one ve num_two değişkenlerini çarpıp sonucu product değişkenine ata
8. num_one değişkenini num_two değişkenine bölün ve sonucu division değişkenine ata
9. Mod alma operatörünü kullanrak num_one değişkeninin num_two değişkenine bölümünden kalanı bul ve kalan değişkenine ata
10. num_one üzeri num_two sonucunu hesapla ve exp adlı bir değişkene ata
11. num_one’ın num_two’ya göre taban bölmesini (floor division) bul ve sonucu floor_division adlı bir değişkene ata
12. Bir dairenin yarıçapı 30 metredir.
    1. Bu dairenin alanını hesaplayıp _daire_alani_ adlı bir değişkene ata
    2. Bu dairenin çevresini hesaplayıp _daire_cevresi_ adlı bir değişkene ata
    3. Kullanıcıdan bir yarıçap değeri al ve bu yarıçaplı dairenin alanını hesapla
1. Kullanıcıdan ad, soyad, ülke ve yaş değerlerini almak için built-in input fonksiyonlarını kullan ve değerleri ilgili değişkenlere ata
1. Python shell ya da python dosyanda help('keywords') komutunu çalıştırarak Python'daki rezerve edilmiş kelimeleri kontrol et

🎉 TEBRİKLER ! 🎉

[<< 1. Gün](../readme.md) | [3. Gün >>](../03_Day_Operators/03_operators.md)
