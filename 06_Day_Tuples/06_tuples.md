<div align="center">
  <h1> 30 Günde Python: 6. Gün - Tuplelar</h1>
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

[<< 5. Gün](../05_Day_Lists/05_lists.md) | [7. Gün >>](../07_Day_Sets/07_sets.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [6. Gün](#day-6)
  - [Tuplelar](#tuples)
    - [Tuple Oluşturma](#creating-a-tuple)
    - [Tuple Uzunluğu](#tuple-length)
    - [Tuple İtemlerine Erişme](#accessing-tuple-items)
    - [Tupleları Bölme](#slicing-tuples)
    - [Tupleı Liste Dönüştürme](#changing-tuples-to-lists)
    - [Tupleda İtem Arama](#checking-an-item-in-a-tuple)
    - [Tupleları Birleştirme](#joining-tuples)
    - [Tupleı Silme](#deleting-tuples)
  - [💻 Alıştırmalar: 6. Gün](#-exercises-day-6)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)

# 6. Gün

## Tuplelar

Bir tuple, farklı veri tiplerinden oluşan, sıralı ve değiştirilemez (immutable) bir koleksiyondur. Tuple’lar parantez () ile yazılır. Bir tuple oluşturulduktan sonra içindeki değerler değiştirilemez. Tuple üzerinde add, insert, remove gibi yöntemler kullanılamaz çünkü değiştirilebilir (mutable) değildir. Liste kıyasla tupleın çok az metodu vardır. Tuple ile ilgili yöntemler şunlardır:

- tuple(): boş tuple oluşturmak için
- count(): bir itemden tupleda kaç tane olduğunu bulmak için
- index(): topledaki bir itemin indeksini bulmak için
- + operator: birden fazla tupleı birleştirip yeni tuple oluşturmak için

### Tuple Oluşturma

- Boş tuple oluşturma
  
  ```py
  # sözdizimi
  empty_tuple = ()
  # or using the tuple constructor
  empty_tuple = tuple()
  ```

- Başlangıç değerli tuple
  
  ```py
  # sözdizimi
  tpl = ('item1', 'item2','item3')
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  ```

### Tuple Uzunluğu

We use the _len()_ method to get the length of a tuple.

```py
# sözdizimi
tpl = ('item1', 'item2', 'item3')
len(tpl)
```

### Tuple İtemlerine Erişme

- Positif indeksleme
  Similar to the list data type we use positive or negative indexing to access tuple items.
  ![Accessing tuple items](../images/tuples_index.png)

  ```py
  # sözdizimi
  tpl = ('item1', 'item2', 'item3')
  first_item = tpl[0]
  second_item = tpl[1]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[0]
  second_fruit = fruits[1]
  last_index =len(fruits) - 1
  last_fruit = fruits[las_index]
  ```

- Negatif indeksleme
  Negative indexing means beginning from the end, -1 refers to the last item, -2 refers to the second last and the negative of the list/tuple length refers to the first item.
  ![Tuple Negative indexing](../images/tuple_negative_indexing.png)

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  first_item = tpl[-4]
  second_item = tpl[-3]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[-4]
  second_fruit = fruits[-3]
  last_fruit = fruits[-1]
  ```

### Slicing tuples

We can slice out a sub-tuple by specifying a range of indexes where to start and where to end in the tuple, the return value will be a new tuple with the specified items.

- Range of Positive Indexes

  ```py
  # sözdizimi
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[0:4]         # all items
  all_items = tpl[0:]         # all items
  middle_two_items = tpl[1:3]  # does not include item at index 3
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[0:4]    # all items
  all_fruits= fruits[0:]      # all items
  orange_mango = fruits[1:3]  # doesn't include item at index 3
  orange_to_the_rest = fruits[1:]
  ```

- Range of Negative Indexes

  ```py
  # sözdizimi
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[-4:]         # all items
  middle_two_items = tpl[-3:-1]  # does not include item at index 3 (-1)
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[-4:]    # all items
  orange_mango = fruits[-3:-1]  # doesn't include item at index 3
  orange_to_the_rest = fruits[-3:]
  ```

### Tupleı Liste Dönüştürme

Tupleları liste, listleri de tuplea çevirebiliriz. Tuple değiştirilemez (immutable) olduğu için, bir tupleı değiştirmek istiyorsak önce liste çevirmeliyiz.

```py
# sözdizimi
tpl = ('item1', 'item2', 'item3','item4')
lst = list(tpl)
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
fruits = list(fruits)
fruits[0] = 'apple'
print(fruits)     # ['apple', 'orange', 'mango', 'lemon']
fruits = tuple(fruits)
print(fruits)     # ('apple', 'orange', 'mango', 'lemon')
```

### Tupleda İtem Arama

Bir öğenin tuple içinde var olup olmadığını in kullanarak kontrol edebiliriz, sonuç boolean (True/False) olarak döner

```py
# sözdizimi
tpl = ('item1', 'item2', 'item3','item4')
'item2' in tpl # True
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
print('orange' in fruits) # True
print('apple' in fruits) # False
fruits[0] = 'apple' # TypeError: 'tuple' tuplelara item atanmaz
```

### Tupleları Birleştirme

Birden fazla tupleı + operatörüyle birleştirebiliriz

```py
# sözdizimi
tpl1 = ('item1', 'item2', 'item3')
tpl2 = ('item4', 'item5','item6')
tpl3 = tpl1 + tpl2
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
vegetables = ('Tomato', 'Potato', 'Cabbage','Onion', 'Carrot')
fruits_and_vegetables = fruits + vegetables
```

### Tupleı Silme

Bir tuple’dan tek bir öğeyi silmek mümkün değildir, ancak tüm tuple’ı _del_ kullanarak silebilirsin.

```py
# sözdizimi
tpl1 = ('item1', 'item2', 'item3')
del tpl1

```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
del fruits
```

🌕 Çok cesursun, bu noktaya kadar geldin. 6. günün challenge’larını tamamladın ve mükemmelliğe giden yolda 6 adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 6. Gün

### Alıştırmalar: 1. Seviye

1. Boş bir tuple oluştur
2. Kız ve erkek kardeşlerinin isimlerini içeren bir tuple oluştur (hayali kardeşler de olabilir)
3. Kardeşlerin tuple’larını birleştir ve siblings değişkenine ata
4. Kaç kardeşin olduğunu bul
5. siblings tuple’ını değiştirerek anne ve babanın isimlerini ekle ve family_members değişkenine ata

### Alıştırmalar: 2. Seviye

1. family_members tuple’ından siblings ve parents değişkenlerini unpack et
2. Fruits, vegetables ve animal products tuple’larını oluştur, üç tuple’ı birleştir ve food_stuff_tp değişkenine ata
3. food_stuff_tp tuple’ını food_stuff_lt listine çevir
4. food_stuff_tp tuple’ından veya food_stuff_lt listinden ortadaki itemi veya öğeleri böl (slice)
5. food_stuff_lt listinden ilk üç ve son üç itemi böl (slice)
6. food_stuff_tp tuple’ını tamamen sil
7. Aşağıdaki itemlerin tuple’da olup olmadığını kontrol et:

- 'Estonia'nın bir Nordik ülkesi olup olmadığını kontrol et
- 'Iceland'ın bir Nordik ülkesi olup olmadığını kontrol et

  ```py
  nordic_countries = ('Denmark', 'Finland','Iceland', 'Norway', 'Sweden')
  ```
  
🎉 TEBRİKLER ! 🎉

[<< 5. Gün](../05_Day_Lists/05_lists.md) | [7. Gün >>](../07_Day_Sets/07_sets.md)
