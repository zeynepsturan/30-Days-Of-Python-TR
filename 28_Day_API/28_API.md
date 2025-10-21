<div align="center">
  <h1> 30 Günde Python: 28. Gün - API </h1>
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
</div>

[<< 27. Gün](../27_Day_Python_with_mongodb/27_python_with_mongodb.md) | [29. Gün >>](../29_Day_Building_API/29_building_API.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 28. Gün](#-day-28)
- [Application Programming Interface(API)](#application-programming-interfaceapi)
  - [API](#api)
  - [API Oluşturma](#building-api)
  - [HTTP(Hypertext Transfer Protocol)](#httphypertext-transfer-protocol)
  - [HTTP Yapısı](#structure-of-http)
  - [Request Başlangıç Satırı (Status Line)](#initial-request-linestatus-line)
    - [Response Başlangıç Satırı (Status Line)](#initial-response-linestatus-line)
    - [Başlık Alanları (Header Fields)](#header-fields)
    - [The message body](#the-message-body)
    - [Request Metodları](#request-methods)
  - [💻 Alıştırmalar: 28. Gün](#-exercises-day-28)

# 📘 28. Gün

# Application Programming Interface(API)

## API

API, Uygulama Programlama Arayüzü (Application Programming Interface) anlamına gelir. Bu bölümde ele alacağımız API türü Web API'ler olacaktır.
Web API'ler, bir kurum ile onun varlıklarını kullanan uygulamalar arasında gerçekleşen etkileşimlerin tanımlandığı arayüzlerdir. Ayrıca, fonksiyonel sağlayıcıyı belirten ve API kullanıcılarına hizmet yolunu (URL) sunan bir Hizmet Seviyesi Anlaşması (SLA) niteliğindedir.

Web geliştirme bağlamında, API; Hypertext Transfer Protocol (HTTP) request mesajları gibi bir dizi spesifikasyon ve genellikle XML ya da JavaScript Object Notation (JSON) formatında olan response mesajlarının yapısının tanımı olarak ifade edilir.

Web API’ler, Simple Object Access Protocol (SOAP) tabanlı web servisleri ve servis odaklı mimari (SOA) yaklaşımından uzaklaşıp, daha çok doğrudan Temsili Durum Transferi (REST) tarzı web kaynaklarına doğru yönelmektedir.

Sosyal medya servisleri ve web API’leri, web topluluklarının içerik ve verileri farklı topluluklar ve platformlar arasında paylaşmasına olanak sağlamıştır.

API kullanarak, bir yerde oluşturulan içerik dinamik bir şekilde web üzerindeki birden fazla konuma gönderilebilir ve güncellenebilir.

Örneğin, Twitter’ın REST API’si geliştiricilerin temel Twitter verilerine erişmesine olanak tanır ve Search API, geliştiricilere Twitter arama ve trend verileriyle etkileşim kurma yöntemleri sunar.

Many applications provide API end points. Some  examples of API such as the countries [API](https://restcountries.eu/rest/v2/all), [cat's breed API](https://api.thecatapi.com/v1/breeds).

In this section, we will cover a RESTful API that uses HTTP request methods to GET, PUT, POST and DELETE data.

## API Oluşturma

RESTful API, verileri GET, PUT, POST ve DELETE istekleriyle işlemek için HTTP requestlerini kullanan bir uygulama programlama arayüzüdür (API). Önceki bölümlerde Python, Flask ve MongoDB hakkında bilgi edindik. Bu bilgileri kullanarak, Python Flask ve MongoDB veri tabanı ile bir RESTful API geliştireceğiz. CRUD (Create, Read, Update, Delete) işlemlerini içeren herhangi bir uygulama, veri tabanına veri eklemek, verileri almak, güncellemek veya silmek için bir API’ye sahiptir.

Bir API oluşturmak için, HTTP protokolünü ve HTTP request-response döngüsünü iyi anlamak önemlidir.

## HTTP(Hypertext Transfer Protocol)

HTTP, bir istemci (client) ile bir sunucu (server) arasındaki iletişimi sağlayan yerleşik bir iletişim protokolüdür. Bu durumda istemci bir tarayıcıdır, sunucu ise verilere eriştiğimiz yerdir. HTTP, dünya çapında (World Wide Web) üzerindeki kaynakları (örneğin HTML dosyaları, resim dosyaları, sorgu sonuçları, scriptler veya diğer dosya türleri) iletmek için kullanılan bir ağ protokolüdür.

Bir tarayıcı, bir HTTP istemcisidir, çünkü HTTP sunucusuna (web sunucusuna) request gönderir ve sunucu da bu isteklere karşılık olarak response gönderir.

## HTTP Yapısı

HTTP, istemci–sunucu (client–server) modelini kullanır.
Bir HTTP istemcisi, bir bağlantı açar ve HTTP sunucusuna bir request mesajı gönderir. HTTP sunucusu ise istenen kaynakları içeren bir responsemesajı döndürür.

![HTTP request response cycle](../images/http_request_response_cycle.png)

Request ve response mesajlarının formatı benzerdir. Her iki tür mesaj da şunları içerir:

- başlangıç satırı (initial line),
- sıfır veya daha fazla başlık satırı (header lines),
- boş bir satır (yani sadece bir CRLF) ve
- isteğe bağlı mesaj gövdesi (message body) (örneğin bir dosya, sorgu verisi veya sorgu çıktısı).

Bir istek ve yanıt mesajı örneği görmek için şu siteyi ziyaret edelim: https://thirtydaysofpython-v1-final.herokuapp.com/. Bu site Heroku free dyno üzerinde dağıtılmıştır ve bazı aylarda yoğun istek nedeniyle çalışmayabilir. Sunucunun her zaman çalışması için desteğe ihtiyaç vardır.

![Request and Response header](../images/request_response_header.png)

##  Request Başlangıç Satırı (Status Line)

Request başlangıç satırı, response başlangıç satırından farklıdır.
request satırı, boşluklarla ayrılmış 3 kısımdan oluşur:

- metod adı(GET, POST, HEAD),
- istenen kaynağın yolu (path),
- kullanılan HTTP sürümü. Örnek: GET / HTTP/1.1

GET, en yaygın HTTP metodudur ve kaynağı almak veya okumak için kullanılır. POST, kaynak oluşturmak için sık kullanılan bir requestir.

### Response Başlangıç Satırı (Status Line)

Response başlangıç satırı, status line olarak adlandırılır ve boşluklarla ayrılmış üç bölüm içerir:

- HTTP sürümü
- Response status code (durum kodu) (requestin sonucunu gösterir),
- Durum kodunu açıklayan bir mesaj (reason).
  
  HTTP/1.0 200 OK
  veya
  HTTP/1.0 404 Not Found
  Notlar:

En yaygın durum kodları:
200 OK: İstek başarılı, ve sonuçta oluşan kaynak (dosya veya script çıktısı) mesaj bodysinde döndürülür.
500 Server Error: Sunucu hatası.
Tüm HTTP durum kodlarının listesine [buradan](https://httpstatuses.com/) veya [buradan](https://httpstatusdogs.com/) ulaşabilirsin.

### Başlık Alanları (Header Fields)

Yukarıdaki ekran görüntüsünde gördüğünüz gibi, başlık satırları (header lines), request veya responsea dair bilgileri veya mesaj gövdesinde gönderilen nesne hakkında bilgileri sağlar.

```sh
GET / HTTP/1.1
Host: thirtydaysofpython-v1-final.herokuapp.com
Connection: keep-alive
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.79 Safari/537.36
Sec-Fetch-User: ?1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Referer: https://thirtydaysofpython-v1-final.herokuapp.com/post
Accept-Encoding: gzip, deflate, br
Accept-Language: en-GB,en;q=0.9,fi-FI;q=0.8,fi;q=0.7,en-CA;q=0.6,en-US;q=0.5,fr;q=0.4
```

### The message body

An HTTP message may have a body of data sent after the header lines. In a response, this is where the requested resource is returned to the client (the most common use of the message body), or perhaps explanatory text if there's an error. In a request, this is where user-entered data or uploaded files are sent to the server.

If an HTTP message includes a body, there are usually header lines in the message that describe the body. In particular,

The Content-Type: header gives the MIME-type of the data in the body(text/html, application/json, text/plain, text/css, image/gif).
The Content-Length: header gives the number of bytes in the body.

### Request Metodları

GET, POST, PUT ve DELETE, API ya da CRUD işlemleri uygulaması yaparken kullanacağımız HTTP istek yöntemleridir.

1. GET:GET metodu, verilen URI kullanılarak sunucudan bilgi almak ve veri çekmek için kullanılır. GET istekleri sadece veri almak için kullanılmalı ve veriler üzerinde başka bir etkisi olmamalıdır.

2. POST: POST isteği, veri oluşturmak ve veriyi sunucuya göndermek için kullanılır. Örneğin, yeni bir gönderi oluşturmak, dosya yüklemek gibi işlemler HTML formları aracılığıyla yapılır.

3. PUT: PUT, hedef kaynağın mevcut tüm temsillerini yüklenen içerik ile değiştirir. Veri üzerinde değişiklik yapmak veya güncellemek için kullanılır.

4. DELETE: Veri siler.

## 💻 Alıştırmalar: 28. Gün

1. API ve HTTP hakkında okuma yap

🎉 TEBRİKLER ! 🎉

[<< 27. Gün](../27_Day_Python_with_mongodb/27_python_with_mongodb.md) | [29. Gün >>](../29_Day_Building_API/29_building_API.md)
