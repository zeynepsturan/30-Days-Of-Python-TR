<div align="center">
  <h1> 30 Günde Python: 23. Gün - Sanal Ortam (Virtual Environment) </h1>
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

[<< 22. Gün](../22_Day_Web_scraping/22_web_scraping.md) | [24. Gün >>](../24_Day_Statistics/24_statistics.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 23. Gün](#-day-23)
  - [Sanal Ortamı Hazırlama](#setting-up-virtual-environments)
  - [💻 Alıştırmalar: 23. Gün](#-exercises-day-23)

# 📘 23. Gün

## Sanal Ortamı Hazırlama

Projeye başlamadan önce, bir sanal ortam (virtual environment) oluşturmak daha iyi olacaktır. Sanal ortam, izole veya ayrı bir çalışma alanı yaratmamıza yardımcı olur. Bu sayede projeler arasındaki kütüphane (dependency) çatışmalarını önlemiş oluruz. Terminale pip freeze yazarsan, bilgisayarında yüklü tüm paketleri görebilirsin. Ancak virtualenv kullanırsak, sadece o projeye özel paketlere erişim sağlarız. Şimdi terminalini aç ve virtualenv paketini yükle:

```sh
asabeneh@Asabeneh:~$ pip install virtualenv
```

30GundePython klasörünün içinde flask_project klasörünü oluştur.

Virtualenv paketini yükledikten sonra, proje klasörüne git ve bir sanal ortam oluşturmak için şu komutu yaz:

Mac/Linux için:
```sh
asabeneh@Asabeneh:~/Desktop/30DaysOfPython/flask_project\$ virtualenv venv

```

Windows için:
```sh
C:\Users\User\Documents\30DaysOfPython\flask_project>python -m venv venv
```

Yeni projeye venv adını vermeyi tercih ediyorum, ancak istersen farklı bir isim de kullanabilirsin. Oluşturulan venv klasörünü kontrol etmek için ls (Mac/Linux) veya dir (Windows) komutunu kullanabilirsin.

```sh
asabeneh@Asabeneh:~/Desktop/30DaysOfPython/flask_project$ ls
venv/
```

Proje klasörümüzde aşağıdaki komutu yazarak sanal ortamı (virtual environment) aktif edelim.

Mac/Linux için:
```sh
asabeneh@Asabeneh:~/Desktop/30DaysOfPython/flask_project$ source venv/bin/activate
```
Windows’ta sanal ortamın aktivasyonu, PowerShell ve Git Bash üzerinde farklılık gösterebilir.

Windows Power Shell için:
```sh
C:\Users\User\Documents\30DaysOfPython\flask_project> venv\Scripts\activate
```

Windows Git bash için:
```sh
C:\Users\User\Documents\30DaysOfPython\flask_project> venv\Scripts\. activate
```

Aktivasyon komutunu yazdıktan sonra, proje klasörün venv ile başlayacaktır. Aşağıda bir örnek görebilirsin.

```sh
(venv) asabeneh@Asabeneh:~/Desktop/30DaysOfPython/flask_project$
```

Şimdi, bu projede mevcut olan paketleri kontrol etmek için pip freeze yazalım. Hiç paket görmeyeceksin.

Küçük bir Flask projesi yapacağımız için, bu projeye Flask paketini yükleyelim.

```sh
(venv) asabeneh@Asabeneh:~/Desktop/30DaysOfPython/flask_project$ pip install Flask
```

Projede yüklü paketlerin listesini görmek için pip freeze yazalım:

```sh
(venv) asabeneh@Asabeneh:~/Desktop/30DaysOfPython/flask_project$ pip freeze
Click==7.0
Flask==1.1.1
itsdangerous==1.1.0
Jinja2==2.10.3
MarkupSafe==1.1.1
Werkzeug==0.16.0
```

When you finish you should dactivate active project using _deactivate_.

```sh
(venv) asabeneh@Asabeneh:~/Desktop/30DaysOfPython$ deactivate
```

Flask ile çalışmak için gerekli modüller yüklendi. Artık proje klasörün bir Flask projesi için hazır. Sanal ortamı (venv) GitHub’a göndermemek için .gitignore dosyana eklemelisin.

## 💻 Alıştırmalar: 23. Gün

1. Yukarıda verilen örneğe göre virtual environment ile bir proje klasörü oluştur.

🎉 TEBRİKLER ! 🎉

[<< 22. Gün](../22_Day_Web_scraping/22_web_scraping.md) | [24. Gün >>](../24_Day_Statistics/24_statistics.md)
