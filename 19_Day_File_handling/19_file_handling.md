<div align="center">
  <h1> 30 Günde Python: 19. Gün - Dosya İşlemleri </h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>
<sub>Yazar:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small>Second Edition: Temmuz, 2021</small>
</sub>
</div>

[<< 18. Gün](../18_Day_Regular_expressions/18_regular_expressions.md) | [20. Gün >>](../20_Day_Python_package_manager/20_python_package_manager.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 19. Gün](#-day-19)
  - [Dosya İşlemleri](#file-handling)
    - [Okumak İçin Dosyaları Açmak](#opening-files-for-reading)
    - [Yazmak ve Güncellemek İçin Dosyaları Açmak](#opening-files-for-writing-and-updating)
    - [Dosyaları Silme](#deleting-files)
  - [Dosya Türleri](#file-types)
    - [txt Uzantılı Dosyalar](#file-with-txt-extension)
    - [json Uzantılı Dosyalar](#file-with-json-extension)
    - [JSON’u Dictionary'ye Dönüştürme](#changing-json-to-dictionary)
    - [Dictionary'yi JSON’a Dönüştürme](#changing-dictionary-to-json)
    - [JSON Dosyası Olarak Kaydetmek](#saving-as-json-file)
    - [csv Uzantılı Dosyalar](#file-with-csv-extension)
    - [xlsl Uzantılı Dosyalar](#file-with-xlsx-extension)
    - [xml Uzantılı Dosyalar](#file-with-xml-extension)
  - [💻 Alıştırmalar: 19. Gün](#-exercises-day-19)
    - [Alıştırmalar: Level 1](#exercises-level-1)
    - [Alıştırmalar: Level 2](#exercises-level-2)

# 📘 19. Gün

## Dosya İşlemleri

Şu ana kadar farklı Python veri tiplerini gördük. Verilerimizi genellikle farklı dosya formatlarında saklarız. Bu bölümde dosya işlemlerine ek olarak farklı dosya formatlarını (.txt, .json, .xml, .csv, .tsv, .excel) da göreceğiz. First, let us get familiar with handling files with common file format(.txt).

Dosya işlemleri; dosya oluşturmamızı, okumamızı, güncellememizi ve silmemizi sağlayan, programlamanın önemli bir parçasıdır. Python'da verileri işlemek için _open()_ built-in fonksiyonunu kullanırız.

```py
# Sözdizimi
open('dosya_adi', mod) # modlar (r, a, w, x, t,b) okumak, yazmak, güncellemek için
```

- "r" - Okuma - Varsayılan değer. Okumak için dosyayı açar, dosya bulunamazsa hata döner
- "a" - Sonuna Ekleme - Sonuna ekleme yapmak için dosyayı açar, dosya bulunamazsa dosyayı oluşturur
- "w" - Yazma - Yazmak için dosyayı açar (dosya içeriğinin üstüne yazar), dosya bulunamazsa dosyayı oluşturur
- "x" - Oluşturma - İstenen dosyayı oluşturur, dosya zaten varsa hata döner
- "t" - Text - Varsayılan değer. Metin modu
- "b" - Binary - Binary modu (e.g. görseller)

### Okumak İçin Dosyaları Açmak

_open_ fonksiyonunun varsayılan değeri okumadır(reading), bu yüzden'r' veya 'rt' şeklinde belirtmemize gerek yoktur. I have created and saved a file named reading_file_example.txt in the files directory. Let us see how it is done:

```py
f = open('./files/reading_file_example.txt')
print(f) # <_io.TextIOWrapper name='./files/reading_file_example.txt' mode='r' encoding='UTF-8'>
```

Yukarıdaki örnekte gördüğünüz gibi, I printed the opened file and it gave  some information about it. Açılmış dosyaların farklı okuma metodları vardır: _read()_, _readline_, _readlines_. Açılmış bir dosya _close()_ metoduyla kapatılmak zorundadır.

- _read()_: bütün metni string olarak okur. If we want to limit the number of characters we want to read, we can limit it by passing int value to the *read(number)* method.

```py
f = open('./files/reading_file_example.txt')
txt = f.read()
print(type(txt))
print(txt)
f.close()
```

```sh
# output
<class 'str'>
This is an example to show how to open a file and read.
This is the second line of the text.
```

Tüm metni yazdırmak yerine metin dosyasının ilk 10 karakterini yazdıralım.

```py
f = open('./files/reading_file_example.txt')
txt = f.read(10)
print(type(txt))
print(txt)
f.close()
```

```sh
# output
<class 'str'>
This is an
```

- _readline()_: sadece ilk satırı okur

```py
f = open('./files/reading_file_example.txt')
line = f.readline()
print(type(line))
print(line)
f.close()
```

```sh
# output
<class 'str'>
This is an example to show how to open a file and read.
```

- _readlines()_: tüm metni satır satır okur ve bir satır listi döner

```py
f = open('./files/reading_file_example.txt')
lines = f.readlines()
print(type(lines))
print(lines)
f.close()
```

```sh
# output
<class 'list'>
['This is an example to show how to open a file and read.\n', 'This is the second line of the text.']
```

Tüm satırları list olarak elde etmenin bir diğer yolu olan _splitlines()_ fonksiyonu:

```py
f = open('./files/reading_file_example.txt')
lines = f.read().splitlines()
print(type(lines))
print(lines)
f.close()
```

```sh
# output
<class 'list'>
['This is an example to show how to open a file and read.', 'This is the second line of the text.']
```

Bir dosyayı açtıktan sonra onu mutlaka kapamalıyız.. There is a high tendency of forgetting to close them. There is a new way of opening files using _with_ - closes the files by itself. Bİr önceki örneği _with_ metoduyla tekrar yazalım:

```py
with open('./files/reading_file_example.txt') as f:
    lines = f.read().splitlines()
    print(type(lines))
    print(lines)
```

```sh
# output
<class 'list'>
['This is an example to show how to open a file and read.', 'This is the second line of the text.']
```

### Yazmak ve Güncellemek İçin Dosyaları Açmak

Var olan bir dosyaya yazmak için modu  _open()_ fonksiyonuna parametre olarak eklemeliyiz:

- "a" - Sonuna Ekleme - Sonuna ekleme yapmak için dosyayı açar, dosya bulunamazsa dosyayı oluşturur
- "w" - Yazma - Yazmak için dosyayı açar (dosya içeriğinin üstüne yazar), dosya bulunamazsa dosyayı oluşturur

Let us append some text to the file we have been reading:

```py
with open('./files/reading_file_example.txt','a') as f:
    f.write('This text has to be appended at the end')
```

Aşağıdaki metod dosya bulunamazsa dosyayı oluşturur:

```py
with open('./files/writing_file_example.txt','w') as f:
    f.write('This text will be written in a newly created file')
```

### Dosyaları Silme

Önceki bölümde _os_ modülünü kullanarak bir klasör oluşturup silmeyi gördük. Bir dosyayı silmek istersek yine _os_ modülünü kullanıyoruz.

```py
import os
os.remove('./files/example.txt')

```

Eğer dosya zaten remove metodu hata verir bu yüzden böyle bir koşul kullanmak iyidir:

```py
import os
if os.path.exists('./files/example.txt'):
    os.remove('./files/example.txt')
else:
    print('The file does not exist')
```

## Dosya Türleri

### txt Uzantılı Dosyalar

File with _txt_ extension is a very common form of data and we have covered it in the previous section. Let us move to the JSON file

### json Uzantılı Dosyalar

JSON JavaScript Object Notation'un kısaltmasıdır. Actually, it is a stringified JavaScript object or Python dictionary.

**Örnek:**

```py
# dictionary
person_dct= {
    "name":"Asabeneh",
    "country":"Finland",
    "city":"Helsinki",
    "skills":["JavaScrip", "React","Python"]
}
# JSON: A string form a dictionary
person_json = "{'name': 'Asabeneh', 'country': 'Finland', 'city': 'Helsinki', 'skills': ['JavaScrip', 'React', 'Python']}"

# we use three quotes and make it multiple line to make it more readable
person_json = '''{
    "name":"Asabeneh",
    "country":"Finland",
    "city":"Helsinki",
    "skills":["JavaScrip", "React","Python"]
}'''
```

### JSON’u Dictionary'ye Dönüştürme

To change a JSON to a dictionary, first we import the json module and then we use _loads_ method.

```py
import json
# JSON
person_json = '''{
    "name": "Asabeneh",
    "country": "Finland",
    "city": "Helsinki",
    "skills": ["JavaScrip", "React", "Python"]
}'''
# let's change JSON to dictionary
person_dct = json.loads(person_json)
print(type(person_dct))
print(person_dct)
print(person_dct['name'])
```

```sh
# output
<class 'dict'>
{'name': 'Asabeneh', 'country': 'Finland', 'city': 'Helsinki', 'skills': ['JavaScrip', 'React', 'Python']}
Asabeneh
```

### Dictionary'yi JSON’a Dönüştürme

Dictionary'yi JSON’a Dönüştürmek için json modülünden _dumps_ metodunu kullanırız.

```py
import json
# python dictionary
person = {
    "name": "Asabeneh",
    "country": "Finland",
    "city": "Helsinki",
    "skills": ["JavaScrip", "React", "Python"]
}
# let's convert it to  json
person_json = json.dumps(person, indent=4) # indent could be 2, 4, 8. It beautifies the json
print(type(person_json))
print(person_json)
```

```sh
# output
# when you print it, it does not have the quote, but actually it is a string
# JSON does not have type, it is a string type.
<class 'str'>
{
    "name": "Asabeneh",
    "country": "Finland",
    "city": "Helsinki",
    "skills": [
        "JavaScrip",
        "React",
        "Python"
    ]
}
```

### Saving as JSON File

Verilerimizi json dosyası olarak da kaydedebiliriz. Aşağıdaki adımları kullanarak json dosyası olarak kaydedelim. Bir json dosyası yazmak için json.dump() metodunu kullanırız. it can take dictionary, output file, ensure_ascii and indent.

```py
import json
# python dictionary
person = {
    "name": "Asabeneh",
    "country": "Finland",
    "city": "Helsinki",
    "skills": ["JavaScrip", "React", "Python"]
}
with open('./files/json_example.json', 'w', encoding='utf-8') as f:
    json.dump(person, f, ensure_ascii=False, indent=4)
```

In the code above, we use encoding and indentation. Indentation makes the json file easy to read.

### csv Uzantılı Dosyalar

CSV comma separated values'ın kısaltmasıdır. CSV is a simple file format used to store tabular data, such as a spreadsheet or database. CSV, veri biliminde çok yaygın kullanılan bir veri formatıdır.

**Örnek:**

```csv
"name","country","city","skills"
"Asabeneh","Finland","Helsinki","JavaScript"
```

**Örnek:**

```py
import csv
with open('./files/csv_example.csv') as f:
    csv_reader = csv.reader(f, delimiter=',') # w use, reader method to read csv
    line_count = 0
    for row in csv_reader:
        if line_count == 0:
            print(f'Column names are :{", ".join(row)}')
            line_count += 1
        else:
            print(
                f'\t{row[0]} is a teachers. He lives in {row[1]}, {row[2]}.')
            line_count += 1
    print(f'Number of lines:  {line_count}')
```

```sh
# output:
Column names are :name, country, city, skills
        Asabeneh is a teacher. He lives in Finland, Helsinki.
Number of lines:  2
```

### xlsx Uzantılı Dosyalar

Excel dosyalarını okumak için _xlrd_ paketini yüklememiz gerekiyor. pip kullanarak paketi yükledikten sonra bunu kullanırız.

```py
import xlrd
excel_book = xlrd.open_workbook('sample.xls)
print(excel_book.nsheets)
print(excel_book.sheet_names)
```

### xml Uzantılı Dosyalar

XML, HTML'e benzeyen başka bir yapılandırılmış(structured) veri formatıdır. In XML the tags are not predefined. The first line is an XML declaration. The person tag is the root of the XML. The person has a gender attribute.
**Örnek:XML**

```xml
<?xml version="1.0"?>
<person gender="female">
  <name>Asabeneh</name>
  <country>Finland</country>
  <city>Helsinki</city>
  <skills>
    <skill>JavaScrip</skill>
    <skill>React</skill>
    <skill>Python</skill>
  </skills>
</person>
```

For more information on how to read an XML file check the [documentation](https://docs.python.org/2/library/xml.etree.elementtree.html)

```py
import xml.etree.ElementTree as ET
tree = ET.parse('./files/xml_example.xml')
root = tree.getroot()
print('Root tag:', root.tag)
print('Attribute:', root.attrib)
for child in root:
    print('field: ', child.tag)
```

```sh
# output
Root tag: person
Attribute: {'gender': 'male'}
field: name
field: country
field: city
field: skills
```

🌕 Büyük bir ilerleme kaydediyorsunuz. Temponuzu düşürmeyin, böyle devam edin. Now do some exercises for your brain and muscles.

## 💻 Alıştırmalar: 19. Gün

### Alıştırmalar: Level 1

1. Bir metindeki satır ve kelime sayısını sayan bir fonksiyon yazın. All the files are in the data the folder:
   a) Read obama_speech.txt file and count number of lines and words
   b) Read michelle_obama_speech.txt file and count number of lines and words
   c) Read donald_speech.txt file and count number of lines and words
   d) Read melina_trump_speech.txt file and count number of lines and words
2. Data klasöründeki countries_data.json dosyasını okuyun, en çok konuşulan 10 dili bulan bir fonksiyon yazın

   ```py
   # Çıktınız böyle gözükmeli
   print(most_spoken_languages(filename='./data/countries_data.json', 10))
   [(91, 'English'),
   (45, 'French'),
   (25, 'Arabic'),
   (24, 'Spanish'),
   (9, 'Russian'),
   (9, 'Portuguese'),
   (8, 'Dutch'),
   (7, 'German'),
   (5, 'Chinese'),
   (4, 'Swahili'),
   (4, 'Serbian')]

   # Çıktınız böyle gözükmeli
   print(most_spoken_languages(filename='./data/countries_data.json', 3))
   [(91, 'English'),
   (45, 'French'),
   (25, 'Arabic')]
   ```

3. Data klasöründeki countries_data.json dosyasını okuyun, en kalabalık 10 ülkeyi bulan bir fonksiyon yazın

   ```py
   # Çıktınız böyle gözükmeli
   print(most_populated_countries(filename='./data/countries_data.json', 10))

   [
   {'country': 'China', 'population': 1377422166},
   {'country': 'India', 'population': 1295210000},
   {'country': 'United States of America', 'population': 323947000},
   {'country': 'Indonesia', 'population': 258705000},
   {'country': 'Brazil', 'population': 206135893},
   {'country': 'Pakistan', 'population': 194125062},
   {'country': 'Nigeria', 'population': 186988000},
   {'country': 'Bangladesh', 'population': 161006790},
   {'country': 'Russian Federation', 'population': 146599183},
   {'country': 'Japan', 'population': 126960000}
   ]

   # Çıktınız böyle gözükmeli

   print(most_populated_countries(filename='./data/countries_data.json', 3))
   [
   {'country': 'China', 'population': 1377422166},
   {'country': 'India', 'population': 1295210000},
   {'country': 'United States of America', 'population': 323947000}
   ]
   ```

### Alıştırmalar: Level 2

4. Extract all incoming email addresses as a list from the email_exchange_big.txt file.
5. Find the most common words in the English language. Call the name of your function find_most_common_words, it will take two parameters - a string or a file and a positive integer, indicating the number of words. Your function will return an array of tuples in descending order. Check the output

```py
    # Your output should look like this
    print(find_most_common_words('sample.txt', 10))
    [(10, 'the'),
    (8, 'be'),
    (6, 'to'),
    (6, 'of'),
    (5, 'and'),
    (4, 'a'),
    (4, 'in'),
    (3, 'that'),
    (2, 'have'),
    (2, 'I')]

    # Your output should look like this
    print(find_most_common_words('sample.txt', 5))

    [(10, 'the'),
    (8, 'be'),
    (6, 'to'),
    (6, 'of'),
    (5, 'and')]
```

6. find_most_frequent_words fonksiyonunu aşağıdakileri bulmak için kullanın:
   a) The ten most frequent words used in [Obama's speech](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/obama_speech.txt)
   b) The ten most frequent words used in [Michelle's speech](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/michelle_obama_speech.txt)
   c) The ten most frequent words used in [Trump's speech](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/donald_speech.txt)
   d) The ten most frequent words used in [Melina's speech](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/melina_trump_speech.txt)
7. Write a python application that checks similarity between two texts. It takes a file or a string as a parameter and it will evaluate the similarity of the two texts. For instance check the similarity between the transcripts of [Michelle's](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/michelle_obama_speech.txt) and [Melina's](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/melina_trump_speech.txt) speech. You may need a couple of functions, function to clean the text(clean_text), function to remove support words(remove_support_words) and finally to check the similarity(check_text_similarity). List of [stop words](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/stop_words.py) are in the data directory
8. romeo_and_juliet.txt dosyasındaki en çok tekrarlanan 10 kelimeyi bulun
9. [hacker news csv](https://github.com/Asabeneh/30-Days-Of-Python/blob/master/data/hacker_news.csv) dosyasını okuyun ve aşağıdakileri bulun:
   a) Count the number of lines containing python or Python
   b) Count the number lines containing JavaScript, javascript or Javascript
   c) Count the number lines containing Java and not JavaScript

🎉 TEBRİKLER ! 🎉

[<< 18. Gün](../18_Day_Regular_expressions/18_regular_expressions.md) | [20. Gün >>](../20_Day_Python_package_manager/20_python_package_manager.md)
