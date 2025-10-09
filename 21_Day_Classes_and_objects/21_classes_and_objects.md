<div align="center">
  <h1> 30 Günde Python: 21. Gün - Classlar ve Objeler</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Yazar:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small>İkinci Versiyon: Temmuz, 2021</small>
</sub>

</div>

[<< 20. Gün](../20_Day_Python_package_manager/20_python_package_manager.md) | [22. Gün >>](../22_Day_Web_scraping/22_web_scraping.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 21. Gün](#-day-21)
  - [Classlar ve Objeler](#classes-and-objects)
    - [Class Oluşturma](#creating-a-class)
    - [Obje Oluşturma](#creating-an-object)
    - [Class Constructor](#class-constructor)
    - [Obje Metodları](#object-methods)
    - [Varsayılan Obje Metodları](#object-default-methods)
    - [Varsayılan Class Değerlerini Değiştiren Metod](#method-to-modify-class-default-values)
    - [Kalıtım (Inheritance)](#inheritance)
    - [Parent Metodu Override Etme](#overriding-parent-method)
  - [💻 Alıştırmalar: 21. Gün](#-exercises-day-21)
    - [Alıştırmalar: 1. Seviye](#exercises-level-1)
    - [Alıştırmalar: 2. Seviye](#exercises-level-2)
    - [Alıştırmalar: 3. Seviye](#exercises-level-3)

# 📘 21. Gün

## Classlar ve Objeler

Python nesne yönelimli (object-oriented) bir programlama dilidir. Python’daki her şey bir nesnedir (object) ve her nesnenin kendi özellikleri (properties) ve metotları (methods) vardır. Bir sayı, string, list, dictionary, tuple, set vb. programda kullanıldığında, bunların her biri ilgili built-in classın örneğidir (instance). Objeler oluşturabilmek için class oluştururuz. Bir class, obje oluşturmak için bir şablon ya da blueprint gibidir. Class, bir objenin özelliklerini (attributes) ve davranışlarını (behaviors) tanımlar; obje ise bu classın somut bir örneğidir.

Aslında bu zamana kadar, farkında olmadan classlar ve objelerle çalıştık. Python programındaki her öğe bir classın objesidir.
Şimdi, Python'daki her şeyin gerçekten bir class olup olmadığını kontrol edelim:

```py
asabeneh@Asabeneh:~$ python
Python 3.9.6 (default, Jun 28 2021, 15:26:21)
[Clang 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> num = 10
>>> type(num)
<class 'int'>
>>> string = 'string'
>>> type(string)
<class 'str'>
>>> boolean = True
>>> type(boolean)
<class 'bool'>
>>> lst = []
>>> type(lst)
<class 'list'>
>>> tpl = ()
>>> type(tpl)
<class 'tuple'>
>>> set1 = set()
>>> type(set1)
<class 'set'>
>>> dct = {}
>>> type(dct)
<class 'dict'>
```

### Class Oluşturma

Bir sınıf oluşturmak için **class** anahtar kelimesini, ardından class adını ve iki nokta (:) kullanırız. Class adı **CamelCase** olmalıdır.

```sh
# sözdizimi
class ClassName:
  kod kod kod kod
```

**Örnek:**

```py
class Person:
  pass
print(Person)
```

```sh
<__main__.Person object at 0x10804e510>
```

### Obje Oluşturma

Classı çağırarak bir obje oluşturabiliriz.

```py
p = Person()
print(p)
```

### Class Constructor

Yukarıdaki örneklerde, Person classından bir obje oluşturduk.Ancak, yapıcı (constructor) olmadan bir sınıf gerçek uygulamalarda pek kullanışlı değildir. Python’da, Java veya JavaScript’te olduğu gibi, built-in bir constructor fonksiyon vardır: **__init__**() fonksiyonu. Bu fonksiyon, classın yeni bir örneği (instance) oluşturulduğunda otomatik olarak çağrılır. Ayrıca, _self_ parametresi — oluşturulan class örneğine (objeye) bir referanstır.

**Örnek:**

```py
class Person:
      def __init__ (self, name):
        # self, classa parametre eklemeye izin verir
          self.name =name

p = Person('Asabeneh')
print(p.name)
print(p)
```

```sh
# çıktı
Asabeneh
<__main__.Person object at 0x2abf46907e80>
```

Constructor fonksiyona daha fazla parametre ekleyelim.

```py
class Person:
      def __init__(self, firstname, lastname, age, country, city):
          self.firstname = firstname
          self.lastname = lastname
          self.age = age
          self.country = country
          self.city = city


p = Person('Asabeneh', 'Yetayeh', 250, 'Finland', 'Helsinki')
print(p.firstname)
print(p.lastname)
print(p.age)
print(p.country)
print(p.city)
```

```sh
# çıktı
Asabeneh
Yetayeh
250
Finland
Helsinki
```

### Obje Metodları

Objelerin metodları olabilir. Metod, bir objeye ait olan fonksiyonlara denir.

**Örnek:**

```py
class Person:
      def __init__(self, firstname, lastname, age, country, city):
          self.firstname = firstname
          self.lastname = lastname
          self.age = age
          self.country = country
          self.city = city
      def person_info(self):
        return f'{self.firstname} {self.lastname} is {self.age} years old. He lives in {self.city}, {self.country}'

p = Person('Asabeneh', 'Yetayeh', 250, 'Finland', 'Helsinki')
print(p.person_info())
```

```sh
# çıktı
Asabeneh Yetayeh is 250 years old. He lives in Helsinki, Finland
```

### Varsayılan Obje Metodları

Bazen, obje metodların için varsayılan değerler belirlemek isteyebilirsin. Eğer constructor içindeki parametrelere varsayılan değerler verirsek classımızı parametre olmadan çağırdığımızda veya örneklediğimizde hatalardan kaçınabiliriz. Nasıl göründüğüne bakalım:

**Örnek:**

```py
class Person:
      def __init__(self, firstname='Asabeneh', lastname='Yetayeh', age=250, country='Finland', city='Helsinki'):
          self.firstname = firstname
          self.lastname = lastname
          self.age = age
          self.country = country
          self.city = city

      def person_info(self):
        return f'{self.firstname} {self.lastname} is {self.age} years old. He lives in {self.city}, {self.country}.'

p1 = Person()
print(p1.person_info())
p2 = Person('John', 'Doe', 30, 'Nomanland', 'Noman city')
print(p2.person_info())
```

```sh
# çıktı
Asabeneh Yetayeh is 250 years old. He lives in Helsinki, Finland.
John Doe is 30 years old. He lives in Noman city, Nomanland.
```

### Varsayılan Class Değerlerini Değiştiren Metod

Aşağıdaki örnekte, Person classındaki tüm constructor parametrelerin varsayılan değerleri var. Buna ek olarak, skills adında bir parametre var ve buna bir metod ile erişebiliriz. skills listine yetenek eklemek için bir add_skill metodu oluşturalım.

```py
class Person:
      def __init__(self, firstname='Asabeneh', lastname='Yetayeh', age=250, country='Finland', city='Helsinki'):
          self.firstname = firstname
          self.lastname = lastname
          self.age = age
          self.country = country
          self.city = city
          self.skills = []

      def person_info(self):
        return f'{self.firstname} {self.lastname} is {self.age} years old. He lives in {self.city}, {self.country}.'
      def add_skill(self, skill):
          self.skills.append(skill)

p1 = Person()
print(p1.person_info())
p1.add_skill('HTML')
p1.add_skill('CSS')
p1.add_skill('JavaScript')
p2 = Person('John', 'Doe', 30, 'Nomanland', 'Noman city')
print(p2.person_info())
print(p1.skills)
print(p2.skills)
```

```sh
# çıktı
Asabeneh Yetayeh is 250 years old. He lives in Helsinki, Finland.
John Doe is 30 years old. He lives in Noman city, Nomanland.
['HTML', 'CSS', 'JavaScript']
[]
```

### Kalıtım (Inheritance)

Kalıtım (inheritance) kullanarak, üst classın (parent class) kodunu yeniden kullanabiliriz. Inheritance, bir classın, üst classın tüm metodlarını ve özelliklerini almasını sağlar. Üst class (parent class) ya da temel class (base class), tüm metodları ve özellikleri veren sınıftır. Alt class (child class) ise başka bir sınıftan veya üst sınıftan miras alan sınıftır. 

Şimdi, Person classını miras alarak bir Student classı oluşturalım.

```py
class Student(Person):
    pass


s1 = Student('Eyob', 'Yetayeh', 30, 'Finland', 'Helsinki')
s2 = Student('Lidiya', 'Teklemariam', 28, 'Finland', 'Espoo')
print(s1.person_info())
s1.add_skill('JavaScript')
s1.add_skill('React')
s1.add_skill('Python')
print(s1.skills)

print(s2.person_info())
s2.add_skill('Organizing')
s2.add_skill('Marketing')
s2.add_skill('Digital Marketing')
print(s2.skills)

```

```sh
çıktı
Eyob Yetayeh is 30 years old. He lives in Helsinki, Finland.
['JavaScript', 'React', 'Python']
Lidiya Teklemariam is 28 years old. He lives in Espoo, Finland.
['Organizing', 'Marketing', 'Digital Marketing']
```

Child classta **__init__**() constructorunu çağırmadık. Eğer çağırmazsak, yine de parent classın tüm özelliklerine erişebiliriz. Ancak çağırırsak, üst classın özelliklerine _super_ anahtar kelimesi ile erişebiliriz.

Ayrıca alt classa yeni bir metod ekleyebilir veya üst classta var olan bir metodu aynı isimle yeniden tanımlayarak (override ederek) davranışını değiştirebiliriz.

Dikkat edilmesi gereken bir nokta: Alt classa **__init__**() fonksiyonunu eklediğimizde, artık üst classın **__init__**() fonksiyonu otomatik olarak miras alınmaz. Bu durumda, üst sınıfın consturctorundaki özellikleri kullanmak istiyorsak, super().__init__() komutunu manuel olarak çağırmamız gerekir.

### Parent Metodu Override Etme

```py
class Student(Person):
    def __init__ (self, firstname='Asabeneh', lastname='Yetayeh',age=250, country='Finland', city='Helsinki', gender='male'):
        self.gender = gender
        super().__init__(firstname, lastname,age, country, city)
    def person_info(self):
        gender = 'He' if self.gender =='male' else 'She'
        return f'{self.firstname} {self.lastname} is {self.age} years old. {gender} lives in {self.city}, {self.country}.'

s1 = Student('Eyob', 'Yetayeh', 30, 'Finland', 'Helsinki','male')
s2 = Student('Lidiya', 'Teklemariam', 28, 'Finland', 'Espoo', 'female')
print(s1.person_info())
s1.add_skill('JavaScript')
s1.add_skill('React')
s1.add_skill('Python')
print(s1.skills)

print(s2.person_info())
s2.add_skill('Organizing')
s2.add_skill('Marketing')
s2.add_skill('Digital Marketing')
print(s2.skills)
```

```sh
Eyob Yetayeh is 30 years old. He lives in Helsinki, Finland.
['JavaScript', 'React', 'Python']
Lidiya Teklemariam is 28 years old. She lives in Espoo, Finland.
['Organizing', 'Marketing', 'Digital Marketing']
```

Built-in super() fonksiyonunu veya üst classın adını (Person) kullanarak, üst classın metodlarını ve özelliklerini (properties) otomatik olarak miras alabiliriz. Yukarıdaki örnekte, ebeveyn classın metodunu **override** (geçersiz kılma) işlemi yaptık.
Alt classtaki metod farklı bir özelliğe sahiptir: cinsiyetin erkek mi kadın mı olduğunu belirleyebilir ve buna uygun zamiri (He/She) atayabilir.
🌕 Programlama konusunda süper bir güçle donanmış durumdasın. Şimdi beynin ve kasların için biraz alıştırma yapalım.

## 💻 Alıştırmalar: 21. Gün

### Alıştırmalar: 1. Seviye

1. Python’da _statistics_ adında bir modül vardır ve bu modülü kullanarak tüm istatistiksel hesaplamaları yapabiliriz. Ancak fonksiyon oluşturmayı ve yeniden kullanmayı öğrenmek için, kendi programımızı geliştirelim:Bu program örneklem (sample) verisinin merkezi eğilim ölçülerini (mean, median, mode) ve dağılım ölçülerini (range, variance, standard deviation) hesaplasın. Bunlara ek olarak: min, max, count, percentile ve frekans dağılımını da bulsun. Bunu yapmak için bir Statistics sınıfı oluşturabilir ve tüm istatistiksel hesaplamaları yapan fonksiyonları sınıfın metodları olarak ekleyebiliriz.

```py
ages = [31, 26, 34, 37, 27, 26, 32, 32, 26, 27, 27, 24, 32, 33, 27, 25, 26, 38, 37, 31, 34, 24, 33, 29, 26]

print('Count:', data.count()) # 25
print('Sum: ', data.sum()) # 744
print('Min: ', data.min()) # 24
print('Max: ', data.max()) # 38
print('Range: ', data.range() # 14
print('Mean: ', data.mean()) # 30
print('Median: ', data.median()) # 29
print('Mode: ', data.mode()) # {'mode': 26, 'count': 5}
print('Standard Deviation: ', data.std()) # 4.2
print('Variance: ', data.var()) # 17.5
print('Frequency Distribution: ', data.freq_dist()) # [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
```

```sh
# çıktın böyle gözükmeli
print(data.describe())
Count: 25
Sum:  744
Min:  24
Max:  38
Range:  14
Mean:  30
Median:  29
Mode:  (26, 5)
Variance:  17.5
Standard Deviation:  4.2
Frequency Distribution: [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
```

### Alıştırmalar: 2. Seviye

1. PersonAccount adında bir class oluştur. firstname, lastname, incomes, expenses propertyleri olsun ve total_income, total_expense, account_info, add_income, add_expense, account_balance metodları olsun. Incomes (gelirler), gelirlerin ve açıklamalarının bulunduğu settir. Aynı şekilde, expenses (giderler) de giderlerin ve onların açıklamalarının bulunduğu bir settir.

### Alıştırmalar: 3. Seviye


🎉 TEBRİKLER ! 🎉

[<< 20. Gün](../20_Day_Python_package_manager/20_python_package_manager.md) | [22. Gün >>](../22_Day_Web_scraping/22_web_scraping.md)
