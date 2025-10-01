<div align="center">
  <h1> 30 Günde Python: 11. Gün - Fonksiyonlar</h1>
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

[<< 10. Gün](../10_Day_Loops/10_loops.md) | [12. Gün >>](../12_Day_Modules/12_modules.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 11. Gün](#-day-11)
  - [Fonksiyonlar](#functions)
    - [Bir Fonksiyon Bildirmek](#defining-a-function)
    - [Fonksiyonu Bildirmek ve Çağırmak](#declaring-and-calling-a-function)
    - [Parametresiz Fonksiyonlar](#function-without-parameters)
    - [Değer Dönen Fonksiyonlar - Kısım 1](#function-returning-a-value---part-1)
    - [Parametreli Fonksiyonlar](#function-with-parameters)
    - [Key ve Value ile Argüman Vermek](#passing-arguments-with-key-and-value)
    - [Değer Dönen Fonksiyonlar - Kısım 2](#function-returning-a-value---part-2)
    - [Varsayılan Parametreli Fonksiyon](#function-with-default-parameters)
    - [Belirsiz Sayıda Argümanlar](#arbitrary-number-of-arguments)
    - [Fonksiyonlarda Varsayılan ve Belirsiz Sayıda Argümanlar](#default-and-arbitrary-number-of-parameters-in-functions)
    - [Bir Fonksiyonun Parametresi Olarak Başka Bir Fonksiyon](#function-as-a-parameter-of-another-function)
  - [Değerlendirme](#testimony)
  - [💻 Alıştırmalar: 11. Gün](#-exercises-day-11)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)
    - [Alıştırmalar: 3. Seviye](#exercises-level-3)

# 📘 11. Gün

## Fonksiyonlar

Şimdiye kadar birçok built-in Python fonksiyonu gördük. Bu bölümde, özel fonksiyonlara odaklanacağız. Peki, fonksiyon nedir? Fonksiyonlar oluşturmaya başlamadan önce, bir fonksiyonun ne olduğunu ve neden ihtiyaç duyduğumuzu öğrenelim.

### Bir Fonksiyon Bildirmek

Fonksiyon, belirli bir görevi yerine getirmek için tasarlanmış, yeniden kullanılabilir bir kod veya programlama ifadeleri bloğudur. Python, bir fonksiyon tanımlamak veya bildirmek için _def_ anahtar kelimesini sağlar. Bir fonksiyon tanımlamanın sözdizimi aşağıdaki gibidir. Fonksiyon bloğundaki kod, yalnızca fonksiyon çağrıldığında veya çalıştırıldığında yürütülür.

###Fonksiyonu Bildirmek ve Çağırmak

Bir fonksiyon oluşturduğumuzda, buna fonksiyon bildirimi (declare) diyoruz. Fonksiyonu kullanmaya başladığımızda ise buna fonksiyonu çağırmak (calling) veya çalıştırmak (invoking) denir. Fonksiyon, parametreli veya parametresiz olarak bildirilebilir.

```py
# sözdizimi
# Declaring a function
def function_name():
    kod
    kod
# Calling a function
function_name()
```

### Parametresiz Fonksiyonlar

Fonksiyonlar parametresiz tanımlanabilir.

**Örnek:**

```py
def generate_full_name ():
    ad = 'Asabeneh'
    soyad = 'Yetayeh'
    bosluk = ' '
    tam_ad = first_name + space + last_name
    print(tam_ad)
generate_full_name () # calling a function

def add_two_numbers ():
    num_one = 2
    num_two = 3
    total = num_one + num_two
    print(total)
add_two_numbers()
```

### Değer Dönen Fonksiyonlar - Kısım 1

Fonksiyonlar değer döndürebilir. Eğer bir fonksiyonun return ifadesi yoksa fonksiyonun değeri None olur. Yukarıdaki fonksiyonları return kullanarak tekrar yazalım. Artık fonksiyonu çağırdığımızda fonksiyondan bir değer alır ve bunu print() ile yazdırabiliriz.

```py
def generate_full_name ():
    first_name = 'Asabeneh'
    last_name = 'Yetayeh'
    space = ' '
    full_name = first_name + space + last_name
    return full_name
print(generate_full_name())

def add_two_numbers ():
    num_one = 2
    num_two = 3
    total = num_one + num_two
    return total
print(add_two_numbers())
```

### Parametreli Fonksiyonlar

Bir fonksiyonda farklı veri tiplerini (sayı, string, boolean, liste, tuple, sözlük veya set) parametre olarak geçirebiliriz.

- Tek Parametre: Eğer fonksiyonumuz bir parametre alıyorsa onu argümanıyla birlikte çağırmalıyız:

```py
  # sözdizimi
  # Declaring a function
  def fonksiyon_adı(parameter):
    kod
    kod
  # Fonksiyonu çağırma
  print(fonksiyon_adı(argument))
```

**Örnek:**

```py
def greetings (name):
    message = name + ', welcome to Python for Everyone!'
    return message

print(greetings('Asabeneh'))

def add_ten(num):
    ten = 10
    return num + ten
print(add_ten(90))

def square_number(x):
    return x * x
print(square_number(2))

def area_of_circle (r):
    PI = 3.14
    area = PI * r ** 2
    return area
print(area_of_circle(10))

def sum_of_numbers(n):
    total = 0
    for i in range(n+1):
        total+=i
    print(total)
print(sum_of_numbers(10)) # 55
print(sum_of_numbers(100)) # 5050
```

- İki Parametre: Bir fonksiyonun hiç parametresi olmayabilir. Aynı zamanda birden fazla parametresi de olabilir. Eğer fonksiyonumuz parametre alıyorsa argümanlarıyla birlikte çağırmalıyız. İki parametreli bir fonksiyona bakalım:

```py
  # sözdizimi
  # Declaring a function
  def fonksiyon_adı(para1, para2):
    codes
    codes
  # Calling function
  print(fonksiyon_adı(arg1, arg2))
```

**Örnek:**

```py
def generate_full_name (first_name, last_name):
    bosluk = ' '
      tam_ad = first_name + space + last_name
      return tam_ad
print('Full Name: ', generate_full_name('Asabeneh','Yetayeh'))

def sum_two_numbers (num_one, num_two):
    sum = num_one + num_two
    return sum
print('Sum of two numbers: ', sum_two_numbers(1, 9))

def calculate_age (current_year, birth_year):
    yas = current_year - birth_year
    return yas;

print('Yaş: ', calculate_age(2021, 1819))

def weight_of_object (mass, gravity):
    weight = str(mass * gravity)+ ' N' # value önce stringe çevrilmeli
    return weight
print('Weight of an object in Newtons: ', weight_of_object(100, 9.81))
```

### Key ve Value ile Argüman Vermek

Eğer argümanları key ve value ile verirsek, argümanların sırası önemli değildir.

```py
# sözdizimi
# Fonksiyon bildirme
def fonksiyon_adı(para1, para2):
    kod
    kod
# Fonksiyonu çağırma
print(fonksiyon_adı(para1 = 'John', para2 = 'Doe')) # the order of arguments does not matter here
```

**Örnek:**

```py
def print_fullname(firstname, lastname):
    space = ' '
    full_name = firstname  + space + lastname
    print(full_name)
print(print_fullname(firstname = 'Asabeneh', lastname = 'Yetayeh'))

def add_two_numbers (num1, num2):
    total = num1 + num2
    print(total)
print(add_two_numbers(num2 = 3, num1 = 2)) # Order does not matter
```

### Değer Dönen Fonksiyonlar - Kısım 2

Eğer bir fonksiyon değer dönmezse, fonksiyon varsayılan olarak _None_ döner. Fonksiyondan bir değer döndürmek için _return_ anahtar kelimesi kullanılır ve ardından döndürmek istediğimiz değişken belirtilir. Fonksiyondan herhangi bir veri tipi döndürülebilir.

- String döndürme:
**Örnek:**

```py
def print_name(firstname):
    return firstname
print_name('Asabeneh') # Asabeneh

def print_full_name(firstname, lastname):
    space = ' '
    full_name = firstname  + space + lastname
    return full_name
print_full_name(firstname='Asabeneh', lastname='Yetayeh')
```

- Sayı döndürme:

**Örnek:**

```py
def add_two_numbers (num1, num2):
    total = num1 + num2
    return total
print(add_two_numbers(2, 3))

def calculate_age (current_year, birth_year):
    yas = current_year - birth_year
    return yas;
print('Yaş: ', calculate_age(2019, 1819))
```

- Boolean döndürme:
  **Örnek:**

```py
def is_even (n):
    if n % 2 == 0:
        print('çift')
        return True    # return fonksiyonun çalışmasını durdurur, break'e benzer
    return False
print(is_even(10)) # True
print(is_even(7)) # False
```

- List döndürme:
  **Örnek:**

```py
def find_even_numbers(n):
    evens = []
    for i in range(n + 1):
        if i % 2 == 0:
            evens.append(i)
    return evens
print(find_even_numbers(10))
```

### Varsayılan Parametreli Fonksiyon

Bazen fonksiyonlara varsayılan değerler veririz. Eğer fonksiyonu çağırırken argümanlarını vermezsek varsayılan argüman değerleri kullanılır.

```py
# sözdizimi
# Fonksiyon bildirme
def function_name(param = value):
    kod
    kod
# Fonksiyon çağırma
function_name()
function_name(arg)
```

**Örnek:**

```py
def greetings (name = 'Peter'):
    message = name + ', welcome to Python for Everyone!'
    return message
print(greetings())
print(greetings('Asabeneh'))

def generate_full_name (first_name = 'Asabeneh', last_name = 'Yetayeh'):
    space = ' '
    full_name = first_name + space + last_name
    return full_name

print(generate_full_name())
print(generate_full_name('David','Smith'))

def calculate_age (birth_year,current_year = 2021):
    age = current_year - birth_year
    return age;
print('Age: ', calculate_age(1821))

def weight_of_object (mass, gravity = 9.81):
    weight = str(mass * gravity)+ ' N' # value stringe çevrilmeli
    return weight
print('Weight of an object in Newtons: ', weight_of_object(100)) # 9.81 - dünya yüzeyindeki ortalama yerçekimi
print('Weight of an object in Newtons: ', weight_of_object(100, 1.62)) # ay yüzeyindeki yer çekimi
```

### Belirsiz Sayıda Argümanlar

Eğer fonksiyonumuza kaç tane argüman verileceğini bilmiyorsak, parametre adının önüne * ekleyerek istediğimiz sayıda argüman alabilen (arbitrary number of arguments) bir fonksiyon oluşturabiliriz.

```py
# sözdizimi
# Fonksiyonu bildirme
def fonksiyon_adı(*args):
    kod
    kod
# Fonksiyonu çağırma
fonksiyon_adı(param1, param2, param3,..)
```

**Örnek:**

```py
def sum_all_nums(*nums):
    total = 0
    for num in nums:
        total += num     # total = total + num 
    return total
print(sum_all_nums(2, 3, 5)) # 10
```

### Fonksiyonlarda Varsayılan ve Belirsiz Sayıda Argümanlar

```py
def generate_groups (team,*args):
    print(team)
    for i in args:
        print(i)
print(generate_groups('Team-1','Asabeneh','Brook','David','Eyob'))
```

### Bir Fonksiyonun Parametresi Olarak Başka Bir Fonksiyon

```py
#Fonksiyonları parametre olarak verebiliriz
def square_number (n):
    return n * n
def do_something(f, x):
    return f(x)
print(do_something(square_number, 3)) # 27
```

🌕 Çok şey başardın, devam et! 11. günün challenge’larını tamamladın ve mükemmellik yolunda 11 adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## Değerlendirme

Şimdi yazar ve 30DaysOfPython hakkındaki düşüncelerini ifade etme zamanı. Görüşlerini bu [link](https://testimonial-s3sw.onrender.com/) üzerinden paylaşabilirsin.

## 💻 Alıştırmalar: 11. Gün

### Alıştırmalar: 1. Seviye

1. _add_two_numbers_ adında bir fonksiyon tanımla. İki parametre alır ve toplamını döndürür.
2. Bir dairenin alanı şu şekilde hesaplanır: alan = π x r x r. _area_of_circle_ adında bir fonksiyon yaz
3. _add_all_nums_ adında bir fonksiyon yaz; rastgele sayıda argüman alır ve tüm argümanları toplar. Listenin tüm elemanlarının sayı tipi olup olmadığını kontrol et. Değilse makul bir geri bildirim ver.
4. Sıcaklık °C’den °F’ye şu formülle dönüştürülebilir: °F = (°C x 9/5) + 32. _convert_celsius_to_fahrenheit_ adında bir fonksiyon yaz.
5. _check_season_ adında bir fonksiyon yaz; bir ay parametresi alır ve mevsimi döndürür: Sonbahar, Kış, İlkbahar veya Yaz.
6. _calculate_slope_ adında bir fonksiyon yaz; bir doğrusal denklemin eğimini döndürür.
7. Bir kuadratik denklem şu şekilde hesaplanır: ax² + bx + c = 0. _solve_quadratic_eqn_ adında bir fonksiyon yaz; kuadratik denklemin çözüm kümesini hesaplar.
8. _print_list_ adında bir fonksiyon tanımla. Bir list parametresi alır ve listi her elemanını yazdırır.
9. _reverse_list_ adında bir fonksiyon tanımla. Bir array parametresi alır ve arrayi ters çevirir (döngü kullanarak).

```py
print(reverse_list([1, 2, 3, 4, 5]))
# [5, 4, 3, 2, 1]
print(reverse_list1(["A", "B", "C"]))
# ["C", "B", "A"]
```

10. _capitalize_list_items_ adında bir fonksiyon tanımla. Bir list parametresi alır ve elemanları büyük harfe çevrilmiş bir list döndürür.
11. _add_item_ adında bir fonksiyon tanımlayın. Bir list ve bir item parametresi alır. İtemi listin sonuna ekleyerek yeni listi döndürür.

```py
food_staff = ['Potato', 'Tomato', 'Mango', 'Milk']
print(add_item(food_staff, 'Meat'))     # ['Potato', 'Tomato', 'Mango', 'Milk','Meat']
numbers = [2, 3, 7, 9]
print(add_item(numbers, 5))      [2, 3, 7, 9, 5]
```

12. _remove_item_ adında bir fonksiyon tanımla. Bir list ve bir item parametresi alır. Liste içinden itemi silerek yeni listi döndürür.

```py
food_staff = ['Potato', 'Tomato', 'Mango', 'Milk']
print(remove_item(food_staff, 'Mango'))  # ['Potato', 'Tomato', 'Milk'];
numbers = [2, 3, 7, 9]
print(remove_item(numbers, 3))  # [2, 7, 9]
```

13. _sum_of_numbers_ adında bir fonksiyon tanımla. Bir sayı parametresi alır ve o sayıya kadar olan tüm sayıların toplamını döndürür.

```py
print(sum_of_numbers(5))  # 15
print(sum_of_numbers(10)) # 55
print(sum_of_numbers(100)) # 5050
```

14. _sum_of_odds_ adında bir fonksiyon tanımla. Bir sayı parametresi alır ve o sayıya kadar olan tüm tek sayıların toplamını döndürür.
15. _sum_of_even_ adında bir fonksiyon tanımla. Bir sayı parametresi alır ve o sayıya kadar olan tüm çift sayıların toplamını döndürür.

### Alıştırmalar: 2. Seviye

1. evens_and_odds adında bir fonksiyon tanımla. Bir pozitif tam sayı parametresi alır ve bu sayıdaki çift ve tek sayıların sayısını hesaplar.

```py
    print(evens_and_odds(100))
    # The number of odds are 50.
    # The number of evens are 51.
```

1. factorial adında bir fonksiyon çağır; bir tam sayı parametresi alır ve sayının faktöriyelini döndürür.
2. _is_empty_ adında bir fonksiyon çağır; bir parametre alır ve boş olup olmadığını kontrol eder.
3. Farklı fonksiyonlar yaz; bunlar listleri parametre olarak almalı ve aşağıdakileri hesaplamalı: calculate_mean (ortalama), calculate_median (medyan), calculate_mode (mod), calculate_range (aralık), calculate_variance (varyans), calculate_std (standart sapma).

### Alıştırmalar: 3. Seviye

1. Bir sayının asal olup olmadığını kontrol eden is_prime adlı bir fonksiyon yaz.
2. Listin tüm elemanlarının benzersiz olup olmadığını kontrol eden bir fonksiyon yaz.
3. Listin tüm elemanlarının aynı veri tipinde olup olmadığını kontrol eden bir fonksiyon yaz.
4. Verilen değişken isminin geçerli bir Python değişken ismi olup olmadığını kontrol eden bir fonksiyon yaz.
5. data klasörüne gidin ve countries-data.py dosyasını aç.

- Dünyadaki en çok konuşulan 10 veya 20 dili azalan sırayla döndüren most_spoken_languages adında bir fonksiyon oluştur.
- En çok nüfusa sahip 10 veya 20 ülkeyi azalan sırayla döndüren most_populated_countries adında bir fonksiyon oluştur.

🎉 TEBRİKLER ! 🎉

[<< 10. Gün](../10_Day_Loops/10_loops.md) | [12. Gün >>](../12_Day_Modules/12_modules.md)
