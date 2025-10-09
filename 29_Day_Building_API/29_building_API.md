<div align="center">
  <h1> 30 Günde Python: 29. Gün - API Oluşturma </h1>
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

[<< 28. Gün](../28_Day_API/28_API.md) | [30. Gün >>](../30_Day_Conclusions/30_conclusions.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [29. Gün](#day-29)
- [API Oluşturma](#building-api)
  - [API Yapısı](#structure-of-an-api)
  - [Get Kullanarak Veri Elde Etme](#retrieving-data-using-get)
  - [Getting a document by id](#getting-a-document-by-id)
  - [Creating data using POST](#creating-data-using-post)
  - [Updating using PUT](#updating-using-put)
  - [Deleting a document using Delete](#deleting-a-document-using-delete)
- [💻 Alıştırmalar: 29. Gün](#-exercises-day-29)

## 29. Gün

## API Oluşturma


Bu bölümde, HTTP request yöntemlerini (GET, PUT, POST, DELETE) kullanarak veri işlemleri yapan RESTful API'yi ele alacağız.

RESTful API, HTTP isteklerini kullanarak veri alma (GET), ekleme (POST), güncelleme (PUT) ve silme (DELETE) işlemlerini gerçekleştiren bir uygulama programlama arayüzüdür (API). Önceki bölümlerde Python, Flask ve MongoDB hakkında bilgi edindik.
Bu bilgileri kullanarak, Python, Flask ve MongoDB ile bir RESTful API geliştireceğiz. Her uygulama, CRUD (Create, Read, Update, Delete) işlemlerine sahiptir ve bir API, veri oluşturmak, almak, güncellemek veya silmek için kullanılır.

Tarayıcı yalnızca GET isteklerini işleyebilir. Bu nedenle, tüm istek yöntemlerini (GET, POST, PUT, DELETE) yönetmemize yardımcı olacak bir araca ihtiyacımız vardır.

API Örneği

- Countries API: https://restcountries.eu/rest/v2/all
- Cats breed API: https://api.thecatapi.com/v1/breeds

[Postman](https://www.getpostman.com/) API geliştirme söz konusu olduğunda çok popüler bir araçtır. Bu bölümü yapmak istiyorsanız, [Postman’i indirin](https://www.getpostman.com/). Postman’in bir alternatifi: [Insomnia](https://insomnia.rest/download).

![Postman](../images/postman.png)

### API Yapısı

Bir API uç noktası (endpoint), bir kaynağı almak (retrieve), oluşturmak (create), güncellemek (update) veya silmek (delete) için kullanılan bir URL’dir. Yapısı şu şekildedir:

Örnek:
https://api.twitter.com/1.1/lists/members.json

Belirtilen listenin üyelerini döndürür. Özel liste üyeleri, yalnızca kimliği doğrulanmış kullanıcı söz konusu listenin sahibi ise gösterilir.
Metotlar:
HTTP metotları ve URL’ler

API, nesne işlemleri için aşağıdaki HTTP metotlarını kullanır:

```sh
GET        Nesne elde etme (retrieval) için kullanılır
POST       Nesne oluşturma (creation) ve nesne işlemleri için kullanılır
PUT        Nesne güncelleme (update) için kullanılır
DELETE     Nesne silme (deletion) için kullanılır
```

Şimdi, 30GündePython öğrencileri hakkında bilgi toplayan bir API oluşturalım.
Toplayacağımız bilgiler: name, country, city, date of birth, skills ve bio.

Bu API’yi uygulamak için kullanacağımız araçlar:

- Postman
- Python
- Flask
- MongoDB

### Get Kullanarak Veri Elde Etme 

In this step, let us use dummy data and return it as a json. To return it as json, will use json module and Response module.

```py
# let's import the flask

from flask import Flask,  Response
import json

app = Flask(__name__)

@app.route('/api/v1.0/students', methods = ['GET'])
def students ():
    student_list = [
        {
            'name':'Asabeneh',
            'country':'Finland',
            'city':'Helsinki',
            'skills':['HTML', 'CSS','JavaScript','Python']
        },
        {
            'name':'David',
            'country':'UK',
            'city':'London',
            'skills':['Python','MongoDB']
        },
        {
            'name':'John',
            'country':'Sweden',
            'city':'Stockholm',
            'skills':['Java','C#']
        }
    ]
    return Response(json.dumps(student_list), mimetype='application/json')


if __name__ == '__main__':
    # for deployment
    # to make it work for both production and development
    port = int(os.environ.get("PORT", 5000))
    app.run(debug=True, host='0.0.0.0', port=port)
```

When you request the http://localhost:5000/api/v1.0/students url on the browser you will get this:

![Get on browser](../images/get_on_browser.png)

When you request the http://localhost:5000/api/v1.0/students url on the browser you will get this:

![Get on postman](../images/get_on_postman.png)

In stead of displaying dummy data let us connect the flask application with MongoDB and get data from mongoDB database.

```py
# let's import the flask

from flask import Flask,  Response
import json
import pymongo


app = Flask(__name__)

#
MONGODB_URI='mongodb+srv://asabeneh:your_password@30daysofpython-twxkr.mongodb.net/test?retryWrites=true&w=majority'
client = pymongo.MongoClient(MONGODB_URI)
db = client['thirty_days_of_python'] # accessing the database

@app.route('/api/v1.0/students', methods = ['GET'])
def students ():

    return Response(json.dumps(student), mimetype='application/json')


if __name__ == '__main__':
    # for deployment
    # to make it work for both production and development
    port = int(os.environ.get("PORT", 5000))
    app.run(debug=True, host='0.0.0.0', port=port)
```

By connecting the flask, we can fetch students collection data from the thirty_days_of_python database.

```sh
[
    {
        "_id": {
            "$oid": "5df68a21f106fe2d315bbc8b"
        },
        "name": "Asabeneh",
        "country": "Finland",
        "city": "Helsinki",
        "age": 38
    },
    {
        "_id": {
            "$oid": "5df68a23f106fe2d315bbc8c"
        },
        "name": "David",
        "country": "UK",
        "city": "London",
        "age": 34
    },
    {
        "_id": {
            "$oid": "5df68a23f106fe2d315bbc8e"
        },
        "name": "Sami",
        "country": "Finland",
        "city": "Helsinki",
        "age": 25
    }
]
```

### Getting a document by id

We can access signle document using an id, let's access Asabeneh using his id.
http://localhost:5000/api/v1.0/students/5df68a21f106fe2d315bbc8b

```py
# let's import the flask

from flask import Flask,  Response
import json
from bson.objectid import ObjectId
import json
from bson.json_util import dumps
import pymongo


app = Flask(__name__)

#
MONGODB_URI='mongodb+srv://asabeneh:your_password@30daysofpython-twxkr.mongodb.net/test?retryWrites=true&w=majority'
client = pymongo.MongoClient(MONGODB_URI)
db = client['thirty_days_of_python'] # accessing the database

@app.route('/api/v1.0/students', methods = ['GET'])
def students ():

    return Response(json.dumps(student), mimetype='application/json')
@app.route('/api/v1.0/students/<id>', methods = ['GET'])
def single_student (id):
    student = db.students.find({'_id':ObjectId(id)})
    return Response(dumps(student), mimetype='application/json')

if __name__ == '__main__':
    # for deployment
    # to make it work for both production and development
    port = int(os.environ.get("PORT", 5000))
    app.run(debug=True, host='0.0.0.0', port=port)
```

```sh
[
    {
        "_id": {
            "$oid": "5df68a21f106fe2d315bbc8b"
        },
        "name": "Asabeneh",
        "country": "Finland",
        "city": "Helsinki",
        "age": 38
    }
]
```

### Creating data using POST

We use the POST request method to create data

```py
# let's import the flask

from flask import Flask,  Response
import json
from bson.objectid import ObjectId
import json
from bson.json_util import dumps
import pymongo
from datetime import datetime


app = Flask(__name__)

#
MONGODB_URI='mongodb+srv://asabeneh:your_password@30daysofpython-twxkr.mongodb.net/test?retryWrites=true&w=majority'
client = pymongo.MongoClient(MONGODB_URI)
db = client['thirty_days_of_python'] # accessing the database

@app.route('/api/v1.0/students', methods = ['GET'])
def students ():

    return Response(json.dumps(student), mimetype='application/json')
@app.route('/api/v1.0/students/<id>', methods = ['GET'])
def single_student (id):
    student = db.students.find({'_id':ObjectId(id)})
    return Response(dumps(student), mimetype='application/json')
@app.route('/api/v1.0/students', methods = ['POST'])
def create_student ():
    name = request.form['name']
    country = request.form['country']
    city = request.form['city']
    skills = request.form['skills'].split(', ')
    bio = request.form['bio']
    birthyear = request.form['birthyear']
    created_at = datetime.now()
    student = {
        'name': name,
        'country': country,
        'city': city,
        'birthyear': birthyear,
        'skills': skills,
        'bio': bio,
        'created_at': created_at

    }
    db.students.insert_one(student)
    return ;
def update_student (id):
if __name__ == '__main__':
    # for deployment
    # to make it work for both production and development
    port = int(os.environ.get("PORT", 5000))
    app.run(debug=True, host='0.0.0.0', port=port)
```

### Updating using PUT

```py
# let's import the flask

from flask import Flask,  Response
import json
from bson.objectid import ObjectId
import json
from bson.json_util import dumps
import pymongo
from datetime import datetime


app = Flask(__name__)

#
MONGODB_URI='mongodb+srv://asabeneh:your_password@30daysofpython-twxkr.mongodb.net/test?retryWrites=true&w=majority'
client = pymongo.MongoClient(MONGODB_URI)
db = client['thirty_days_of_python'] # accessing the database

@app.route('/api/v1.0/students', methods = ['GET'])
def students ():

    return Response(json.dumps(student), mimetype='application/json')
@app.route('/api/v1.0/students/<id>', methods = ['GET'])
def single_student (id):
    student = db.students.find({'_id':ObjectId(id)})
    return Response(dumps(student), mimetype='application/json')
@app.route('/api/v1.0/students', methods = ['POST'])
def create_student ():
    name = request.form['name']
    country = request.form['country']
    city = request.form['city']
    skills = request.form['skills'].split(', ')
    bio = request.form['bio']
    birthyear = request.form['birthyear']
    created_at = datetime.now()
    student = {
        'name': name,
        'country': country,
        'city': city,
        'birthyear': birthyear,
        'skills': skills,
        'bio': bio,
        'created_at': created_at

    }
    db.students.insert_one(student)
    return
@app.route('/api/v1.0/students/<id>', methods = ['PUT']) # this decorator create the home route
def update_student (id):
    query = {"_id":ObjectId(id)}
    name = request.form['name']
    country = request.form['country']
    city = request.form['city']
    skills = request.form['skills'].split(', ')
    bio = request.form['bio']
    birthyear = request.form['birthyear']
    created_at = datetime.now()
    student = {
        'name': name,
        'country': country,
        'city': city,
        'birthyear': birthyear,
        'skills': skills,
        'bio': bio,
        'created_at': created_at

    }
    db.students.update_one(query, student)
    # return Response(dumps({"result":"a new student has been created"}), mimetype='application/json')
    return
def update_student (id):
if __name__ == '__main__':
    # for deployment
    # to make it work for both production and development
    port = int(os.environ.get("PORT", 5000))
    app.run(debug=True, host='0.0.0.0', port=port)
```

### Deleting a document using Delete

```py
# let's import the flask

from flask import Flask,  Response
import json
from bson.objectid import ObjectId
import json
from bson.json_util import dumps
import pymongo
from datetime import datetime


app = Flask(__name__)

#
MONGODB_URI='mongodb+srv://asabeneh:your_password@30daysofpython-twxkr.mongodb.net/test?retryWrites=true&w=majority'
client = pymongo.MongoClient(MONGODB_URI)
db = client['thirty_days_of_python'] # accessing the database

@app.route('/api/v1.0/students', methods = ['GET'])
def students ():

    return Response(json.dumps(student), mimetype='application/json')
@app.route('/api/v1.0/students/<id>', methods = ['GET'])
def single_student (id):
    student = db.students.find({'_id':ObjectId(id)})
    return Response(dumps(student), mimetype='application/json')
@app.route('/api/v1.0/students', methods = ['POST'])
def create_student ():
    name = request.form['name']
    country = request.form['country']
    city = request.form['city']
    skills = request.form['skills'].split(', ')
    bio = request.form['bio']
    birthyear = request.form['birthyear']
    created_at = datetime.now()
    student = {
        'name': name,
        'country': country,
        'city': city,
        'birthyear': birthyear,
        'skills': skills,
        'bio': bio,
        'created_at': created_at

    }
    db.students.insert_one(student)
    return
@app.route('/api/v1.0/students/<id>', methods = ['PUT']) # this decorator create the home route
def update_student (id):
    query = {"_id":ObjectId(id)}
    name = request.form['name']
    country = request.form['country']
    city = request.form['city']
    skills = request.form['skills'].split(', ')
    bio = request.form['bio']
    birthyear = request.form['birthyear']
    created_at = datetime.now()
    student = {
        'name': name,
        'country': country,
        'city': city,
        'birthyear': birthyear,
        'skills': skills,
        'bio': bio,
        'created_at': created_at

    }
    db.students.update_one(query, student)
    # return Response(dumps({"result":"a new student has been created"}), mimetype='application/json')
    return
@app.route('/api/v1.0/students/<id>', methods = ['PUT']) # this decorator create the home route
def update_student (id):
    query = {"_id":ObjectId(id)}
    name = request.form['name']
    country = request.form['country']
    city = request.form['city']
    skills = request.form['skills'].split(', ')
    bio = request.form['bio']
    birthyear = request.form['birthyear']
    created_at = datetime.now()
    student = {
        'name': name,
        'country': country,
        'city': city,
        'birthyear': birthyear,
        'skills': skills,
        'bio': bio,
        'created_at': created_at

    }
    db.students.update_one(query, student)
    # return Response(dumps({"result":"a new student has been created"}), mimetype='application/json')
    return ;
@app.route('/api/v1.0/students/<id>', methods = ['DELETE'])
def delete_student (id):
    db.students.delete_one({"_id":ObjectId(id)})
    return
if __name__ == '__main__':
    # for deployment
    # to make it work for both production and development
    port = int(os.environ.get("PORT", 5000))
    app.run(debug=True, host='0.0.0.0', port=port)
```

## 💻 Alıştırmalar: 29. Gün

1. Implement the above example and develop [this](https://thirtydayofpython-api.herokuapp.com/)

🎉 TEBRİKLER ! 🎉

[<< 28. Gün](../28_Day_API/28_API.md) | [30. Gün >>](../30_Day_Conclusions/30_conclusions.md)
