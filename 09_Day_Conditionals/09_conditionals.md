<div align="center">
  <h1> 30 Günde Python: 9. Gün - Koşullu İfadeler</h1>
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

[<< 8. Gün](../08_Day_Dictionaries/08_dictionaries.md) | [10. Gün >>](../10_Day_Loops/10_loops.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 9. Gün](#-day-9)
  - [Koşullu İfadeler](#conditionals)
    - [If Koşulu](#if-condition)
    - [If Else](#if-else)
    - [If Elif Else](#if-elif-else)
    - [Short Hand (Kısaltılmış Koşul)](#short-hand)
    - [İç İçe Koşullar](#nested-conditions)
    - [If Koşulu ve And Mantıksal Operatörü](#if-condition-and-logical-operators)
    - [If Koşulu ve Or Mantıksal Operatörü](#if-and-or-logical-operators)
  - [💻 Alıştırmalar: 9. Gün](#-exercises-day-9)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)
    - [Alıştırmalar: 3. Seviye](#exercises-level-3)

# 📘 9. Gün

## Koşullu İfadeler

Varsayılan olarak, Python scriptindeki ifadeler üstten alta doğru sıralı şekilde çalıştırılır. Eğer işleme mantığı bunu gerektiriyorsa, yürütme sırasının akışı iki şekilde değiştirilebilir:

- Koşullu yürütme (Conditional execution): Belirli bir ifade doğruysa, bir veya daha fazla ifadenin bulunduğu bir blok çalıştırılır.
- Tekrarlı yürütme (Repetitive execution): Belirli bir ifade doğru olduğu sürece, bir veya daha fazla ifadenin bulunduğu bir blok tekrarlı olarak çalıştırılır.

Bu bölümde if, else, elif ifadelerini öğreneceğiz. Önceki bölümlerde öğrendiğimiz karşılaştırma (comparison) ve mantıksal (logical) operatörler burada faydalı olacaktır.

### If Koşulu

Python ve diğer programlama dillerinde _if_ anahtar kelimesi, bir koşulun doğru olup olmadığını kontrol etmek ve koşul doğruysa blok kodunu çalıştırmak için kullanılır. İki noktadan (:) sonra girintiye (indentation) dikkat edin.

```py
# sözdizimi
if koşulu:
    koşul doğruysa bu
    kod bloğu çalışır
```

**Örnek:**

```py
a = 3
if a > 0:
    print('A is a positive number')
# A bir pozitif sayıdır
```

Yukarıdaki örnekte gördüğün gibi, 3, 0’dan büyüktür. Koşul doğru olduğu için blok kodu çalıştırıldı.
Ancak koşul yanlış olsaydı, sonucu göremezdik. Yanlış bir koşulun sonucunu görmek için başka bir blok gerekir; bu blok _else_ olacaktır.

### If Else

Koşul doğruysa ilk blok çalıştırılır, değilse else bloğu çalışır

```py
# sözdizimi
if koşulu:
    koşul doğruysa kodun bu kısmı çalışır
else:
     koşul yanlışsa kodun bu kısmı çalışır
```

**Örnek:**

```py
a = 3
if a < 0:
    print('A is a negative number')
else:
    print('A is a positive number')
```

Üstteki koşul yanlış, bu yüzden else bloğu çalışır. Peki ya ikiden fazla koşulumuz varsa? O  _elif_ kullanırız

### If Elif Else

Günlük hayatımızda, her gün kararlar alırız. Kararları sadece bir veya iki koşulu kontrol ederek değil, birden fazla koşulu değerlendirerek veririz. Hayata benzer şekilde, programlama da koşullarla doludur. Birden fazla koşul olduğunda _elif_ kullanırız.

```py
# sözdizimi
if koşulu:
    code
elif koşulu:
    code
else:
    code

```

**Örnek:**

```py
a = 0
if a > 0:
    print('A is a positive number')
elif a < 0:
    print('A is a negative number')
else:
    print('A is zero')
```

### Short Hand (Kısaltılmış Koşul)

```py
# sözdizimi
code if condition else code
```

**Örnek:**

```py
a = 3
print('A is positive') if a > 0 else print('A is negative') # ilk koşul sağlandı, 'A is positive' yazdırılacak
```

### İç İçe Koşullar

Koşullar iç içe olabilir

```py
# sözdizimi
if koşulu:
    code
    if koşulu:
    code
```

**Örnek:**

```py
a = 0
if a > 0:
    if a % 2 == 0:
        print('A is a positive and even integer')
    else:
        print('A is a positive number')
elif a == 0:
    print('A is zero')
else:
    print('A is a negative number')

```

Mantıksal _and_ operatörünü kullanarak iç içe koşullardan kaçınabiliriz

### If Koşulu ve And Mantıksal Operatörü

```py
# sözdizimi
if koşul1 and koşul2:
    code
```

**Örnek:**

```py
a = 0
if a > 0 and a % 2 == 0:
        print('A is an even and positive integer')
elif a > 0 and a % 2 !=  0:
     print('A is a positive integer')
elif a == 0:
    print('A is zero')
else:
    print('A is negative')
```

### If Koşulu ve Or Mantıksal Operatörü

```py
# sözdizimi
if koşul1 or koşul2:
    code
```

**Örnek:**

```py
user = 'James'
access_level = 3
if user == 'admin' or access_level >= 4:
        print('Access granted!')
else:
    print('Access denied!')
```

🌕 Harika gidiyorsun. Asla pes etme çünkü güzel şeyler zaman alır. 9. günün challenge’larını tamamladın ve mükemmellik yolunda 9 adım ileridesin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 9. Gün

### Alıştırmalar: 1. Seviye

1. Kullanıcıdan input(“Enter your age: ”) ile yaşını al. Eğer kullanıcı 18 veya daha büyükse, geri bildirim ver: You are old enough to drive. Eğer 18’den küçükse, eksik yıl sayısı kadar beklemesi gerektiğini bildir. Çıktıt:

    ```sh
    Enter your age: 30
    You are old enough to learn to drive.
    Output:
    Enter your age: 15
    You need 3 more years to learn to drive.
    ```

2. my_age ve your_age değerlerini if … else ile karşılaştır. Kim daha yaşlı (ben mi sen mi)? Yaşı girdi olarak almak için input(“Enter your age: ”) kullan. Yaş farkı için nested condition kullanarak: 1 yıl fark varsa "year", Daha büyük fark varsa "years", my_age = your_age ise özel bir metin yazdır Çıktı:

    ```sh
    Enter your age: 30
    You are 5 years older than me.
    ```

3. Kullanıcıdan input ile iki sayı al. a, b'den büyükse "a is greater than b", a, b'den küçükse "a is smaller than b", eşitlerse "a is equal to b" döndür. Çıktı:

```sh
Enter number one: 4
Enter number two: 3
4 is greater than 3
```

### Alıştırmalar: 2. Seviye

   1. Öğrencilerin notuna göre harf notunu veren kodu yaz:

        ```sh
        80-100, A
        70-89, B
        60-69, C
        50-59, D
        0-49, F
        ```

   1. Mevsimin Autumn, Winter, Spring veya Summer olduğunu kontrol et. Kullanıcı inputu:
    September, October or November ise mevsim Autumn.
    December, January veya February ise mevsim Winter.
    March, April or May ise mevsim Spring
    June, July or August ise mevsim Summer
   
   2. Aşağıdaki list bazı meyveleri içeriyor:

    ```sh
    fruits = ['banana', 'orange', 'mango', 'lemon']
    ```

  Eğer bir meyve listede yoksa, meyveyi listeye ekle ve güncellenmiş listeyi yazdır. Eğer meyve zaten varsa: print('That fruit already exist in the list')

### Alıştırmalar: 3. Seviye

   1. Burada bir person sözlüğü var. Dilediğin gibi değiştirebilirsin!

```py
        person={
    'first_name': 'Asabeneh',
    'last_name': 'Yetayeh',
    'age': 250,
    'country': 'Finland',
    'is_marred': True,
    'skills': ['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address': {
        'street': 'Space street',
        'zipcode': '02210'
    }
    }
```

  * Person sözlüğünde skills keyi varsa, skills listinin ortadaki itemini yazdır.
  * Person sözlüğünde skills keyi varsa, kişinin 'Python' becerisine sahip olup olmadığını kontrol et ve sonucu yazdır.
  * Eğer kişinin skillsi sadece JavaScript ve React ise: print('He is a front end developer'). Eğer kişinin skillsi içinde Node, Python, MongoDB varsa:   print('He is a backend developer'). Eğer kişinin skills içinde React, Node, MongoDB varsa: print('He is a fullstack developer'). Aksi takdirde print('unknown title'). (Daha doğru sonuçlar için daha fazla koşul iç içe (nested) kullanılabilir)
  * Eğer kişi evli ise ve Finlandiya’da yaşıyorsa, bilgileri aşağıdaki formatta yazdır.

```py
    Asabeneh Yetayeh lives in Finland. He is married.
```

🎉 TEBRİKLER ! 🎉

[<< 8. Gün](../08_Day_Dictionaries/08_dictionaries.md) | [10. Gün >>](../10_Day_Loops/10_loops.md)
