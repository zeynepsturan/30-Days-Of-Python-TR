<div align="center">
  <h1> 30 Günde Python: 13. Gün - List Oluşturma Kısayolu</h1>
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

[<< 12. Gün](../12_Day_Modules/12_modules.md) | [14. Gün>>](../14_Day_Higher_order_functions/14_higher_order_functions.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 13. Gün](#-day-13)
  - [List Oluşturma Kısayolu](#list-comprehension)
  - [Lambda Fonksiyonu](#lambda-function)
    - [Lambda Fonksiyonu Oluşturma](#creating-a-lambda-function)
    - [Fonksiyon İçinde Lambda Fonksiyonu](#lambda-function-inside-another-function)
  - [💻 Alıştırmalar: 13. Gün](#-exercises-day-13)

# 📘 13. Gün

## List Oluşturma Kısayolu

Python’da list comprehension, bir diziden (sequence) liste oluşturmanın kısa ve öz bir yoludur. Yeni bir liste oluşturmanın kısa yoludur ve bir listeyi _for_ döngüsüyle işlemekten genellikle çok daha hızlıdır.

```py
# sözdizimi
[i for i in iterable if expression]
```

**Örnek:1**

Örneğin, bir string’i karakterlerden oluşan bir liste çevirmek istiyorsanız birkaç yöntem kullanabilirsiniz. İşte bazı örnekler:

```py
# Birinci yöntem
language = 'Python'
lst = list(language) # stringi liste dönüştürme
print(type(lst))     # list
print(lst)           # ['P', 'y', 't', 'h', 'o', 'n']

# İkinci yöntem: list kısayolu
lst = [i for i in language]
print(type(lst)) # list
print(lst)       # ['P', 'y', 't', 'h', 'o', 'n']

```

**Örnek:2**

Örneğin bir sayı listi oluşturmak istersen

```py
# Sayı üretme
numbers = [i for i in range(11)]  #  0 - 10 arası sayı üretme
print(numbers)                    # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# İterasyon sırasında matematiksel işlemler yapmak mümkün
squares = [i * i for i in range(11)]
print(squares)                    # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

# Tuple listi yapmak da mümkün
numbers = [(i, i * i) for i in range(11)]
print(numbers)                             # [(0, 0), (1, 1), (2, 4), (3, 9), (4, 16), (5, 25)]

```

List comprehension if koşuluyla birleştirilebilir


```py
# çift sayı üretme
even_numbers = [i for i in range(21) if i % 2 == 0]  # 0 - 21 arası
print(even_numbers)                    # [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

# tek sayı üretme
odd_numbers = [i for i in range(21) if i % 2 != 0]  # 0 - 21 arası
print(odd_numbers)                      # [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]

# Sayıları filtreleme: aşağıdaki listten pozitif çift sayıları filtreleyelim
numbers = [-8, -7, -3, -1, 0, 1, 3, 4, 5, 7, 6, 8, 10]
positive_even_numbers = [i for i in numbers if i % 2 == 0 and i > 0]
print(positive_even_numbers)                    # [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

# 3 boyutlu arrayi flatten yapma
list_of_lists = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flattened_list = [ number for row in list_of_lists for number in row]
print(flattened_list)    # [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

## Lambda Fonksiyonu

Lambda fonksiyonu, isimsiz (anonymous) küçük bir fonksiyondur. Herhangi sayıda argüman alabilir, fakat yalnızca bir ifade (expression) içerebilir. Lambda fonksiyonu, JavaScript’teki anonim fonksiyonlara benzer. Başka bir fonksiyon içinde isimsiz bir fonksiyon yazmak istediğimizde kullanılır.

### Lambda Fonksiyonu Oluşturma

Bir lambda fonksiyonu oluşturmak için _lambda_ anahtar kelimesini kullanırız, ardından parametre(ler) gelir ve sonra bir ifade (expression) gelir. Aşağıda sözdizimi ve örnek gösterilmiştir. Lambda fonksiyonları return kullanmaz, fakat ifade otomatik olarak döndürülür (explicit olarak).

```py
# sözdizimi
x = lambda param1, param2, param3: param1 + param2 + param2
print(x(arg1, arg2, arg3))
```

**Örnek:**

```py
# Named function
def add_two_nums(a, b):
    return a + b

print(add_two_nums(2, 3))     # 5
# yukarıdaki fonksiyonu lambda fonksiyona çevirelim
add_two_nums = lambda a, b: a + b
print(add_two_nums(2,3))    # 5

# Self invoking lambda function
(lambda a, b: a + b)(2,3) # 5 - Sonucu konsolda görebilmek için bunu print() içine sarmamız gerekiyor.

square = lambda x : x ** 2
print(square(3))    # 9
cube = lambda x : x ** 3
print(cube(3))    # 27

# Multiple variables
multiple_variable = lambda a, b, c: a ** 2 - 3 * b + 4 * c
print(multiple_variable(5, 5, 3)) # 22
```

### Fonksiyon İçinde Lambda Fonksiyonu

lambda fonksiyonunu başka bir fonksiyon içinde kullanma:

```py
def power(x):
    return lambda n : x ** n

cube = power(2)(3)   # power fonksiyonu artık çalıştırılmak için 2 argümana ihtiyaç duyuyor ve bu argümanlar ayrı ayrı parantezler içinde verilmeli.
print(cube)          # 8
two_power_of_five = power(2)(5) 
print(two_power_of_five)  # 32
```

🌕 Devam et, enerjini kaybetme. Başarı sadece birkaç adım ötede! 13. günün challenge’larını tamamladın ve mükemmellik yolunda 13 adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 13. Gün

1. List comprehension kullanarak sadece negatif ve sıfır değerleri filtrele.
   ```py
   numbers = [-4, -3, -2, -1, 0, 2, 4, 6]
   ```
2. Aşağıdaki list içinde listleri tek boyutlu bir liste dönüştür (flatten):

   ```py
   list_of_lists =[[[1, 2, 3]], [[4, 5, 6]], [[7, 8, 9]]]

   output
   [1, 2, 3, 4, 5, 6, 7, 8, 9]
   ```

3. List comprehension kullanarak aşağıdaki tuple listesini oluştur:
   ```py
   [(0, 1, 0, 0, 0, 0, 0),
   (1, 1, 1, 1, 1, 1, 1),
   (2, 1, 2, 4, 8, 16, 32),
   (3, 1, 3, 9, 27, 81, 243),
   (4, 1, 4, 16, 64, 256, 1024),
   (5, 1, 5, 25, 125, 625, 3125),
   (6, 1, 6, 36, 216, 1296, 7776),
   (7, 1, 7, 49, 343, 2401, 16807),
   (8, 1, 8, 64, 512, 4096, 32768),
   (9, 1, 9, 81, 729, 6561, 59049),
   (10, 1, 10, 100, 1000, 10000, 100000)]
   ```
4. Aşağıdaki listi yeni bir tek boyutlu liste dönüştür (flatten):
   ```py
   countries = [[('Finland', 'Helsinki')], [('Sweden', 'Stockholm')], [('Norway', 'Oslo')]]
   çıktı:
   [['FINLAND','FIN', 'HELSINKI'], ['SWEDEN', 'SWE', 'STOCKHOLM'], ['NORWAY', 'NOR', 'OSLO']]
   ```
5. Aşağıdaki listi dictionarylerden oluşan bir liste çevir:
   ```py
   countries = [[('Finland', 'Helsinki')], [('Sweden', 'Stockholm')], [('Norway', 'Oslo')]]
   çıktı:
   [{'country': 'FINLAND', 'city': 'HELSINKI'},
   {'country': 'SWEDEN', 'city': 'STOCKHOLM'},
   {'country': 'NORWAY', 'city': 'OSLO'}]
   ```
6. Aşağıdaki listi, birleştirilmiş stringlerden oluşan bir liste çevirin:
   ```py
   names = [[('Asabeneh', 'Yetayeh')], [('David', 'Smith')], [('Donald', 'Trump')], [('Bill', 'Gates')]]
   çıktı:
   ['Asabeneh Yetaeyeh', 'David Smith', 'Donald Trump', 'Bill Gates']
   ```
7. Doğrusal fonksiyonların eğimini y eksenini kestiği noktayı bulan bir lambda fonksiyonu yaz

🎉 TEBRİKLER ! 🎉

[<< 12. Gün](../12_Day_Modules/12_modules.md) | [14. Gün>>](../14_Day_Higher_order_functions/14_higher_order_functions.md)
