# Animasyonlar

Artık DOM öğelerini nasıl seçip değiştireceğimizi bildiğimize göre, basit bir animasyon oluşturabiliriz.

JS kullanılarak canlandırılacak bir **kutu** öğesi içeren basit bir HTML sayfası oluşturalım.

* HTML kodu:

```html
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <div id="konteyner">
      <div id="kutu"> </div>
    </div>
  </body>

</html>
```

* CSS kodu:

```css
#konteyner {
  width: 200px;
  height: 200px;
  background: green;
  position: relative;
}

#kutu {
  width: 50px;
  height: 50px;
  background: red;
  position: absolute;
}
```

**Kutu** elemanımız bir **konteyner** elemanının içindedir. Öğeler için kullanılan konum niteliğine dikkat edin: 

Konteyner **görecelidir** ve kutu **mutlaktır**. Bu, konteynere göre animasyonu oluşturmamıza izin verecektir.

![Örnek2](https://media.discordapp.net/attachments/861208192121569280/998207824628822066/rnek_.excalidraw.png?width=500&height=500)

Konteynerin sağ tarafına hareket etmesini sağlamak için kırmızı kutuyu canlandıracağız.[^1]
  
  [^1]: Sağlanan kodu daha iyi anlamak için CSS'ye aşina olmanız gerekir.

<hr>

Bir animasyon oluşturmak için, bir elemanın özelliklerini küçük zaman aralıklarında değiştirmemiz gerekir. Bunu, bir zamanlayıcı oluşturmamıza ve belirli aralıklarla (milisaniye cinsinden) tekrar tekrar özellikleri değiştirmek için bir işlev çağırmamıza izin veren **setInterval()** yöntemini kullanarak başarabiliriz.

**Örneğin:**

```javascript
var o = setInterval(oynat, 500); 
```	

Bu kod, her 500 milisaniyede bir **oynat()** işlevini çağıran bir zamanlayıcı oluşturur.

Şimdi kutunun konumunu değiştiren **oynat()** fonksiyonunu tanımlamamız gerekiyor.[^2]

```javascript	
// Başlangıç ​​pozisyonu
var poz = 0; 
// Kutu elementimiz
var kutu = document.getElementById("kutu");

function oynat() {
  poz += 1;
  kutu.style.left = poz + "px"; //px = piksel
}
```	

  [^2]: oynat() işlevi, kutu öğesinin **sol** özelliğini her çağrıldığında bir artırır.

<hr>

Aşağıdaki kod, her 10 milisaniyede bir **oynat()** işlevini çağıran bir zamanlayıcı tanımlar:

```javascript
var o = setInterval(oynat, 10); 
```

Ancak bu, kutumuzun sonsuza kadar sağa hareket etmesini sağlar. 

Kutu kabın sonuna ulaştığında animasyonu durdurmak için `oynat()` işlevine basit bir kontrol ekliyoruz ve zamanlayıcıyı durdurmak için ``clearInterval()`` yöntemini kullanıyoruz.

```javascript
function oynat() {
  if(poz >= 150) {
    clearInterval(o);
  } else {
    poz += 1;
    kutu.style.left = poz + "px";
  }
}
```

Kutunun left özelliği 150 değerine ulaştığında, kutu genişliği 200 ve kutu genişliği 50 bazında kutu kutunun sonuna ulaşır.

**Son kod:**

* HTML kodu:

```html
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <div id="konteyner">
      <div id="kutu"> </div>
    </div>
  </body>

</html>
```

* CSS kodu:

```css
#konteyner {
  width: 200px;
  height: 200px;
  background: green;
  position: relative;
}

#kutu {
  width: 50px;
  height: 50px;
  background: red;
  position: absolute;
}
```

* JS kodu:

```javascript
window.onload = function() {
  var poz = 0; 

  //kutu elementimiz
  var kutu = document.getElementById('kutu');
  var o = setInterval(oynat, 10);
  
  function oynat() {
    if(poz >= 150) {
      clearInterval(o);
    } else {
      poz += 1;
      kutu.style.left = poz + 'px';
    }
  }
};
```

> Tebrikler, az önce ilk JavaScript animasyonunuzu oluşturdun :D


