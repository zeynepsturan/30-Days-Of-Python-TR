<div align="center">
  <h1> 30 Günde Python: 17. Gün - Exception Handling (İstisna Yönetimi) </h1>
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

[<< 16. Gün](../16_Day_Python_date_time/16_python_datetime.md) | [18. Gün >>](../18_Day_Regular_expressions/18_regular_expressions.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 Day 17](#-day-17)
  - [Exception Handling (İstisna Yönetimi)](#exception-handling)
  - [Python'da Argümanları Packing ve Unpacking Etme](#packing-and-unpacking-arguments-in-python)
    - [Unpacking](#unpacking)
      - [Listleri Unpacking Etme](#unpacking-lists)
      - [Dictionaryleri Unpacking Etme](#unpacking-dictionaries)
    - [Packing](#packing)
    - [Listleri Packing Etme](#packing-lists)
      - [Dictionaryleri Packing Etme](#packing-dictionaries)
  - [Python'da Spreading](#spreading-in-python)
  - [Enumerate](#enumerate)
  - [Zip](#zip)
  - [Alıştırmalar: 17. Gün](#exercises-day-17)

# 📘 17. Gün

## Exception Handling (İstisna Yönetimi)

Python, hataları "zarif" bir şekilde ele almak için _try_ ve _except_ yapısını kullanır. Hatalardan "zarif" bir şekilde çıkış yapmak (veya hataları "zarifçe" yönetmek), basit bir programlama yaklaşımıdır — program ciddi bir hata durumu tespit eder ve kontrollü bir şekilde "zarifçe" sonlanır. Çoğu zaman program, bu çıkış sırasında terminale veya log dosyasına açıklayıcı bir hata mesajı yazar; bu da uygulamamızı daha sağlam hale getirir. Bir istisnanın nedeni çoğunlukla programın kendisi dışındadır. İstisna örnekleri arasında hatalı giriş, yanlış dosya adı, dosyanın bulunamaması veya arızalı bir giriş/çıkış cihazı sayılabilir. Hataları zarif bir şekilde yönetmek, uygulamalarımızın çökmesini önler.

Önceki bölümde farklı Python hata türlerini ele aldık. Eğer programımızda _try_ ve _except_ yapısını kullanırsak, bu bloklarda hata oluşsa bile program hata vermez.

![Try and Except](../images/try_except.png)

```py
try:
    işler yolunda giderse bu blok çalışır
except:
    bir şeyler yanlış olursa bu blok çalışır
```

**Örnek:**

```py
try:
    print(10 + '5')
except:
    print('Something went wrong')
```

Yukarıdaki örnekte, ikinci argüman bir string. Bunu sayıyla toplamak için float veya int’e çevirebilirdik ve işlem çalışırdı. Ama herhangi bir değişiklik yapmazsak, ikinci blok olan except çalıştırılacak.

**Örnek:**

```py
try:
    name = input('Enter your name:')
    year_born = input('Year you were born:')
    age = 2019 - year_born
    print(f'You are {name}. And your age is {age}.')
except:
    print('Something went wrong')
```

```sh
Something went wrong
```

Yukarıdaki örnekte, exception bloğu çalışacak fakat sorunun ne olduğunu tam olarak bilmiyoruz. Problemi analiz etmek için, farklı hata türlerini _except_ ile kullanabiliriz.

Aşağıdaki örnekte, hata bulunacak ve ayrıca hangi tür hatanın oluştuğunu bize bildirecek.

```py
try:
    name = input('Enter your name:')
    year_born = input('Year you were born:')
    age = 2019 - year_born
    print(f'You are {name}. And your age is {age}.')
except TypeError:
    print('Type error occured')
except ValueError:
    print('Value error occured')
except ZeroDivisionError:
    print('zero division error occured')
```

```sh
Enter your name:Asabeneh
Year you born:1920
Type error occured
```

Yukarıdaki kodda çıktı TypeError olacak.
Şimdi, ek bir blok ekleyelim:

```py
try:
    name = input('Enter your name:')
    year_born = input('Year you born:')
    age = 2019 - int(year_born)
    print(f'You are {name}. And your age is {age}.')
except TypeError:
    print('Type error occur')
except ValueError:
    print('Value error occur')
except ZeroDivisionError:
    print('zero division error occur')
else:
    print('I usually run with the try block')
finally:
    print('I alway run.')
```

```sh
Enter your name:Asabeneh
Year you born:1920
You are Asabeneh. And your age is 99.
I usually run with the try block
I alway run.
```

Yukarıdaki kod şu şekilde kısaltılabilir:

```py
try:
    name = input('Enter your name:')
    year_born = input('Year you born:')
    age = 2019 - int(year_born)
    print(f'You are {name}. And your age is {age}.')
except Exception as e:
    print(e)

```

## Python'da Argümanları Packing ve Unpacking Etme

İki operatör kullanıyoruz:

- tuple için \* 
- dictionary için \*\*

Aşağıdaki örneği inceleyelim. Fonksiyon sadece argüman alıyor ama elimizde bir list var. Listi açabiliriz (unpack) ve argümana dönüştürebiliriz.

### Unpacking

#### Listleri Unpacking Etme

```py
def sum_of_five_nums(a, b, c, d, e):
    return a + b + c + d + e

lst = [1, 2, 3, 4, 5]
print(sum_of_five_nums(lst)) # TypeError: sum_of_five_nums() missing 4 required positional arguments: 'b', 'c', 'd', and 'e'
```

Bu kodu çalıştırdığımızda bir hata verir, çünkü bu fonksiyon argüman olarak sayı alıyor (list değil). Listeyi unpack edip argümanları öyle verelim.

```py
def sum_of_five_nums(a, b, c, d, e):
    return a + b + c + d + e

lst = [1, 2, 3, 4, 5]
print(sum_of_five_nums(*lst))  # 15
```

Başlangıç ve bitiş bekleyen _range_ built-in fonksiyonunda unpacking yöntemini kullanabiliriz.

```py
numbers = range(2, 7)  # normal call with separate arguments
print(list(numbers)) # [2, 3, 4, 5, 6]
args = [2, 7]
numbers = range(*args)  # call with arguments unpacked from a list
print(numbers)      # [2, 3, 4, 5,6]

```

Bir list veya tuple şu şekilde unpack edilebilir:

```py
countries = ['Finland', 'Sweden', 'Norway', 'Denmark', 'Iceland']
fin, sw, nor, *rest = countries
print(fin, sw, nor, rest)   # Finland Sweden Norway ['Denmark', 'Iceland']
numbers = [1, 2, 3, 4, 5, 6, 7]
one, *middle, last = numbers
print(one, middle, last)      #  1 [2, 3, 4, 5, 6] 7
```

#### Dictionaryleri Unpacking Etme

```py
def unpacking_person_info(name, country, city, age):
    return f'{name} lives in {country}, {city}. He is {age} year old.'
dct = {'name':'Asabeneh', 'country':'Finland', 'city':'Helsinki', 'age':250}
print(unpacking_person_info(**dct)) # Asabeneh lives in Finland, Helsinki. He is 250 years old.
```

### Packing

Bazen bir Python fonksiyonuna kaç tane argüman geçileceğini önceden bilemeyiz. Fonksiyonumuzun sınırsız veya rastgele sayıda argümanı alabilmesini sağlamak için packing yöntemini kullanabiliriz.

### Listleri Packing Etme

```py
def sum_all(*args):
    s = 0
    for i in args:
        s += i
    return s
print(sum_all(1, 2, 3))             # 6
print(sum_all(1, 2, 3, 4, 5, 6, 7)) # 28
```

#### Dictionaryleri Packing Etme

```py
def packing_person_info(**kwargs):
    # check the type of kwargs and it is a dict type
    # print(type(kwargs))
    # Printing dictionary items
    for key in kwargs:
        print(f"{key} = {kwargs[key]}")
    return kwargs

print(packing_person_info(name="Asabeneh",
      country="Finland", city="Helsinki", age=250))
```

```sh
name = Asabeneh
country = Finland
city = Helsinki
age = 250
{'name': 'Asabeneh', 'country': 'Finland', 'city': 'Helsinki', 'age': 250}
```

## Python'da Spreading 

JavaScript'te olduğu gibi, Python'da da spread (yayma) işlemi mümkündür. Aşağıdaki örnekte bunu inceleyelim:

```py
lst_one = [1, 2, 3]
lst_two = [4, 5, 6, 7]
lst = [0, *lst_one, *lst_two]
print(lst)          # [0, 1, 2, 3, 4, 5, 6, 7]
country_lst_one = ['Finland', 'Sweden', 'Norway']
country_lst_two = ['Denmark', 'Iceland']
nordic_countries = [*country_lst_one, *country_lst_two]
print(nordic_countries)  # ['Finland', 'Sweden', 'Norway', 'Denmark', 'Iceland']
```

## Enumerate

Eğer bir listin indeksleriyle ilgileniyorsak, listteki her itemin indeksini almak için _enumerate_ built-in fonksiyonunu kullanırız.

```py
for index, item in enumerate([20, 30, 40]):
    print(index, item)
```

```py
for index, i in enumerate(countries):
    print('hi')
    if i == 'Finland':
        print('The country {i} has been found at index {index}')
```

```sh
The country Finland has been found at index 1.
```

## Zip

Bazen döngü sırasında listeleri birleştirmek isteyebiliriz. Aşağıdaki örneğe bakalım:

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'lime']                    
vegetables = ['Tomato', 'Potato', 'Cabbage','Onion', 'Carrot']
fruits_and_veges = []
for f, v in zip(fruits, vegetables):
    fruits_and_veges.append({'fruit':f, 'veg':v})

print(fruits_and_veges)
```

```sh
[{'fruit': 'banana', 'veg': 'Tomato'}, {'fruit': 'orange', 'veg': 'Potato'}, {'fruit': 'mango', 'veg': 'Cabbage'}, {'fruit': 'lemon', 'veg': 'Onion'}, {'fruit': 'lime', 'veg': 'Carrot'}]
```

🌕 Kararlısın. 17. günün challenge’larını tamamladın ve mükemmellik yolunda 17 adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## Alıştırmalar: 17. Gün

1. names = ['Finland', 'Sweden', 'Norway','Denmark','Iceland', 'Estonia','Russia']. Ülkeleri unpack et ve ilk 5 ülkeyi nordic_countries listinde, Estonia'yı es, Russia'yı ru değişkenlerinde tut.

🎉 TEBRİKLER ! 🎉

[<< 16. Gün](../16_Day_Python_date_time/16_python_datetime.md) | [18. Gün >>](../18_Day_Regular_expressions/18_regular_expressions.md)
