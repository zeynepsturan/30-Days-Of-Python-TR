<div align="center">
  <h1> 30 Günde Python: 8. Gün - Dictionaryler</h1>
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

[<< 7. Gün ](../07_Day_Sets/07_sets.md) | [9. Gün >>](../09_Day_Conditionals/09_conditionals.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 8. Gün](#-day-8)
  - [Dictionaryler](#dictionaries)
    - [Dictionary Oluşturma](#creating-a-dictionary)
    - [Dictionary Uzunluğu](#dictionary-length)
    - [Dictionary İtemlerine Erişme](#accessing-dictionary-items)
    - [Dictionaryye İtem Ekleme](#adding-items-to-a-dictionary)
    - [Dictionary İtemlerini Modifiye Etme](#modifying-items-in-a-dictionary)
    - [Dictionaryde Key Bulma](#checking-keys-in-a-dictionary)
    - [Dictionaryden Key-Value Çiftlerini Kaldırma](#removing-key-and-value-pairs-from-a-dictionary)
    - [Dictionaryyi İtem Listine Dönüştürme](#changing-dictionary-to-a-list-of-items)
    - [Dictionaryyi Temizleme](#clearing-a-dictionary)
    - [Dictionaryyi Silme](#deleting-a-dictionary)
    - [Dictionaryyi Kopyalama](#copy-a-dictionary)
    - [Dictionary Keylerini List Olarak Alma](#getting-dictionary-keys-as-a-list)
    - [Dictionary Valuelerini List Olarak Alma](#getting-dictionary-values-as-a-list)
  - [💻 Alıştırmalar: 8. Gün](#-exercises-day-8)

# 📘 8. Gün

## Dictionaryler

A dictionary is a collection of unordered, modifiable(mutable) paired (key: value) data type.

### Dictionary Oluşturma

To create a dictionary we use curly brackets, {} or the *dict()* built-in function.

```py
# sözdizimi
empty_dict = {}
# Dictionary with data values
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
```

**Örnek:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
```

The dictionary above shows that a value could be any data types:string, boolean, list, tuple, set or a dictionary.

### Dictionary Uzunluğu

It checks the number of 'key: value' pairs in the dictionary.

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(len(dct)) # 4
```

**Örnek:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_married':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(len(person)) # 7

```

### Dictionary İtemlerine Erişme

We can access Dictionary items by referring to its key name.

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct['key1']) # value1
print(dct['key4']) # value4
```

**Örnek:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(person['first_name']) # Asabeneh
print(person['country'])    # Finland
print(person['skills'])     # ['JavaScript', 'React', 'Node', 'MongoDB', 'Python']
print(person['skills'][0])  # JavaScript
print(person['address']['street']) # Space street
print(person['city'])       # Error
```

Accessing an item by key name raises an error if the key does not exist. To avoid this error first we have to check if a key exist or we can use the _get_ method. The get method returns None, which is a NoneType object data type, if the key does not exist.
```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(person.get('first_name')) # Asabeneh
print(person.get('country'))    # Finland
print(person.get('skills')) #['HTML','CSS','JavaScript', 'React', 'Node', 'MongoDB', 'Python']
print(person.get('city'))   # None
```

### Dictionaryye İtem Ekleme

Dictionaryye yeni key*value pairs çiftleri ekleyebiliriz 

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct['key5'] = 'value5'
```

**Örnek:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
        }
}
person['job_title'] = 'Instructor'
person['skills'].append('HTML')
print(person)
```

### Dictionary İtemlerini Modifiye Etme

Dictionarydeki itemleri değiştirebiliriz

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct['key1'] = 'value-one'
```

**Örnek:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
person['first_name'] = 'Eyob'
person['age'] = 252
```

### Dictionaryde Key Bulma

Bir keyin dictionaryde olup olmadığını kontrol etmek için _in_ operatörünü kullanırız

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print('key2' in dct) # True
print('key5' in dct) # False
```

### Dictionaryden Key-Value Çiftlerini Kaldırma

- _pop(key)_: belli bir key ismindeki itemi kaldırır
- _popitem()_: son itemi kaldırır
- _del_: belli bir key ismindeki itemi kaldırır

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct.pop('key1') # key1 itemini kaldırır
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct.popitem() # son itemi kaldırır
del dct['key2'] # key2 itemini kaldırır
```

**Örnek:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
person.pop('first_name')        # firstname itemini siler
person.popitem()                # address itemini siler
del person['is_married']        # is_married itemini siler
```

### Dictionaryyi İtem Listine Dönüştürme

items() metodu, sözlüğü tuplelardan oluşan bir liste dönüştürür.

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct.items()) # dict_items([('key1', 'value1'), ('key2', 'value2'), ('key3', 'value3'), ('key4', 'value4')])
```

### Dictionaryyi Temizleme

Bir sözlükteki itemleri istemiyorsak _clear()_ metodu ile temizleyebiliriz.

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct.clear()) # None
```

### Dictionaryyi Silme

Dictionaryyi kullanmıyorsak tamamen silebiliriz

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
del dct
```

### Dictionary Kopyalama

_copy()_ metodunu kullanarak bir dictionaryyi kopyalayabiliriz. copy yöntemini kullanarak orijinal sözlüğün değişmesini (mutation) önleyebiliriz.

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct_copy = dct.copy() # {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
```

### Dictionary Keylerini List Olarak Alma

_keys_ metodu dictionarydeki tüm valueleri list olarak döner

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
keys = dct.keys()
print(keys)     # dict_keys(['key1', 'key2', 'key3', 'key4'])
```

### Dictionary Valuelerini List Olarak Alma

_values_ metodu dictionarydeki tüm valueleri list olarak döner

```py
# sözdizimi
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
values = dct.values()
print(values)     # dict_values(['value1', 'value2', 'value3', 'value4'])
```

🌕 Gerçekten şaşırtıcısın. Artık dictionarylerin gücüyle tam anlamıyla süper güçlüsün. 8. günün challenge’larını tamamladın ve mükemmellik yolunda 8 adım ilerledin. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 8. Gün

1. dog adında boş bir dictionary (sözlük) oluştur
2. dog sözlüğüne name, color, breed, legs, age keylerini ekle
3. student adında bir sözlük oluştur ve şu keyleri ekle: first_name, last_name, gender, age, marital status, skills, country, city, address
4. student sözlüğünün uzunluğunu al
5. skills keyinin değerini al ve veri tipini kontrol et, list olmalı
6. skills valuesine bir veya iki beceri daha ekleyerek değiştir
7. Dictionary keylerini list olarak al
8. Dictionary valuelerini list olarak al
9. Sözlüğü items() metodu ile tuplelardan oluşan bir liste çevir
10. Sözlükteki bir öğeyi sil
11. Sözlüklerden birini sil

🎉 TEBRİKLER ! 🎉

[<< 7. Gün ](../07_Day_Sets/07_sets.md) | [9. Gün >>](../09_Day_Conditionals/09_conditionals.md)
