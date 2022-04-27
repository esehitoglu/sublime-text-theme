<h1 align="center">Tema renkleri</h1>

![](https://github.com/esehitoglu/1.-odev/blob/main/figures/typescript-javascript.png)

Javascript  | TypeScript
------------- | -------------
JS betik dilidir  | TS nesne yönelimli program dilidir
JS dinamik olarak verileri tanır  | TS statik veri tiplemesine sahiptir 
JS desteklemez opsiyonel olarak parametreli fonksiyonları | TS opsiyonel olarak parametreli fonksiyonları destekler
JS kodu derlenmediği için hata denetimi yapılamaz | TS kodunda derleme yapıldığı için hata denetimi yapılır
JS büyük ve karmaşık projelerin geliştirme zaman alır | TS ile JS olarak tasarlanmış büyük ve karmaşık projelerin geliştirme aşaması çok daha kısa sürelere indirilebilir
JS soyut sınıfları destekler | TS soyut sınıfları desteklemez.
TS'e göre okunması zordur | TS kolay okunabilir ve düzenlenebilir
JS öğrenmesi kolay | Sert öğrenme eğrisi.Önceden kodlama bilgisi gerektirir
JavaScript’te büyük bir geliştirici topluluğu var | Typescript yazıcının geniş bir geliştirici topluluğu yoktur.
Airbnb, Codecademy ve Instagram JavaScript kullanmasına rağmen | Asana, Clever, Screen award, vb. TypeScript kullanıyor
JavaScript, istemci tarafında çalışır |TypeScript, istemci tarafında olduğu kadar sunucu tarafında da çalışır
“Typescript geliştiricisi” için ortalama maaş Amerika Birleşik Devletleri’nde yılda yaklaşık 148.027 $ arasında değişmektedir | Javascript Developer için ortalama maaş, ABD’de yıllık 110.777 $ ‘dır.
dosya uzantısı .js | dosya uzantısı .ts

<h2 align="center">JavaScript ve TypeScript</h2>
JavaScript, dinamik web sayfaları oluşturmak için kullanılan bir dildir. HTML ve CSS ile entegre edilmesi kolay, hafif bir yorumlanmış dildir. Form doğrulama, animasyon ve bir web sayfasına multimedya yetenekleri eklemek için kullanışlıdır. TypeScript, ek özelliklere sahip JavaScript'tir. JavaScript ve TypeScript arasındaki fark, JavaScript'in istemci tarafı kodlama dili olması ve TypeScript'in Nesne Yönelimli bir derlenmiş dil olmasıdır.

<h2 align="center">TypeScrip Avantajları</h2>
<p align="center">
  <img src="https://github.com/A101-Node-js-TypeScript-Bootcamp/a101-bootcamp-odev1-esehitoglu/blob/main/figures/screenshot_20220112_220824.png" alt="animated" />
</p>
<p align="center">
  <img src="https://github.com/esehitoglu/1.-odev/blob/main/figures/09f3f48adf2719c5.jpeg" alt="animated" />
</p>


<h1 align="center">HTTP Server kullanarak Nodejs servisi nasıl ayağı kaldırılır.</h1>

ilk olarak node.js kurulumunu gerçekleştiriyoruz daha sonra konsol ekranına <pre>node -v </pre>
komutunu yazıyoruz versiyonu ekranda görüyorsak node.js kurulumunu gerçekleştirmiş oluyoruz. 

http server paketini kurmak için:
 <pre>npm i http-server </pre> komutunu kullanıyoruz.

Daha sonra projemizin içine index.js isminde bir dosya oluşturuyoruz ((farklı isimli dosya da olabilir) ve içine kodlarımızı yazıyoruz.

```javascript
var http = require('http'); //yeni bir server objesi oluşturuyoruz
http.createServer(function (req, res) {
  res.writeHead(200,{'content-type':'text/html;charset=utf-8'});
  res.write('<b> Merhaba Dünya! </b>'); //sunucuya yazılacak mesajı belirliyoruz
  res.end(); // cevabı sonlandırıyoruz
}).listen(3000); //sunucu nesnesini 3000 numaralı bağlantı noktasında dinler
```

veya 

```javascript
const http = require('http');
const server = http.createServer((req, res) => {
 res.writeHead(200, {'Content-Type': 'text/plain; charset=utf-8'}); 
 res.write('Merhaba Dünya!');
 res.end();
});
server.listen(3000, () => {
 console.log('Uygulama çalıştırıldı...');
});
```

daha sonra dosyamızı çalıştırmak için:
```node
node index.js
```
yazıyoruz ve tarayıcımızda görüntülemek için:

```
http://localhost:3000/
```
adresine gidiyoruz.

![](https://github.com/esehitoglu/1.-odev/blob/main/figures/screenshot_20220109_173431.png)

<h1 align="center">Express kullanarak Nodejs servisi nasıl ayağı kaldırılır.</h1>

nodejs express modülünü yüklemek için:
<pre>
npm install express
</pre>
kodunu konsola yazıyoruz daha sonra , projemizin içinde bulunan index.js dosyasının içine javascript kodlarımızı yazıyoruz.

```javascript
const express = require('express');//express’i projemize dahil ediyoruz.
const app = express(); //Express’in fonksiyonun bütün özellikleri kullanabilmek için şu kodu yazıyoruz.

//tarayıcıda görmek için şu kodları kullanalım.
app.get('/', (req, res) => {
 res.send('<h1> Merhaba Dünya! </h1>');
});
app.listen(3000, () => {
 console.log('Uygulama çalıştırıldı...');
});
```

diyoruz ve kaydedip (aynı dizinde olduğumuzu kontrol ederek) terminale 

<pre>
node index.js </pre>

yazıp projemizi başlatıyoruz.

yazıyoruz ve tarayıcımızda görüntülemek için:

```
http://localhost:3000/
```
adresine gidiyoruz.

![](https://github.com/esehitoglu/1.-odev/blob/main/figures/screenshot_20220109_173431.png)


