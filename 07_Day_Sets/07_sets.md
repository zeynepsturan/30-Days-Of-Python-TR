<div align="center">
  <h1> 30 Günde Python: 7. Gün - Setler</h1>
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

[<< 6. Gün](../06_Day_Tuples/06_tuples.md) | [8. Gün >>](../08_Day_Dictionaries/08_dictionaries.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 7. Gün](#-day-7)
  - [Setler](#sets)
    - [Set Oluşturma](#creating-a-set)
    - [Set Uzunluğunu Bulma](#getting-sets-length)
    - [Set Itemlerine Erişme](#accessing-items-in-a-set)
    - [Item Bulma](#checking-an-item)
    - [Sete İtem Ekleme](#adding-items-to-a-set)
    - [Setten İtem Silme](#removing-items-from-a-set)
    - [Set İtemlerini Silme](#clearing-items-in-a-set)
    - [Seti Silme](#deleting-a-set)
    - [Listi Sete Dönüştürme](#converting-list-to-set)
    - [Setleri Birleştirme](#joining-sets)
    - [Kesişen İtemleri Bulma](#finding-intersection-items)
    - [Subset ve Super Set Bulma](#checking-subset-and-super-set)
    - [İki Set Arasındaki Farkı Bulma](#checking-the-difference-between-two-sets)
    - [İki Set Arasındaki Simetrik Farkı Bulma](#finding-symmetric-difference-between-two-sets)
    - [Setleri Birleştirme](#joining-sets-1)
  - [💻 Alıştırmalar: 7. Gün](#-exercises-day-7)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)
    - [Alıştırmalar: 3. Seviye](#exercises-level-3)

# 📘 7. Gün

## Setler

Set, bir itemler koleksiyonudur. Sizi ilkokul ya da lise matematik derslerinize geri götüreyim: Matematikteki küme tanımı Python’da da geçerlidir. Python’da set (küme), sırasız (unordered) ve indekslenemez (un-indexed) benzersiz elemanlar topluluğudur. Bir set, benzersiz (her itemden bir adet) itemleri saklar ve kümeler arasında _union (birleşim)_, _intersection (kesişim)_, _difference (fark)_, _symmetric difference (simetrik fark)_, _subset (alt küme)_, _super set (üst küme)_ ve _disjoint set (ayrık küme)_ gibi işlemleri yapmak mümkündür.

### Set Oluşturma

Built-in _set()_ fonksiyonuyla set oluştururuz.

- Boş tuple oluşturma

```py
# sözdizimi
st = set()
```

- Başlangıç değerli set oluşturma

```py
# sözdizimi
st = {'item1', 'item2', 'item3', 'item4'}
```

**Örnek:**

```py
# sözdizimi
fruits = {'banana', 'orange', 'mango', 'lemon'}
```

### Set Uzunluğunu Bulma

Bir setin uzunluğunu bulmak için **len()** metodunu kullanırız.

```py
# sözdizimi
st = {'item1', 'item2', 'item3', 'item4'}
len(st)
```

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
len(fruits)
```

### Set Itemlerine Erişme

Set itemlerine erişmek için döngüleri kullanırız. Bunu döngüler bölümünde göreceğiz

### Item Bulma

Bir itemin sette olup olmadığını kontrol etmek için _in_ operatörünü kullanırız

```py
# sözdizimi
st = {'item1', 'item2', 'item3', 'item4'}
print("Does set st contain item3? ", 'item3' in st) # Set item3 itemini içeriyor mu? True
```

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
print('mango' in fruits ) # True
```

### Sete İtem Ekleme

Set oluşturulduktan sonra itemler değiştirilemez ama yeni itemler eklenebilir

- _add()_ kullanarak tek item eklemek

```py
# sözdizimi
st = {'item1', 'item2', 'item3', 'item4'}
st.add('item5')
```

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.add('lime')
```

-  _update()_ metoduyla birden fazla item eklemek
  _update()_ sete birden fazla item eklemeye izin verir. Argüman olarak list alır

```py
# sözdizimi
st = {'item1', 'item2', 'item3', 'item4'}
st.update(['item5','item6','item7'])
```

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = ('tomato', 'potato', 'cabbage','onion', 'carrot')
fruits.update(vegetables)
```

### Setten İtem Silme

Bir setten bir itemi _remove()_ metodu ile kaldırabiliriz. Eğer item bulunmazsa _remove()_ metodu hata verir, bu yüzden itemin verilen sette olup olmadığını kontrol etmek iyidir. Ancak, _discard()_ metodu hiçbir hata vermez.

```py
# sözdizimi
st = {'item1', 'item2', 'item3', 'item4'}
st.remove('item2')
```

pop() metodu setten rastgele bir item siler ve silinen itemi döner

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.pop()  # setten rastgele bir item siler

```

Eğer silinen itemi bilmek istiyorsak

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
removed_item = fruits.pop() 
```

### Set İtemlerini Silme

Seti temizlemek için _clear_ metodunu kullanırız

```py
# sözdizimi
st = {'item1', 'item2', 'item3', 'item4'}
st.clear()
```

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.clear()
print(fruits) # set()
```

### Seti Silme

Setin kendisini silmek istersek _del_ operatörünü kullanırız

```py
# sözdizimi
st = {'item1', 'item2', 'item3', 'item4'}
del st
```

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
del fruits
```

### Listi Sete Dönüştürme

Bir listi sete ve bir seti liste dönüştürebiliriz. Listi sete dönüştürürken tekrarlanan itemler kaldırılır ve sadece benzersiz (unique) itemler kalır.

```py
# sözdizimi
lst = ['item1', 'item2', 'item3', 'item4', 'item1']
st = set(lst)  # {'item2', 'item4', 'item1', 'item3'} - the order is random, because sets in general are unordered
```

**Örnek:**

```py
fruits = ['banana', 'orange', 'mango', 'lemon','orange', 'banana']
fruits = set(fruits) # {'mango', 'lemon', 'banana', 'orange'}
```

### Setleri Birleştirme

İki seti _union()_ veya _update()_ metodlarıyla birleştirebiliriz

- Union
  Bu metod yeni bir set döner

```py
# sözdizimi
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item5', 'item6', 'item7', 'item8'}
st3 = st1.union(st2)
```

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = {'tomato', 'potato', 'cabbage','onion', 'carrot'}
print(fruits.union(vegetables)) # {'lemon', 'carrot', 'tomato', 'banana', 'mango', 'orange', 'cabbage', 'potato', 'onion'}
```

- Update
Bu yöntem, bir sete başka bir seti ekler

```py
# sözdizimi
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item5', 'item6', 'item7', 'item8'}
st1.update(st2) # st2 contents are added to st1
```

**Örnek:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = {'tomato', 'potato', 'cabbage','onion', 'carrot'}
fruits.update(vegetables)
print(fruits) # {'lemon', 'carrot', 'tomato', 'banana', 'mango', 'orange', 'cabbage', 'potato', 'onion'}
```

### Kesişen İtemleri Bulma

Kesişim (intersection) iki sette de ortak olan itemleri döner

```py
# sözdizimi
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item3', 'item2'}
st1.intersection(st2) # {'item3', 'item2'}
```

**Örnek:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.intersection(even_numbers) # {0, 2, 4, 6, 8, 10}

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.intersection(dragon)     # {'o', 'n'}
```

### Subset ve Super Set Bulma

Bir set, diğer setlerin alt kümesi (subset) veya üst kümesi (super set) olabilir:

- Subset: _issubset()_
- Super set: _issuperset_

```py
# sözdizimi
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.issubset(st1) # True
st1.issuperset(st2) # True
```

**Örnek:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.issubset(even_numbers) # False, çünkü üst küme
whole_numbers.issuperset(even_numbers) # True

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.issubset(dragon)     # False
```

### İki Set Arasındaki Farkı Bulma

İki setin farkını döner

```py
# sözdizimi
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.difference(st1) # set()
st1.difference(st2) # {'item1', 'item4'} => st1\st2
```

**Örnek:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.difference(even_numbers) # {1, 3, 5, 7, 9}

python = {'p', 'y', 't', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.difference(dragon)     # {'p', 'y', 't'}  - sonuç sırasız döner (setin karakteristik bir özelliği)
dragon.difference(python)     # {'d', 'r', 'a', 'g'}
```

### İki Set Arasındaki Simetrik Farkı Bulma

İki küme arasındaki simetrik farkı döner. Yani her iki kümede bulunan ortak elemanlar hariç, her iki kümeden de tüm elemanları içeren bir küme verir.
Matematiksel gösterimi: (A\B) ∪ (B\A)

```py
# sözdizimi
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
# it means (A\B)∪(B\A)
st2.symmetric_difference(st1) # {'item1', 'item4'}
```

**Örnek:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
some_numbers = {1, 2, 3, 4, 5}
whole_numbers.symmetric_difference(some_numbers) # {0, 6, 7, 8, 9, 10}

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.symmetric_difference(dragon)  # {'r', 't', 'p', 'y', 'g', 'a', 'd', 'h'}
```

### Joining Sets

İki setin ortak itemi yoksa onlara disjoint sets (ayrık kümeler) deriz. İki setin ayrık küme olup olmadığını _isdisjoint()_ metoduyla kontrol ederiz

```py
# sözdizimi
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.isdisjoint(st1) # False
```

**Örnek:**

```py
even_numbers = {0, 2, 4 ,6, 8}
odd_numbers = {1, 3, 5, 7, 9}
even_numbers.isdisjoint(odd_numbers) # True, çünkü ortak item yok

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.isdisjoint(dragon)  # False, ortak itemler var {'o', 'n'}
```

🌕 Yükselen bir yıldızsın. 7. günün challenge’larını tamamladın ve mükemmelliğe giden yolda 7 adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 7. Gün

```py
# setler
it_companies = {'Facebook', 'Google', 'Microsoft', 'Apple', 'IBM', 'Oracle', 'Amazon'}
A = {19, 22, 24, 20, 25, 26}
B = {19, 22, 20, 25, 26, 24, 28, 27}
age = [22, 19, 24, 25, 26, 24, 25, 24]
```

### Alıştırmalar: 1. Seviye

1. it_companies setinin uzunluğunu bul
2. it_companies setine 'Twitter' ekle
3. it_companies setine birden fazla IT şirketini aynı anda ekle
4. it_companies setinden bir şirketi sil
5. remove ve discard arasındaki fark nedir?

### Alıştırmalar: 2. Seviye

1. A ve B'yi birleştir
2. A ve B'nin kesişimini bul
3. A, B'nin alt kümesi mi?
4. A ve B kümeleri disjoint mi? (ortak elemanları yok mu?) kontrol et
5. A ve B kümelerini birleştir (A ∪ B ve B ∪ A)
6. A ve B kümeleri arasındaki simetrik farkı bul (sadece birinde olan elemanlar)
7. Kümeleri tamamen sil

### Alıştırmalar: 3. Seviye

1. Ages listini bir sete çevir, listin ve setin uzunluğunu karşılaştır, hangisi daha büyük?
2. Şu veri tipleri arasındaki farkı açıkla: string, list, tuple ve set
3. _I am a teacher and I love to inspire and teach people._ cümlesinde kaç benzersiz (unique) kelime kullanılmış? Benzersiz kelimeleri bulmak için split ve set yöntemlerini kullan.

🎉 TEBRİKLER ! 🎉

[<< 6. Gün](../06_Day_Tuples/06_tuples.md) | [8. Gün >>](../08_Day_Dictionaries/08_dictionaries.md)
