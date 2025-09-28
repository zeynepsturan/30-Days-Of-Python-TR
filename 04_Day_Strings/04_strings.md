<div align="center">
  <h1> 30 Günde Python: 4. Gün - Stringler</h1>
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

[<< 3. Gün](../03_Day_Operators/03_operators.md) | [5. Gün >>](../05_Day_Lists/05_lists.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [4. Gün](#day-4)
  - [Stringler](#strings)
    - [String Oluşturmak](#creating-a-string)
    - [Stringleri Birleştirme (Concatenation)](#string-concatenation)
    - [Stringlerde Kaçış Dizileri](#escape-sequences-in-strings)
    - [String Formatlama](#string-formatting)
      - [Eski Yöntemle String Formatlama (% Operatörü)](#old-style-string-formatting--operator)
      - [Yeni Yöntemle String Formatlama (str.format)](#new-style-string-formatting-strformat)
      - [Stringe Değer Yerleştirme / f-Stringler (Python 3.6+)](#string-interpolation--f-strings-python-36)
    - [Karakter Dizileri Olarak Python Stringleri](#python-strings-as-sequences-of-characters)
      - [Unpacking Characters](#unpacking-characters)
      - [Stringdeki Karakterlere Indeksle Erişmek](#accessing-characters-in-strings-by-index)
      - [Python Stringlerini Bölme (Slicing)](#slicing-python-strings)
      - [Bir String'i Tersine Çevirme](#reversing-a-string)
      - [Stringi Bölerken Karakterleri Atlama](#skipping-characters-while-slicing)
    - [String Metodları](#string-methods)
  - [💻 Alıştırmalar - 4. Gün](#-exercises---day-4)

# 4. Gün

## Stringler

Metinler string veri tipidir. Metin olarak yazılmış her şey stringdir. Tek, çift veya üçlü tırnak içinde yazılmış her veri stringdir. String verileri işlemek için farklı metodlar ve built-in fonksiyonlar vardır. Bir stringin uzunluğunu elde etmek için len() metodu kullanılır.

### String Oluşturmak

```py
letter = 'P'                # Stringler tek bir karakter veya uzun metinler olabilir
print(letter)               # P
print(len(letter))          # 1
greeting = 'Hello, World!'  # Stringler tek veya çift tırnakla oluşturulabilir. "Hello, World!"
print(greeting)             # Hello, World!
print(len(greeting))        # 13
sentence = "I hope you are enjoying 30 days of Python Challenge"
print(sentence)
```

Çok satırlı stringler üçlü tek tırnak (''') veya üçlü çift tırnak (""") kullanarak oluşturulur. Aşağıdaki örneğe bakalım

```py
multiline_string = '''I am a teacher and enjoy teaching.
I didn't find anything as rewarding as empowering people.
That is why I created 30 days of python.'''
print(multiline_string)

# Aynısını oluşturmanın farklı bir yolu
multiline_string = """I am a teacher and enjoy teaching.
I didn't find anything as rewarding as empowering people.
That is why I created 30 days of python."""
print(multiline_string)
```

### Stringleri Birleştirme (Concatenation)

Stringleri birbirine bağlayabiliriz. Stringleri birleştirmeye veya bağlamaya concatenation denir. Aşağıdaki örnekteki gibi:

```py
first_name = 'Asabeneh'
last_name = 'Yetayeh'
space = ' '
full_name = first_name  +  space + last_name
print(full_name) # Asabeneh Yetayeh
# Stringin uzunluğunu len() built-in fonksiyonuyla bulma
print(len(first_name))  # 8
print(len(last_name))   # 7
print(len(first_name) > len(last_name)) # True
print(len(full_name)) # 16
```

### Stringlerde Kaçış Dizileri

Python ve diğer programlama dillerinde \ ve sonrasında gelen bir karakter kaçış dizisidir. Let us see the most common escape characters:

- \n: yeni satır
- \t: Tab means(8 spaces)
- \\\\: Back slash
- \\': Tek tırnak (')
- \\": Çift tırnak (")

Şimdi bu kaçış dizilerini örnekleriyle görelim:

```py
print('Umarım herkes Python Challenge'dan keyif alıyordur.\nAre you ?') # yeni satır
print('Günler\tKonular\tExercises') # tab boşluğu yani 4 boşluk ekleme 
print('1. Gün\t5\t5')
print('2. Gün\t6\t20')
print('3. Gün\t5\t23')
print('4. Gün\t1\t35')
print('This is a backslash  symbol (\\)') # ters çizgi yazabilmek için
print('In every programming language it starts with \"Hello, World!\"') # tek tırnakların içine çift tırnak yazabilmek için
# çıktı
Umarım herkes Python Challenge'dan keyif alıyordur.
Are you ?
Günler	Konular	Exercises
1. Gün	5	    5
2. Gün	6	    20
3. Gün	5	    23
4. Gün	1	    35
This is a backslash  symbol (\)
In every programming language it starts with "Hello, World!"
```

### String Formatlama

#### Eski Yöntemle String Formatlama (% Operatörü)

Python’da stringleri biçimlendirmenin birçok yolu vardır. Bu bölümde bazı yöntemleri ele alacağız. % operatörü, tuple (sabit boyutlu list) içinde yer alan değişkenleri, bir format string ile birlikte biçimlendirmek için kullanılır. Format string, normal metin ile birlikte “argüman belirleyicileri” (argument specifiers) içerir. Bu özel semboller şunlardır: %s, %d, %f, %. <small>basamak sayısı></small>f

- %s - String
- %d - Integers
- %f - Floating point numbers
- "%.<small>basamak sayısı</small>f" - belirli bir ondalık basamak sayısıyla floating point numbers

```py
# Sadece string
ad = 'Asabeneh'
soyad = 'Yetayeh'
dil = 'Python'
formated_string = 'I am %s %s. I teach %s' %(first_name, last_name, language)
print(formated_string)

# Stringler ve sayılar
radius = 10
pi = 3.14
area = pi * radius ** 2
formated_string = 'The area of circle with a radius %d is %.2f.' %(radius, area) # virgülden sonra 2 basamak

python_libraries = ['Django', 'Flask', 'NumPy', 'Matplotlib','Pandas']
formated_string = 'The following are python libraries:%s' % (python_libraries)
print(formated_string) # "The following are python libraries:['Django', 'Flask', 'NumPy', 'Matplotlib','Pandas']"
```

#### Yeni Yöntemle String Formatlama (str.format)

Bu yöntem Python version 3'te tanıtıldı.

```py

ad = 'Asabeneh'
soyad = 'Yetayeh'
dil = 'Python'
formated_string = 'I am {} {}. I teach {}'.format(first_name, last_name, language)
print(formated_string)
a = 4
b = 3

print('{} + {} = {}'.format(a, b, a + b))
print('{} - {} = {}'.format(a, b, a - b))
print('{} * {} = {}'.format(a, b, a * b))
print('{} / {} = {:.2f}'.format(a, b, a / b)) # virgülden sonra iki basamak sınırlandırır
print('{} % {} = {}'.format(a, b, a % b))
print('{} // {} = {}'.format(a, b, a // b))
print('{} ** {} = {}'.format(a, b, a ** b))

# çıktı
4 + 3 = 7
4 - 3 = 1
4 * 3 = 12
4 / 3 = 1.33
4 % 3 = 1
4 // 3 = 1
4 ** 3 = 64

# Stringler ve sayılar
yaricap = 10
pi = 3.14
alan = pi * yaricap ** 2
formated_string = 'The area of a circle with a radius {} is {:.2f}.'.format(radius, area) # virgülden sonra 2 basamak
print(formated_string)

```

#### Stringe Değer Yerleştirme/ f-Stringler (Python 3.6+)

Bir diğer yeni string biçimlendirme yöntemi string interpolasyonu (f-string)’tir. F-string’ler f harfi ile başlar ve verileri ilgili konumlarına yerleştirebiliriz.

```py
a = 4
b = 3
print(f'{a} + {b} = {a +b}')
print(f'{a} - {b} = {a - b}')
print(f'{a} * {b} = {a * b}')
print(f'{a} / {b} = {a / b:.2f}')
print(f'{a} % {b} = {a % b}')
print(f'{a} // {b} = {a // b}')
print(f'{a} ** {b} = {a ** b}')
```

### Karakter Dizileri Olarak Python Stringleri

Python string’leri, karakter dizileri (sequences of characters) şeklindedir ve temel erişim yöntemlerini, diğer Python sıralı nesne dizileri (listler ve tuplelar) ile aynıdır. String’lerden tek bir karakteri (veya herhangi bir dizideki bireysel öğeyi) çıkarmanın en basit yolu, bunları **ilgili değişkenlere açmak (unpack)**tır.

#### Unpacking Characters

```
language = 'Python'
a,b,c,d,e,f = language # karakter dizisini değişkenlere unpacking etme
print(a) # P
print(b) # y
print(c) # t
print(d) # h
print(e) # o
print(f) # n
```

#### Stringdeki Karakterlere Indeksle Erişmek

Programlamada saymaya sıfırdan başlanır. Bu yüzden stringin ilk harfi 0. indekstedir ve son harfi string uzunluğunun 1 eksiği indekstedir.

![String index](../images/string_index.png)

```py
language = 'Python'
first_letter = language[0]
print(first_letter) # P
second_letter = language[1]
print(second_letter) # y
last_index = len(language) - 1
last_letter = language[last_index]
print(last_letter) # n
```

Sağdan başlamak istersek negatif indeksleme kullanabiliriz. -1 son indeksi temsil eder.

```py
dil = 'Python'
last_letter = language[-1]
print(last_letter) # n
second_last = language[-2]
print(second_last) # o
```

#### Python Stringlerini Bölme (Slicing)

Python'da stringleri alt stringlere (substring) bölebiliriz.

```py
dil = 'Python'
first_three = language[0:3] # 0. indeksten başlayıp 3. indekse kadar devam eder ama 3.yü dahil etmez
print(first_three) #Pyt
last_three = language[3:6]
print(last_three) # hon
# Diğer bir yöntem
last_three = language[-3:]
print(last_three)   # hon
last_three = language[3:]
print(last_three)   # hon
```

#### Bir String'i Tersine Çevirme

Python'da bir stringi kolayca tersine çevirebiliriz.

```py
greeting = 'Hello, World!'
print(greeting[::-1]) # !dlroW ,olleH
```

#### Stringi Bölerken Karakterleri Atlama

Slice yöntemine adım (step) argümanı vererek karakterleri atlayarak seçmek mümkündür.

```py
dil = 'Python'
pto = language[0:6:2] #
print(pto) # Pto
```

### String Metodları

Stringleri biçimlendirmemize olanak tanıyan birçok string yöntemi vardır. Aşağıdaki örnekte bazı string yöntemlerini görebilirsiniz:

- capitalize(): Stringin ilk karakterini büyük harfe dönüştürür.

```py
challenge = 'thirty days of python'
print(challenge.capitalize()) # 'Thirty days of python'
```

- count(): Bir string içinde bir alt string’in (substring) kaç kez geçtiğini döner: count(substring, start=.., end=..): start saymaya başlanan indeks, end saymanın bittiği son indekstir.

```py
challenge = 'thirty days of python'
print(challenge.count('y')) # 3
print(challenge.count('y', 7, 14)) # 1, 
print(challenge.count('th')) # 2`
```

- endswith(): Stringin belli bir şekilde bitip bitmediğini kontrol eder

```py
challenge = 'thirty days of python'
print(challenge.endswith('on'))   # True
print(challenge.endswith('tion')) # False
```

- expandtabs(): Tab karakterini boşluk ile değiştirir. Varsayılan tab boyutu 8'dir. Argüman olarak tab boyutu alır.

```py
challenge = 'thirty\tdays\tof\tpython'
print(challenge.expandtabs())   # 'thirty  days    of      python'
print(challenge.expandtabs(10)) # 'thirty    days      of        python'
```

- find(): Bir alt stringin (substring) ilk geçtiği indeks’i döner, bulunmuyorsa -1 döner.

```py
challenge = 'thirty days of python'
print(challenge.find('y'))  # 5
print(challenge.find('th')) # 0
```

- rfind(): Bir alt stringin (substring) son geçtiği indeks’i döner, bulunmuyorsa -1 döner.

```py
challenge = 'thirty days of python'
print(challenge.rfind('y'))  # 16
print(challenge.rfind('th')) # 17
```

- format(): Stringi daha düzgün bir çıktıya formatlar. String biçimlendirme hakkında daha fazla bilgi için şuraya bakın:[bağlantı (https://www.programiz.com/python-programming/methods/string/format)

```py
first_name = 'Asabeneh'
last_name = 'Yetayeh'
age = 250
job = 'teacher'
country = 'Finland'
sentence = 'I am {} {}. I am a {}. I am {} years old. I live in {}.'.format(first_name, last_name, age, job, country)
print(sentence) # I am Asabeneh Yetayeh. I am 250 years old. I am a teacher. I live in Finland.

radius = 10
pi = 3.14
area = pi * radius ** 2
result = 'The area of a circle with radius {} is {}'.format(str(radius), str(area))
print(result) # The area of a circle with radius 10 is 314
```

- index(): Bir alt stringin (substring) en düşük indeksini döner. Ek argümanlar, başlangıç ve bitiş indekslerini belirtir (varsayılan değerler: 0 ve string uzunluğu - 1). Eğer alt string bulunamazsa, ValueError hatası verir.

```py
challenge = 'thirty days of python'
sub_string = 'da'
print(challenge.index(sub_string))  # 7
print(challenge.index(sub_string, 9)) # hata
```

- rindex(): Bir alt stringin (substring) en yüksek indeksini döner., Ek argümanlar, başlangıç ve bitiş indekslerini belirtir (varsayılan değerler: 0 ve string uzunluğu - 1)

```py
challenge = 'thirty days of python'
sub_string = 'da'
print(challenge.rindex(sub_string))  # 7
print(challenge.rindex(sub_string, 9)) # hata
print(challenge.rindex('on', 8)) # 19
```

- isalnum(): Alfanumerik karakterleri kontrol eder

```py
challenge = 'ThirtyDaysPython'
print(challenge.isalnum()) # True

challenge = '30DaysPython'
print(challenge.isalnum()) # True

challenge = 'thirty days of python'
print(challenge.isalnum()) # False, boşluk bir alfanumerik karakter değildir

challenge = 'thirty days of python 2019'
print(challenge.isalnum()) # False
```

- isalpha(): Stringdeki tüm karakterlerin harf olup olmadığını kontrol eder (a-z ve A-Z)

```py
challenge = 'thirty days of python'
print(challenge.isalpha()) # False, boşluk harf değildir
challenge = 'ThirtyDaysPython'
print(challenge.isalpha()) # True
num = '123'
print(num.isalpha())      # False
```

- isdecimal(): Stringdeki tüm karakterlerin rakam olup olmadığını kontrol eder (0-9)

```py
challenge = 'thirty days of python'
print(challenge.isdecimal())  # False
challenge = '123'
print(challenge.isdecimal())  # True
challenge = '\u00B2'
print(challenge.isdigit())   # False
challenge = '12 3'
print(challenge.isdecimal())  # False, boşluk rakam değildir
```

- isdigit(): Bir stringdeki tüm karakterlerin sayı (0-9 ve bazı diğer unicode sayı karakterleri) olup olmadığını kontrol eder.

```py
challenge = 'Thirty'
print(challenge.isdigit()) # False
challenge = '30'
print(challenge.isdigit())   # True
challenge = '\u00B2'
print(challenge.isdigit())   # True
```

- isnumeric(): Bir stringdeki tüm karakterlerin sayılar veya sayı ile ilgili semboller (örneğin ½) olup olmadığını kontrol eder. isdigit() yöntemine benzer, ancak daha fazla sembolü kabul eder.

```py
num = '10'
print(num.isnumeric()) # True
num = '\u00BD' # ½
print(num.isnumeric()) # True
num = '10.5'
print(num.isnumeric()) # False
```

- isidentifier(): Geçerli bir identifier (tanımlayıcı) olup olmadığını kontrol eder – yani bir stringin geçerli bir değişken adı olup olmadığını denetler.

```py
challenge = '30DaysOfPython'
print(challenge.isidentifier()) # False, çünkü sayıyla başlıyor
challenge = 'thirty_days_of_python'
print(challenge.isidentifier()) # True
```

- islower(): Stringdeki tüm karakterlerin küçük harf olup olmadığını kontrol eder

```py
challenge = 'thirty days of python'
print(challenge.islower()) # True
challenge = 'Thirty days of python'
print(challenge.islower()) # False
```

- isupper(): Stringdeki tüm karakterlerin büyük harf olup olmadığını kontrol eder

```py
challenge = 'thirty days of python'
print(challenge.isupper()) #  False
challenge = 'THIRTY DAYS OF PYTHON'
print(challenge.isupper()) # True
```

- join(): Birleştirilmiş stringi döner

```py
web_tech = ['HTML', 'CSS', 'JavaScript', 'React']
result = ' '.join(web_tech)
print(result) # 'HTML CSS JavaScript React'
```

```py
web_tech = ['HTML', 'CSS', 'JavaScript', 'React']
result = '# '.join(web_tech)
print(result) # 'HTML# CSS# JavaScript# React'
```

- strip(): Stringin başından ve sonundan verilen tüm karakterleri kaldırır.

```py
challenge = 'thirty days of pythoonnn'
print(challenge.strip('noth')) # 'irty days of py'
```

- replace(): Bir alt stringi (substring) verilen başka bir string ile değiştirir.

```py
challenge = 'thirty days of python'
print(challenge.replace('python', 'coding')) # 'thirty days of coding'
```

- split(): Stringi, verilen string veya boşluk karakterini ayırıcı (separator) olarak kullanarak böler.

```py
challenge = 'thirty days of python'
print(challenge.split()) # ['thirty', 'days', 'of', 'python']
challenge = 'thirty, days, of, python'
print(challenge.split(', ')) # ['thirty', 'days', 'of', 'python']
```

- title(): Stringi her kelimenin baş harfini büyük harf yaparak döner

```py
challenge = 'thirty days of python'
print(challenge.title()) # Thirty Days Of Python
```

- swapcase(): Tüm büyük harfleri küçük harfe, tüm küçük harfleri büyük harfe dönüştürür.

```py
challenge = 'thirty days of python'
print(challenge.swapcase())   # THIRTY DAYS OF PYTHON
challenge = 'Thirty Days Of Python'
print(challenge.swapcase())  # tHIRTY dAYS oF pYTHON
```

- startswith(): String’in belirtilen string ile başlayıp başlamadığını kontrol eder.

```py
challenge = 'thirty days of python'
print(challenge.startswith('thirty')) # True

challenge = '30 days of python'
print(challenge.startswith('thirty')) # False
```

🌕 Olağanüstü birisin ve dikkate değer bir potansiyele sahipsin. 4. günün challenge’larını tamamladın ve mükemmellik yolunda dört adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar - 4. Gün

1. 'Thirty', 'Days', 'Of', 'Python' stringlerini birleştirerek tek bir string oluştur: 'Thirty Days Of Python'
2. 'Coding', 'For', 'All' stringlerini birleştirerek tek bir string oluştur: 'Coding For All'
3. company adında bir değişken tanımlayın ve başlangıç değeri olarak "Coding For All" ata
4. company değişkenini _print()_ ile yazdır
5. company stringinin uzunluğunu _len()_ yöntemi ile bul ve _print()_ ile yazdır
6. Tüm karakterleri büyük harf yapmak için _upper()_ yöntemini kullan
7. Tüm karakterleri küçük harf yapmak için _lower()_ yöntemini kullan
8. _Coding For All_ stringinin değerini capitalize(), title(), swapcase() yöntemleri ile biçimlendir
9. _Coding For All_ stringinin ilk kelimesini kesip (slice) çıkar
10. _Coding For All_ stringinde "Coding" kelimesinin olup olmadığını index, find veya diğer yöntemlerle kontrol et
11. 'Coding For All' stringindeki "Coding" kelimesini "Python" ile değiştir
12. "Python for Everyone" ifadesini "Python for All" olarak replace veya diğer yöntemlerle değiştir
13. 'Coding For All' stringini boşluk karakterini ayırıcı olarak kullanarak böl(split())
14. "Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon" stringini virgül karakterini ayırıcı olarak kullanarak böl
15. _Coding For All_ stringinde 0. indeksteki karakter nedir?
16. _Coding For All_ stringinin son indeksi nedir?
17. "Coding For All" stringinde 10. indeksteki karakter nedir?
18. 'Python For Everyone' ifadesi için bir kısaltma (abbreviation) oluştur
19. 'Coding For All' ifadesi için bir kısaltma (abbreviation) oluştur
20. "Coding For All" stringinde C harfinin ilk geçtiği pozisyonu bulmak için index yöntemini kullan
21. "Coding For All" stringinde F harfinin ilk geçtiği pozisyonu bulmak için index yöntemini kullan
22. "Coding For All People" stringinde l harfinin son geçtiği pozisyonu bulmak için rfind yöntemini kullan
23. 'You cannot end a sentence with because because because is a conjunction' cümlesinde 'because' kelimesinin ilk geçtiği pozisyonu bulmak için index veya find yöntemini kullan
24. 'You cannot end a sentence with because because because is a conjunction' cümlesinde 'because' kelimesinin son geçtiği pozisyonu bulmak için rindex yöntemini kullan
25. 'You cannot end a sentence with because because because is a conjunction' cümlesinden 'because because because' ifadesini kesip (slice) çıkar
26. 'You cannot end a sentence with because because because is a conjunction' cümlesinde 'because' kelimesinin ilk geçtiği pozisyonu bul
27. 'Coding For All' stringi Coding substringi ile başlıyor mu?
28. 'Coding For All' stringi coding substringi ile bitiyor mu?
29. '&nbsp;&nbsp; Coding For All &nbsp;&nbsp;&nbsp; &nbsp;' &nbsp; stringinin başındaki ve sonundaki boşlukları (trailing spaces) kaldırın.
30. Aşağıdaki değişkenlerden hangisi isidentifier() yöntemi kullanıldığında True döner?
    - 30DaysOfPython
    - thirty_days_of_python
31. Bu liste Python kütüphanelerinin isimlerini içeriyor: ['Django', 'Flask', 'Bottle', 'Pyramid', 'Falcon']. Listeyi boşluk ve hash (#) ile birleştir (join).
32. Aşağıdaki cümleleri yeni satır kaçış karakteri kullanarak ayır
    ```py
    I am enjoying this challenge.
    I just wonder what is next.
    ```
33. Aşağıdaki satırları yazmak için tab kaçış karakteri kullan
    ```py
    Name      Age     Country   City
    Asabeneh  250     Finland   Helsinki
    ```
34. Aşağıdakileri string biçimlendirme (string formatting) yöntemi kullanarak görüntüle

```sh
radius = 10
area = 3.14 * radius ** 2
The area of a circle with radius 10 is 314 meters square.
```

35. String formatlama metodlarını kullanarak aşağıdakileri yap:

```sh
8 + 6 = 14
8 - 6 = 2
8 * 6 = 48
8 / 6 = 1.33
8 % 6 = 2
8 // 6 = 1
8 ** 6 = 262144
```

🎉 TEBRİKLER ! 🎉

[<< 3. Gün](../03_Day_Operators/03_operators.md) | [5. Gün >>](../05_Day_Lists/05_lists.md)


