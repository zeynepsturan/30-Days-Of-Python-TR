<div align="center">
  <h1> 30 Günde Python: 5. Gün - Listler</h1>
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

[<< 4. Gün](../04_Day_Strings/04_strings.md) | [6. Gün >>](../06_Day_Tuples/06_tuples.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [5. Gün](#day-5)
  - [Listler](#lists)
    - [List Nasıl Oluşturulur?](#how-to-create-a-list)
    - [Pozitif İndeksleme Kullanarak List İtemlerine Erişme](#accessing-list-items-using-positive-indexing)
    - [Negatif İndeksleme Kullanarak List İtemlerine Erişme](#accessing-list-items-using-negative-indexing)
    - [List Itemlerini Unpacking Etme](#unpacking-list-items)
    - [Listten İtem Bölme](#slicing-items-from-a-list)
    - [Listleri Modifiye Etme](#modifying-lists)
    - [Listte İtem Kontrolü](#checking-items-in-a-list)
    - [Listin Sonuna Item Ekleme](#adding-items-to-a-list)
    - [Listin Arasına Item Ekleme](#inserting-items-into-a-list)
    - [Listten İtem Silme](#removing-items-from-a-list)
    - [Pop Kullanarak İtem Silme](#removing-items-using-pop)
    - [Del Kullanarak İtem Silme](#removing-items-using-del)
    - [List İtemlerini Temizleme](#clearing-list-items)
    - [Listi Kopyalama](#copying-a-list)
    - [Listleri Birleştirme](#joining-lists)
    - [List İtemlerini Sayma](#counting-items-in-a-list)
    - [Bir İtemin İndeksini Bulma](#finding-index-of-an-item)
    - [Listi Tersine Çevirme](#reversing-a-list)
    - [List İtemlerini Sıralama](#sorting-list-items)
  - [💻 Alıştırmalar: 5. Gün](#-exercises-day-5)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)

# 5. Gün

## Listler

Python’da veri gruplarını saklamak için kullanılan dört temel koleksiyon yapısı vardır:

- List: Sıralı ve değiştirilebilir (modifiable) bir koleksiyondur. Tekrarlanan elemanlara izin verir.
- Tuple: Sıralı ama değiştirilemez (immutable) bir koleksiyondur. Tekrarlanan elemanlara izin verir.
- Set: Sırasız, indekslenemez ve değiştirilemez bir koleksiyondur fakat sete yeni eleman ekleyebiliriz. Tekrarlanan elemanlara izin verilmez.
- Dictionary: Sırasız, değiştirilebilir (modifiye edilebilir) ve indekslenebilir bir koleksiyondur. Tekrarlanan elemanlara izin verilmez.

List, farklı veri tiplerinden oluşan, sıralı ve değiştirilebilir (mutable) bir koleksiyondur. Bir list boş olabilir veya farklı veri tiplerinden öğeler içerebilir.

### List Nasıl Oluşturulur?

Python'da iki farklı şekilde list oluşturabiliiriz:

- list built-in Fonksiyonunu Kullanarak

```py
# sözdizimi
lst = list()
```

```py
empty_list = list() # bu boş bir list, listte item yok
print(len(empty_list)) # 0
```

- Köşeli parantez [] kullanarak

```py
# sözdizimi
lst = []
```

```py
empty_list = [] # bu boş bir list, listte item yok
print(len(empty_list)) # 0
```

Başlangıç değerli listler oluşturalım ve _len()_ fonksiyonuyla list uzunluğunu bulalım

```py
fruits = ['banana', 'orange', 'mango', 'lemon']                     # meyve listi
vegetables = ['Tomato', 'Potato', 'Cabbage','Onion', 'Carrot']      # sebze listi
animal_products = ['milk', 'meat', 'butter', 'yoghurt']             # hayvansal gıda listi
web_techs = ['HTML', 'CSS', 'JS', 'React','Redux', 'Node', 'MongDB'] # web teknolojileri listi
countries = ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway'] # ülke listi

# listleri ve uzunluklarını yazdırma
print('Fruits:', fruits)
print('Number of fruits:', len(fruits))
print('Vegetables:', vegetables)
print('Number of vegetables:', len(vegetables))
print('Animal products:',animal_products)
print('Number of animal products:', len(animal_products))
print('Web technologies:', web_techs)
print('Number of web technologies:', len(web_techs))
print('Countries:', countries)
print('Number of countries:', len(countries))
```

```sh
çıktı
Fruits: ['banana', 'orange', 'mango', 'lemon']
Number of fruits: 4
Vegetables: ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
Number of vegetables: 5
Animal products: ['milk', 'meat', 'butter', 'yoghurt']
Number of animal products: 4
Web technologies: ['HTML', 'CSS', 'JS', 'React', 'Redux', 'Node', 'MongDB']
Number of web technologies: 7
Countries: ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']
Number of countries: 5
```

- Listler farklı veri tiplerinden veriler içerebilir

```py
 lst = ['Asabeneh', 250, True, {'country':'Finland', 'city':'Helsinki'}] # farklı veri tipleri içeren list
```

### Pozitif İndeksleme Kullanarak List İtemlerine Erişme

Listdeki her bir iteme indekslerini kullanarak erişiriz. List indeksleri 0’dan başlar. Aşağıdaki resim, indekslemeyi açıkça gösterir.

![List index](../images/list_index.png)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
first_fruit = fruits[0] # indeksini kullanarak ilk iteme erişme
print(first_fruit)      # banana
second_fruit = fruits[1]
print(second_fruit)     # orange
last_fruit = fruits[3]
print(last_fruit) # lemon
# Last index
last_index = len(fruits) - 1
last_fruit = fruits[last_index]
```

### Negatif İndeksleme Kullanarak List İtemlerine Erişme

Negatif indeksleme, listin sonundan başlamayı ifade eder; -1 son öğeyi, -2 sondan bir önceki itemi gösterir.

![List negative indexing](../images/list_negative_indexing.png)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
first_fruit = fruits[-4]
last_fruit = fruits[-1]
second_last = fruits[-2]
print(first_fruit)      # banana
print(last_fruit)       # lemon
print(second_last)      # mango
```

### List Itemlerini Unpacking Etme

```py
lst = ['item1','item2','item3', 'item4', 'item5']
first_item, second_item, third_item, *rest = lst
print(first_item)     # item1
print(second_item)    # item2
print(third_item)     # item3
print(rest)           # ['item4', 'item5']

```

```py
# ilk örnek
fruits = ['banana', 'orange', 'mango', 'lemon','lime','apple']
first_fruit, second_fruit, third_fruit, *rest = fruits 
print(first_fruit)     # banana
print(second_fruit)    # orange
print(third_fruit)     # mango
print(rest)           # ['lemon','lime','apple']

# ikinci örnek
first, second, third,*rest, tenth = [1,2,3,4,5,6,7,8,9,10]
print(first)          # 1
print(second)         # 2
print(third)          # 3
print(rest)           # [4,5,6,7,8,9]
print(tenth)          # 10

# üçüncü örnek
countries = ['Germany', 'France','Belgium','Sweden','Denmark','Finland','Norway','Iceland','Estonia']
gr, fr, bg, sw, *scandic, es = countries
print(gr)
print(fr)
print(bg)
print(sw)
print(scandic)
print(es)
```

### Listten İtem Bölme

- Pozitif İndeksleme: Pozitif indekslerin bir aralığını başlangıç (start), bitiş (end) ve adım (step) değerlerini belirterek seçebiliriz; dönen değer yeni bir list olur. (Varsayılan değerler: start = 0, end = len(lst) - 1 (son öğe), step = 1)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
all_fruits = fruits[0:4] # tüm meyveleri döner
# üsttekiyle aynı sonucu verir
all_fruits = fruits[0:] # stop değeri vermezsek kalan tüm itemleri alır
orange_and_mango = fruits[1:3] # ilk indeksi dahil etmez
orange_mango_lemon = fruits[1:]
orange_and_lemon = fruits[::2] # burada 3. argüman olan step'i kullandık. It will take every 2cnd item - ['banana', 'mango']
```

- Negatif İndeksleme: Negatif indekslerin bir aralığını başlangıç (start), bitiş (end) ve adım (step) değerlerini belirleyerek seçebiliriz; dönen değer yeni bir list olur.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
all_fruits = fruits[-4:] # tüm meyveleri döner
orange_and_mango = fruits[-3:-1] # son indeksi dahil etmez,['orange', 'mango']
orange_mango_lemon = fruits[-3:] # -3 indeksinden başlayarak sona kadar olan öğeleri verir,['orange', 'mango', 'lemon']
reverse_fruits = fruits[::-1] # Negatif bir adım (step), listenin ters sırayla alınmasını sağlar,['lemon', 'mango', 'orange', 'banana']
```

### Listleri Modifiye Etme

List değiştirilebilir (modifiable) bir koleksiyondur. Meyve listini modifiye edelim

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits[0] = 'avocado'
print(fruits)       #  ['avocado', 'orange', 'mango', 'lemon']
fruits[1] = 'apple'
print(fruits)       #  ['avocado', 'apple', 'mango', 'lemon']
last_index = len(fruits) - 1
fruits[last_index] = 'lime'
print(fruits)        #  ['avocado', 'apple', 'mango', 'lime']
```

### Listte İtem Kontrolü

Checking an item if it is a member of a list using *in* operator. See the example below.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
does_exist = 'banana' in fruits
print(does_exist)  # True
does_exist = 'lime' in fruits
print(does_exist)  # False
```

### Listin Sonuna Item Ekleme

To add item to the end of an existing list we use the method *append()*.

```py
# syntax
lst = list()
lst.append(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.append('apple')
print(fruits)           # ['banana', 'orange', 'mango', 'lemon', 'apple']
fruits.append('lime')   # ['banana', 'orange', 'mango', 'lemon', 'apple', 'lime']
print(fruits)
```

### Listin Arasına Item Ekleme

We can use *insert()* method to insert a single item at a specified index in a list. Note that other items are shifted to the right. The *insert()* methods takes two arguments:index and an item to insert.

```py
# syntax
lst = ['item1', 'item2']
lst.insert(index, item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.insert(2, 'apple') # insert apple between orange and mango
print(fruits)           # ['banana', 'orange', 'apple', 'mango', 'lemon']
fruits.insert(3, 'lime')   # ['banana', 'orange', 'apple', 'lime', 'mango', 'lemon']
print(fruits)
```

### Listten İtem Silme

The remove method removes a specified item from a list

```py
# syntax
lst = ['item1', 'item2']
lst.remove(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'banana']
fruits.remove('banana')
print(fruits)  # ['orange', 'mango', 'lemon', 'banana'] - this method removes the first occurrence of the item in the list
fruits.remove('lemon')
print(fruits)  # ['orange', 'mango', 'banana']
```

### Pop Kullanarak İtem Silme

The *pop()* method removes the specified index, (or the last item if index is not specified):

```py
# syntax
lst = ['item1', 'item2']
lst.pop()       # last item
lst.pop(index)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.pop()
print(fruits)       # ['banana', 'orange', 'mango']

fruits.pop(0)
print(fruits)       # ['orange', 'mango']
```

### Del Kullanarak İtem Silme

The *del* keyword removes the specified index and it can also be used to delete items within index range. It can also delete the list completely

```py
# syntax
lst = ['item1', 'item2']
del lst[index] # only a single item
del lst        # to delete the list completely
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'kiwi', 'lime']
del fruits[0]
print(fruits)       # ['orange', 'mango', 'lemon', 'kiwi', 'lime']
del fruits[1]
print(fruits)       # ['orange', 'lemon', 'kiwi', 'lime']
del fruits[1:3]     # this deletes items between given indexes, so it does not delete the item with index 3!
print(fruits)       # ['orange', 'lime']
del fruits
print(fruits)       # This should give: NameError: name 'fruits' is not defined
```

### List İtemlerini Temizleme

The *clear()* method empties the list:

```py
# syntax
lst = ['item1', 'item2']
lst.clear()
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.clear()
print(fruits)       # []
```

### Copying a List

It is possible to copy a list by reassigning it to a new variable in the following way: list2 = list1. Now, list2 is a reference of list1, any changes we make in list2 will also modify the original, list1. But there are lots of case in which we do not like to modify the original instead we like to have a different copy. One of way of avoiding the problem above is using _copy()_.

```py
# syntax
lst = ['item1', 'item2']
lst_copy = lst.copy()
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits_copy = fruits.copy()
print(fruits_copy)       # ['banana', 'orange', 'mango', 'lemon']
```

### Joining Lists

There are several ways to join, or concatenate, two or more lists in Python.

- Plus Operator (+)

```py
# syntax
list3 = list1 + list2
```

```py
positive_numbers = [1, 2, 3, 4, 5]
zero = [0]
negative_numbers = [-5,-4,-3,-2,-1]
integers = negative_numbers + zero + positive_numbers
print(integers) # [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
fruits = ['banana', 'orange', 'mango', 'lemon']
vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
fruits_and_vegetables = fruits + vegetables
print(fruits_and_vegetables ) # ['banana', 'orange', 'mango', 'lemon', 'Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

- Joining using extend() method
  The *extend()* method allows to append list in a list. See the example below.

```py
# syntax
list1 = ['item1', 'item2']
list2 = ['item3', 'item4', 'item5']
list1.extend(list2)
```

```py
num1 = [0, 1, 2, 3]
num2= [4, 5, 6]
num1.extend(num2)
print('Numbers:', num1) # Numbers: [0, 1, 2, 3, 4, 5, 6]
negative_numbers = [-5,-4,-3,-2,-1]
positive_numbers = [1, 2, 3,4,5]
zero = [0]

negative_numbers.extend(zero)
negative_numbers.extend(positive_numbers)
print('Integers:', negative_numbers) # Integers: [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
fruits = ['banana', 'orange', 'mango', 'lemon']
vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
fruits.extend(vegetables)
print('Fruits and vegetables:', fruits ) # Fruits and vegetables: ['banana', 'orange', 'mango', 'lemon', 'Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

### Counting Items in a List

The *count()* method returns the number of times an item appears in a list:

```py
# syntax
lst = ['item1', 'item2']
lst.count(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
print(fruits.count('orange'))   # 1
ages = [22, 19, 24, 25, 26, 24, 25, 24]
print(ages.count(24))           # 3
```

### Finding Index of an Item

The *index()* method returns the index of an item in the list:

```py
# syntax
lst = ['item1', 'item2']
lst.index(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
print(fruits.index('orange'))   # 1
ages = [22, 19, 24, 25, 26, 24, 25, 24]
print(ages.index(24))           # 2, the first occurrence
```

### Reversing a List

The *reverse()* method reverses the order of a list.

```py
# syntax
lst = ['item1', 'item2']
lst.reverse()

```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.reverse()
print(fruits) # ['lemon', 'mango', 'orange', 'banana']
ages = [22, 19, 24, 25, 26, 24, 25, 24]
ages.reverse()
print(ages) # [24, 25, 24, 26, 25, 24, 19, 22]
```

### Sorting List Items

To sort lists we can use _sort()_ method or _sorted()_ built-in functions. The _sort()_ method reorders the list items in ascending order and modifies the original list. If an argument of _sort()_ method reverse is equal to true, it will arrange the list in descending order.

- sort(): this method modifies the original list

  ```py
  # syntax
  lst = ['item1', 'item2']
  lst.sort()                # ascending
  lst.sort(reverse=True)    # descending
  ```

  **Example:**

  ```py
  fruits = ['banana', 'orange', 'mango', 'lemon']
  fruits.sort()
  print(fruits)             # sorted in alphabetical order, ['banana', 'lemon', 'mango', 'orange']
  fruits.sort(reverse=True)
  print(fruits) # ['orange', 'mango', 'lemon', 'banana']
  ages = [22, 19, 24, 25, 26, 24, 25, 24]
  ages.sort()
  print(ages) #  [19, 22, 24, 24, 24, 25, 25, 26]
 
  ages.sort(reverse=True)
  print(ages) #  [26, 25, 25, 24, 24, 24, 22, 19]
  ```

  sorted(): returns the ordered list without modifying the original list
  **Example:**

  ```py
  fruits = ['banana', 'orange', 'mango', 'lemon']
  print(sorted(fruits))   # ['banana', 'lemon', 'mango', 'orange']
  # Reverse order
  fruits = ['banana', 'orange', 'mango', 'lemon']
  fruits = sorted(fruits,reverse=True)
  print(fruits)     # ['orange', 'mango', 'lemon', 'banana']
  ```

🌕 You are diligent and you have already achieved quite a lot. You have just completed day 5 challenges and you are 5 steps a head in to your way to greatness. Now do some exercises for your brain and muscles.

## 💻 Alıştırmalar: 5. Gün

### Alıştırmalar: 1. Seviye

1. Boş bir list tanımla
2. 5’ten fazla iteme sahip bir list tanımla
3. Listin uzunluğunu bul
4. Listin ilk, orta ve son öğesini bul
5. mixed_data_types adında bir list tanımla ve içine (name, age, height, marital status, address) bilgilerini koy
6. it_companies adında bir list değişkeni tanımla ve başlangıç değerleri olarak Facebook, Google, Microsoft, Apple, IBM, Oracle ve Amazon ekle
7. Listeyi print() kullanarak yazdır
8. Listdeki şirketlerin sayısını yazdır
9. Listin ilk, orta ve son şirketini yazdır
10. Şirketlerden birini değiştirerek listi tekrar yazdır
11. it_companies listine yeni bir IT şirketi ekle
12. Şirketler listinin ortasına bir IT şirketi ekle
13. IBM hariç olmak üzere it_companies listindeki şirketlerden birinin adını büyük harfe çevir
14. it_companies listini '#' stringi ile birleştir 
15. Belirli bir şirketin it_companies listinde olup olmadığını kontrol et
16. Listi sort() metodu ile sırala
17. Listi reverse() metodu ile azalan düzende (ters) sırala
18. Listdeki ilk 3 şirketi böl (slice)
19. Listdeki son 3 şirketi böl (slice)
20. Listin ortasındaki IT şirketini böl (slice)
21. Listdeki ilk IT şirketini sil
22. Listin ortasındaki IT şirketini sil
23. Listdeki son IT şirketini sil
24. Listdeki tüm IT şirketlerini kaldır
25. it_companies listini tamamen sil
26. Aşağıdaki listleri birleştir

    ```py
    front_end = ['HTML', 'CSS', 'JS', 'React', 'Redux']
    back_end = ['Node','Express', 'MongoDB']
    ```

27. After joining the lists in question 26. Copy the joined list and assign it to a variable full_stack, then insert Python and SQL after Redux.

### Alıştırmalar: 2. Seviye

1. The following is a list of 10 students ages:

```sh
ages = [19, 22, 19, 24, 20, 25, 26, 24, 25, 24]
```

- Listi sırala ve en küçük ile en büyük yaşı bul
- En küçük ve en büyük yaşları tekrar liste ekle
- Yaşların medyanını bul (ortadaki yaş)
- Ortalama yaşı bul
- Yaşların aralığını bul (en büyük yaş – en küçük yaş)
- (en küçük yaş – ortalama yaş) ve (en büyük yaş – ortalama yaş) değerlerini karşılaştır, _abs()_ metodunu kullan

1. Find the middle country(ies) in the [countries list](https://github.com/Asabeneh/30-Days-Of-Python/tree/master/data/countries.py)
1. Divide the countries list into two equal lists if it is even if not one more country for the first half.
1. ['China', 'Russia', 'USA', 'Finland', 'Sweden', 'Norway', 'Denmark']. Unpack the first three countries and the rest as scandic countries.

🎉 TEBRİKLER ! 🎉

[<< 4. Gün](../04_Day_Strings/04_strings.md) | [6. Gün >>](../06_Day_Tuples/06_tuples.md)
