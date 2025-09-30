<div align="center">
  <h1> 30 Günde Python: 10. Gün - Döngüler</h1>
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

[<< 9. Gün](../09_Day_Conditionals/09_conditionals.md) | [11. Gün >>](../11_Day_Functions/11_functions.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 10. Gün](#-day-10)
  - [Döngüler](#loops)
    - [While Döngüsü](#while-loop)
    - [Break ve Continue - 1. Kısım](#break-and-continue---part-1)
    - [For Döngüsü](#for-loop)
    - [Break ve Continue - 2. Kısım](#break-and-continue---part-2)
    - [Range Fonksiyonu](#the-range-function)
    - [İç İçe For Döngüsü](#nested-for-loop)
    - [For Else](#for-else)
    - [Pass](#pass)
  - [💻 Alıştırmalar: 10. Gün](#-exercises-day-10)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)
    - [Alıştırmalar: 3. Seviye](#exercises-level-3)

# 📘 10. Gün

## Döngüler

Hayat rutinlerle dolu. Programlamada da sık sık tekrarlayan tasklar yaparız. Tekrarlayan görevleri gerçekleştirmek için programlama dilleri döngüleri kullanır. Python programlama dili aşağıdaki iki döngüyü sağlar:

1. while döngüsü
2. for döngüsü

### While Döngüsü

While döngüsü kurmak için _while_ rezerve kelimesini kullanırız. Belirli bir koşul sağlanana kadar bir blok ifadeyi tekrar tekrar çalıştırmak için kullanılır. Koşul False olduğunda döngü sonrası kod satırlarının yürütülmesine devam edilir.

```py
  # sözdizimi
while koşulu:
    kod
```

**Örnek:**

```py
count = 0
while count < 5:
    print(count)
    count = count + 1
#prints from 0 to 4
```

Yukarıdaki while döngüsünde, koşul count = 5 olduğunda false olur. Bu noktada döngü durur.
Koşul artık doğru olmadığında bir kod bloğunu bir kez çalıştırmak istiyorsak, _else_ ifadesini kullanabiliriz.

```py
  # sözdizimi
while koşulu:
    kod
else:
    kod
```

**Örnek:**

```py
count = 0
while count < 5:
    print(count)
    count = count + 1
else:
    print(count)
```

Yukarıdaki döngü koşulu, count 5 olduğunda False olacak ve döngü duracaktır; ardından yürütme else bloğuna geçer. Sonuç olarak 5 yazdırılır.

### Break ve Continue - 1. Kısım

- Break: Döngüden çıkmak istediğimizde break kullanırız

```py
# sözdizimi
while koşul:
    kod
    if başka koşul:
        break
```

**Örnek:**

```py
count = 0
while count < 5:
    print(count)
    count = count + 1
    if count == 3:
        break
```

Yukarıdaki while döngüsü yalnızca 0, 1, 2 yazdırır, 3’e ulaştığında durur.

- Continue: continue ifadesiyle mevcut iterasyonu atlayabilir ve bir sonraki iterasyona devam edebiliriz:

```py
  # sözdizimi
while koşul:
    kod
    if başka koşul:
        continue
```

**Örnek:**

```py
count = 0
while count < 5:
    if count == 3:
        count = count + 1
        continue
    print(count)
    count = count + 1
```

Yukarıdaki while döngüsü yalnızca 0, 1, 2 ve 4 yazdırır, 3’ü atlar.

### For Döngüsü

_for_ anahtar kelimesi, bir for döngüsü oluşturmak için kullanılır. Diğer programlama dillerine benzerdir ancak bazı sözdizimi farklılıkları vardır. Döngü, list,  tuple, dictionary, set veya string gibi bir dizi (sequence) üzerinde yineleme (iteration) yapmak için kullanılır.

- List ile for döngüsü

```py
# sözdizimi
for iterator in lst:
    kod
```

**Örnek:**

```py
numbers = [0, 1, 2, 3, 4, 5]
for number in numbers: # number is temporary name to refer to the list's items, valid only inside this loop
    print(number)       # the numbers will be printed line by line, from 0 to 5
```

- String ile for döngüsü

```py
# sözdizimi
for iterator in string:
    kod
```

**Örnek:**

```py
language = 'Python'
for letter in language:
    print(letter)


for i in range(len(language)):
    print(language[i])
```

- Tuple ile for döngüsü

```py
# sözdizimi
for iterator in tpl:
    kod
```

**Örnek:**

```py
numbers = (0, 1, 2, 3, 4, 5)
for number in numbers:
    print(number)
```

- Dictionary ile for döngüsü
  Looping through a dictionary gives you the key of the dictionary.

```py
  # sözdizimi
for iterator in dct:
    kod
```

**Örnek:**

```py
person = {
    'ad':'Asabeneh',
    'soyad':'Yetayeh',
    'yas':250,
    'ulke':'Finland',
    'evli_mi':True,
    'beceriler':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'adres':{
        'sokak':'Space street',
        'zipcode':'02210'
    }
}
for key in person:
    print(key)

for key, value in person.items():
    print(key, value) # this way we get both keys and values printed out
```

- Set ile döngüler

```py
# sözdizimi
for iterator in st:
    kod
```

**Örnek:**

```py
it_companies = {'Facebook', 'Google', 'Microsoft', 'Apple', 'IBM', 'Oracle', 'Amazon'}
for company in it_companies:
    print(company)
```

### Break ve Continue - 2. Kısım

Hatırlatma:
_Break_: We use break when we like to stop our loop before it is completed.

```py
# sözdizimi
for iterator in sequence:
    kod
    if koşulu:
        break
```

**Example:**

```py
numbers = (0,1,2,3,4,5)
for number in numbers:
    print(number)
    if number == 3:
        break
```

In the above example, the loop stops when it reaches 3.

Continue: We use continue when we like to skip some of the steps in the iteration of the loop.

```py
  # sözdizimi
for iterator in sequence:
    kod
    if koşulu:
        continue
```

**Örnek:**

```py
numbers = (0,1,2,3,4,5)
for number in numbers:
    print(number)
    if number == 3:
        continue
    print('Next number should be ', number + 1) if number != 5 else print("loop's end") # for short hand conditions need both if and else statements
print('outside the loop')
```

In the example above, if the number equals 3, the step *after* the condition (but inside the loop) is skipped and the execution of the loop continues if there are any iterations left.

### Range Fonksiyonu

_range()_ fonksiyonu bir sayı listesi (dizi) oluşturmak için kullanılır. _range(start, end, step)_ 3 parametre alır: start, end ve increment. Varsayılan olarak 0'dan başlar ve 1'er 1'er artar. Bir range dizisi en az 1 argüman (end) gerektirir.
range kullanarak sayı dizileri oluşturma örneği:

```py
lst = list(range(11)) 
print(lst) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
st = set(range(1, 11))    # 2 arguments indicate start and end of the sequence, step set to default 1
print(st) # {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}

lst = list(range(0,11,2))
print(lst) # [0, 2, 4, 6, 8, 10]
st = set(range(0,11,2))
print(st) #  {0, 2, 4, 6, 8, 10}
```

```py
# sözdizimi
for iterator in range(start, end, step):
```

**Örnek:**

```py
for number in range(11):
    print(number)   # prints 0 to 10, not including 11
```

### İç İçe For Döngüsü

We can write loops inside a loop.

```py
# sözdizimi
for x in y:
    for t in x:
        print(t)
```

**Örnek:**

```py
person = {
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
for key in person:
    if key == 'skills':
        for skill in person['skills']:
            print(skill)
```

### For Else

If we want to execute some message when the loop ends, we use else.

```py
# sözdizimi
for iterator in range(start, end, step):
    bir şeyler yap
else:
    print('The loop ended')
```

**Örnek:**

```py
for number in range(11):
    print(number)   # prints 0 to 10, not including 11
else:
    print('The loop stops at', number)
```

### Pass

In python when statement is required (after semicolon), but we don't like to execute any code there, we can write the word _pass_ to avoid errors. Also we can use it as a placeholder, for future statements.

**Örnek:**

```py
for number in range(6):
    pass
```

🌕 Büyük bir dönüm noktasına ulaştın, durdurulamazsın. Devam et! 10. günün challengelarını tamamladın ve mükemmelliğe giden yolda 10 adım ilerledin.  Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 10. Gün

### Alıştırmalar: 1. Seviye

1. 0’dan 10’a kadar iterate etmek için for döngüsü kullan, aynı işlemi while döngüsü ile yap.
2. 10’dan 0’a kadar iterate etmek için for döngüsü kullan, aynı işlemi while döngüsü ile yap.
3. Yedi kez print() çağıran bir döngü yaz, böylece çıktı olarak aşağıdaki üçgen elde edilir:

   ```py
     #
     ##
     ###
     ####
     #####
     ######
     #######
   ```

4. Aşağıdakini oluşturmak için iç içe döngüler yaz:

   ```sh
   # # # # # # # #
   # # # # # # # #
   # # # # # # # #
   # # # # # # # #
   # # # # # # # #
   # # # # # # # #
   # # # # # # # #
   # # # # # # # #
   ```

5. Aşağıdaki örüntüyü yazdır:

   ```sh
   0 x 0 = 0
   1 x 1 = 1
   2 x 2 = 4
   3 x 3 = 9
   4 x 4 = 16
   5 x 5 = 25
   6 x 6 = 36
   7 x 7 = 49
   8 x 8 = 64
   9 x 9 = 81
   10 x 10 = 100
   ```

6. Iterate through the list, ['Python', 'Numpy','Pandas','Django', 'Flask'] using a for loop and print out the items.
7. 0’dan 100’e kadar iterate etmek için for döngüsü kullan ve sadece çift sayıları yazdır
8. 0’dan 100’e kadar iterate etmek için for döngüsü kullan ve sadece tek sayıları yazdır
   
### Alıştırmalar: 2. Seviye
    
1.  0’dan 100’e kadar iterate etmek için for döngüsü kullan ve sayıların toplamını yazdır

   ```sh
   The sum of all numbers is 5050.
   ```

1. 0’dan 100’e kadar iterate etmek için for döngüsü kullan ve  çift sayıların toplamı ile tek sayıların toplamını ayrı ayrı yazdır

    ```sh
    The sum of all evens is 2550. And the sum of all odds is 2500.
    ```

### Alıştırmalar: 3. Seviye

1. data klasörüne git ve and use the [countries.py](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/countries.py) file. Loop through the countries and extract all the countries containing the word _land_.
1. Bu bir meyve listi, ['banana', 'orange', 'mango', 'lemon']. Döngü kullanarak listi tersine çevir
2. Go to the data folder and use the [countries_data.py](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/countries-data.py) file. 
   1. What are the total number of languages in the data
   2. Find the ten most spoken languages from the data
   3. Find the 10 most populated countries in the world

🎉 TEBRİKLER ! 🎉

[<< 9. Gün](../09_Day_Conditionals/09_conditionals.md) | [11. Gün >>](../11_Day_Functions/11_functions.md)
