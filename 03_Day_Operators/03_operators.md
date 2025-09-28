<div align="center">
  <h1> 30 Günde Python: 3. Gün - Operatörler</h1>
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

[<< 2. Gün](../02_Day_Variables_builtin_functions/02_variables_builtin_functions.md) | [4. Gün >>](../04_Day_Strings/04_strings.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 3. Gün](#-day-3)
  - [Booleanlar](#boolean)
  - [Operatörler](#operators)
    - [Atama Operatörleri](#assignment-operators)
    - [Aritmetik Operatörler:](#arithmetic-operators)
    - [Karşılaştırma Operatörleri](#comparison-operators)
    - [Mantıksal Operatörler](#logical-operators)
  - [💻 Alıştırmalar - 3. Gün](#-exercises---day-3)

# 📘 3. Gün

## Booleanlar

Boolean veri tipi _True (doğru)_ veya _False (yanlış)_ değerini alır. Bu veri tiplerinin kullanımını karşılaştırma operatörlerini kullanmaya başlayınca daha iyi anlayacaksın. JavaScript'in aksine Python'da True ve False değerlerinin baş harfleri **T** ve **F** büyük harf olmak zorundadır.

**Example: Boolean Değerler**

```py
print(True)
print(False)
```

## Operatörler

Python farklı çeşitlerde operatörleri destekler. Bu bölümde bunlardan bazılarına odaklanacağız.

### Atama Operatörleri

Atama operatörleri, değişkenlere değer atamak için kullanılır. = operatörünü örnek alalım. Matematikte eşittir işareti (=), iki değerin eşit olduğunu gösterir; ancak Python’da bir değeri belirli bir değişkene atadığımızı ifade eder. Buna atama (assignment) veya değeri bir değişkene atama denir. Aşağıdaki tablo farklı python atama operatörlerini gösteriyor. Tablo, [w3school](https://www.w3schools.com/python/python_operators.asp)'dan alınmıştır.

![Assignment Operators](../images/assignment_operators.png)

### Aritmetik Operatörler:

- Toplama(+): a + b
- Çıkarma(-): a - b
- Çarpma(*): a * b
- Bölme(/): a / b
- Mod alma(%): a % b
- Tam/kalansız bölme (floor division)(//): a // b
- Üs alma(**): a ** b

![Arithmetic Operators](../images/arithmetic_operators.png)

**Örnek:Integerlar**

```py
# Python'da aritmetik operatörler
# Integerlar

print('Addition: ', 1 + 2)        # 3
print('Subtraction: ', 2 - 1)     # 1
print('Multiplication: ', 2 * 3)  # 6
print ('Division: ', 4 / 2)       # 2.0  Python'da bölme floating sayı döner
print('Division: ', 6 / 2)        # 3.0         
print('Division: ', 7 / 2)        # 3.5
print('Floor divsiion: ', 7 // 2)   # 3,  kalan olmadan tam sayı bölümü verir
print ('Floor divsiion: ',7 // 3)   # 2
print('Modulus: ', 3 % 2)         # 1, Kalanı verir
print('Exponention: ', 2 ** 3) # 9  2 * 2 * 2 demek
```

**Örnek:Floatlar**

```py
# Floating sayılar
print('Floating Point Number, PI', 3.14)
print('Floating Point Number, gravity', 9.81)
```

**Örnek:Complex(Karmaşık sayılar)**

```py
# Complex numbers
print('Complex number: ', 1 + 1j)
print('Multiplying complex numbers: ',(1 + 1j) * (1 - 1j))
```

Bir değişken tanımlayalım ve ona bir sayı (number) veri tipi atayalım. Ben tek karakterli bir değişken kullanacağım, ancak unutmayın: Bu tür değişkenler tanımlama alışkanlığı edinmeyin. Değişken adları her zaman hatırlatıcı (mnemonic) olmalıdır.

**Örnek:**

```python
# Değişkenleri tanımlama

a = 3 # a bir değişken ismi ve 3 bir integer veri tipi
b = 2 # b bir değişken ismi ve 2 bir integer veri tipi

# Aritmetik işlemlerin sonuçlarını değişkenlere atama
total = a + b
diff = a - b
product = a * b
division = a / b
reminder = a % b
floor_division = a // b
exponential = a ** b

# I should have used sum instead of total but sum is a built-in function - try to avoid overriding built-in functions
print(total) # if you do not label your print with some string, you never know where the result is coming from
print('a + b = ', total)
print('a - b = ', diff)
print('a * b = ', product)
print('a / b = ', division)
print('a % b = ', reminder)
print('a // b = ', floor_division)
print('a ** b = ', exponentiation)
```

**Örnek:**

```py
print('== Addition, Subtraction, Multiplication, Division, Modulus ==')

# Declaring values and organizing them together
num_one = 3
num_two = 4

# Aritmetik operasyonlar
toplam = num_one + num_two
fark = num_two - num_one
carpim = num_one * num_two
bolum = num_two / num_one
kalan = num_two % num_one

# Printing values with label
print('toplam: ', total)
print('fark: ', diff)
print('carpim: ', product)
print('bolum: ', div)
print('kalan: ', remainder)
```

Noktalardan birleştirmeye başlayalım ve bildiklerimizi kullanarak alan, hacim, yoğunluk, ağırlık, çevre, mesafe, kuvvet hesaplamaları yapalım.
**Örnek:**

```py
# Dairenin alanını hesaplama
radius = 10                                 # dairenin yarıçapı
area_of_circle = 3.14 * radius ** 2         # ** işareti üs alma demek
print('Area of a circle:', area_of_circle)

# Dikdörtgenin alanını hesaplama
height = 10
width = 20
area_of_rectangle = height * width
print('Area of a rectangle:', area_of_rectangle)

# Bir nesnenin ağırlığını hesaplama
mass = 75
gravity = 9.81
weight = mass * gravity
print(weight, 'N')                         # Ağırlığı birimiyle yazdırma
# Bir sıvının yoğunluğunu hesaplama
mass = 75 # Kg cinsinden
volume = 0.075 # metreküp
density = mass / volume # 1000 Kg/m^3

```

### Karşılaştırma Operatörleri

Programlamada sıkça değerleri karşılaştırırız ve iki değeri karşılaştırmak için karşılaştırma operatörlerini (comparison operators) kullanırız.
Bir değerin diğer değerden büyük, küçük veya eşit olup olmadığını kontrol ederiz. Aşağıdaki tablo, Python karşılaştırma operatörlerini göstermektedir ve [w3shool](https://www.w3schools.com/python/python_operators.asp)’dan alınmıştır. 

![Comparison Operators](../images/comparison_operators.png)
**Örnek: Karşılaştırma Operatörleri**

```py
print(3 > 2)     # True, çünkü 3, 2'den büyük
print(3 >= 2)    # True, çünkü 3, 2'den büyük
print(3 < 2)     # False, çünkü 3, 2'den büyük
print(2 < 3)     # True, çünkü 2, 3'ten küçük
print(2 <= 3)    # True, çünkü 2, 3'ten küçük
print(3 == 2)    # False, çünkü 3, 2'ye eşit değil
print(3 != 2)    # True, çünkü 3, 2'ye eşit değil
print(len('mango') == len('avocado'))  # False
print(len('mango') != len('avocado'))  # True
print(len('mango') < len('avocado'))   # True
print(len('milk') != len('meat'))      # False
print(len('milk') == len('meat'))      # True
print(len('tomato') == len('potato'))  # True
print(len('python') > len('dragon'))   # False


# Bir şeyleri karşılaştırmak True veya False değerini verir.

print('True == True: ', True == True)
print('True == False: ', True == False)
print('False == False:', False == False)
```

Python, karşılaştırma operatörlerine ek olarak bunları kullanır:

- _is_: İki değişken de aynı objeyse true döner (x is y)
- _is not_: Değişkenler aynı obje değilse true döner(x is not y)
- _in_: Sorgulanan list belirli bir öğeyi içeriyorsa true döner (x in y)
- _not in_: Sorgulanan liste belirli bir öğeyi içermiyorsa true döner (x not in y)

```py
print('1 is 1', 1 is 1)                   # True - çünkü veri değerleri aynı
print('1 is not 2', 1 is not 2)           # True - çünkü 1, 2 değil
print('A in Asabeneh', 'A' in 'Asabeneh') # True - A found in the string
print('B in Asabeneh', 'B' in 'Asabeneh') # False - there is no uppercase B
print('coding' in 'coding for all') # True - çünkü coding for all içinde coding kelimesi var
print('a in an:', 'a' in 'an')      # True
print('4 is 2 ** 2:', 4 is 2 ** 2)   # True
```

### Mantıksal Operatörler

Diğer programlama dillerinin aksine python mantıksal operatörler için _and_, _or_ and _not_ kelimelerini kullanır. Mantıksal operatörler, mantıksal ifadeleri bağlamak için kullanılır.

![Logical Operators](../images/logical_operators.png)

```py
print(3 > 2 and 4 > 3) # True - because both statements are true
print(3 > 2 and 4 < 3) # False - because the second statement is false
print(3 < 2 and 4 < 3) # False - because both statements are false
print('True and True: ', True and True)
print(3 > 2 or 4 > 3)  # True - because both statements are true
print(3 > 2 or 4 < 3)  # True - because one of the statements is true
print(3 < 2 or 4 < 3)  # False - because both statements are false
print('True or False:', True or False)
print(not 3 > 2)     # False - because 3 > 2 is true, then not True gives False
print(not True)      # False - Negation, the not operator turns true to false
print(not False)     # True
print(not not True)  # True
print(not not False) # False

```

🌕 Sınırsız enerjin var. 3. günün challenge’larını tamamladın ve mükemmellik yolunda üç adım ileridesin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar - 3. Gün

1. Yaşını bir integer değişken olarak ata
2. Boyunu bir float değişken olarak ata
3. Karmaşık sayılar tutan bir değişken tanımla
4. Kullanıcıdan üçgenin tabanını ve yüksekliğini alıp alanını hesaplayan kodu yaz (alan = taban * yükseklik / 2)

```py
    Enter base: 20
    Enter height: 10
    The area of the triangle is 100
```

5. Kullanıcıdan bir üçgenin a, b ve c kenarlarını girdi alıp çevresini hesaplayan kodu yaz (çevre = a + b + c)

```py
Enter side a: 5
Enter side b: 4
Enter side c: 3
The perimeter of the triangle is 12
```

6. Kullanıcıdan bir dikdörtgenin enini ve boyunu girdi alıp alanını ve çevresini hesaplayan kodu yaz (alan = en x boy) ve (çevre = 2 x (en + boy)
7. Kullanıcıdan bir dairenin yarıçapını girmesini isteyen bir script yaz. Ardından dairenin alanını ve çevresini hesapla (alan = pi x r x r) ve (çevre = 2 x pi x r), pi = 3.14
8. y = 2x - 2 doğrusu için eğim , x eksenini kestiği nokta ve y eksenini kestiği nokta değerlerini hesaplayın.
9. Eğim formülü (m = y2-y1/x2-x1). (2, 2) ve (6,10) noktalarının eğimini ve [Öklid uzaklığını](https://en.wikipedia.org/wiki/Euclidean_distance#:~:text=In%20mathematics%2C%20the%20Euclidean%20distance,being%20called%20the%20Pythagorean%20distance.)  bul
10. 8. ve 9. alıştırmadaki eğimleri kıyasla
11. (y = x^2 + 6x + 9) y değerini hesapla. Farklı x değerleri deneyerek hangi x değerinin y'yi 0 yaptığını bul
12. 'python' ve 'dragon' değerlerinin uzunluklarını hesapla ve yanlış bir karşılaştırma ifadesi yaz
13. and operatörünü kullanarak 'on' ifadesinin hem 'python' hem de 'dragon' içinde bulunup bulunmadığını kontrol et
14. _I hope this course is not full of jargon_.cümlesinde in operatörünü kullanarak _jargon_ kelimesinin cümlede olup olmadığını kontrol edin.
15. 'on' ifadesi ne 'dragon' ne de 'python' içinde yoktur anlamına gelen mantıksal ifadeyi yaz
16. _python_ metninin uzunluğunu bul, ardından değeri float’a çevir ve daha sonra string’e dönüştür
17. Çift sayılar 2’ye bölündüğünde kalan 0’dır. Python kullanarak bir sayının çift olup olmadığını nasıl kontrol edersin?
18. 7 sayısının 3’e bölünmesinin taban bölmesi (floor division) değerinin, 2.7’nin int’e çevrilmiş değerine eşit olup olmadığını kontrol et
19. Check if type of '10' is equal to type of 10
20. '10' değerinin tipi ile 10 değerinin tipinin eşit olup olmadığını kontrol et
21. Kullanıcıdan çalışma saatini ve saat başı ücreti girmesini isteyen bir Python scripti yaz ve kişinin maaşını hesapla

```py
Enter hours: 40
Enter rate per hour: 28
Your weekly earning is 1120
```

22. Kullanıcıdan kaç yıl yaşadığını girdi alan bir kod yaz. Bu kişinin kaç yıl yaşadığını hesapla.

```py
Enter number of years you have lived: 100
You have lived for 3153600000 seconds.
```

23. Aşağıdaki tabloyu yazdıran bir Python kodu yazın

```py
1 1 1 1 1
2 1 2 4 8
3 1 3 9 27
4 1 4 16 64
5 1 5 25 125
```

🎉 TEBRİKLER ! 🎉

[<< 2. Gün](../02_Day_Variables_builtin_functions/02_variables_builtin_functions.md) | [4. Gün >>](../04_Day_Strings/04_strings.md)
