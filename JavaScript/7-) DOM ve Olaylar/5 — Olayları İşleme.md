# Olaylar

Bir kullanıcı bir HTML öğesini tıklattığında, fareyi hareket ettirdiğinde veya bir form gönderdiğinde olduğu gibi bir **olay** meydana geldiğinde yürütülen JavaScript kodu yazabilirsiniz.

Hedef öğede bir olay meydana geldiğinde, bir **işleyici** işlevi yürütülür.

Yaygın HTML olayları şunları içerir:

| Olay | Açıklama |
| ---- | ------- |
| `onclick` | Kullanıcı bir öğeye tıkladığında |
| `onload` | Bir nesne yüklendiğinde |
| `onunload` | bir nesne kaldırıldıktan sonra (\<body> için) |
| `onchange` | Bir form öğesinin içeriği, seçim veya kontrol edilen durum değiştiğinde (\<input>, \<keygen>, \<select> ve \<textarea> için) |
| `onmouseover` | İşaretçi bir öğeye veya onun alt öğelerinden birine geldiğinde |
| `onmouseout` | İşaretçi bir öğeye veya onun alt öğelerinden birine taşındığında |
| `onmousedown` | Kullanıcı bir öğe üzerinde fare düğmesine bastığında |
| `onmouseup` | Kullanıcı bir öğenin üzerinde fare düğmesini bıraktığında |
| `onblur` | Bir öğe odağı kaybettiğinde |
| `onfocus` | Bir öğe odaklandığında |

> Karşılık gelen olaylar, HTML öğelerine nitelikler olarak eklenebilir. 
Örneğin: \<p onclick="birFonksiyon()">Biraz metin\</p>

## Olayları İşleme

Kullanıcı belirli bir düğmeyi tıkladığında bir uyarı açılır penceresi görüntüleyelim:[^1]

* HTML kodu:
```html	
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <button onclick="sergile();">Butona bas</button>
  </body>

</html>
```

* JavaScript kodu:

```javascript
function sergile() {
  alert("Merhaba!");
}
```

Olay işleyicileri öğelere atanabilir.

**Örneğin:**

* HTML kodu:
```html	
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body> 
    <!-- demo idli bir buton oluşturduk-->
    <button id="demo">Butona bas</button>
  </body>

</html>
```

* JavaScript kodu:

```javascript
window.onload = function() {
  var x = document.getElementById('demo'); // öğe alma

  x.onclick = function () {
    document.body.innerHTML = Date(); // Şimdi ki zamanı gösterir.
  }
};
```

  [^1]: Olayları neredeyse tüm HTML öğelerine ekleyebilirsiniz.

<hr>

``onload`` ve ``onunload`` olayları, kullanıcı sayfaya girdiğinde veya sayfadan ayrıldığında tetiklenir. Bunlar, sayfa yüklendikten sonra eylemler gerçekleştirirken faydalı olabilir.

```html
<body onload="birseylerYap()">
```

Benzer şekilde, **window.onload** olayı, tüm sayfa yüklendikten sonra kodu çalıştırmak için kullanılabilir.

```javascript
window.onload = function() {
  //bazı kodlar
}
```

``onchange`` olayı çoğunlukla metin kutularında kullanılır. Olay işleyicisi, metin kutusunun içindeki metin değiştiğinde ve öğeden odak kaybolduğunda çağrılır.[^2]

**Örneğin:**

* HTML kodu:
```html
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <input type="text" id="ad" onchange="degistir()">
  </body>

</html>
```

* JavaScript kodu:

```javascript
function degistir() {
  var x = document.getElementById('ad');
  x.value = x.value.toUpperCase(); // metin kutusundaki metni büyük harfe çevirir.
}
```
> `value` özelliği, metin kutusunun içindeki metni alır.

  [^2]: Olayları anlamak önemlidir, çünkü bunlar dinamik web sayfalarının önemli bir parçasıdır.

## Olay Dinleyicileri


**addEventListener()** yöntemi, mevcut olay işleyicilerinin üzerine yazmadan bir öğeye bir olay işleyicisi ekler. Bir öğeye birçok olay işleyici ekleyebilirsiniz.

Aynı türden birçok olay işleyiciyi tek bir öğeye, yani iki "tıklama" olayına da ekleyebilirsiniz.

```javascript
element.addEventListener(olay, fonksiyon, yakalamayı kullanma);
```

İlk parametre olayın **türüdür** ("onclick" veya "mousedown" gibi).

İkinci parametre ise olay gerçekleştiğinde çağırmak istediğimiz **fonksiyondur**.

Üçüncü parametre, olay **köpürme** mi yoksa olay **yakalama** mı kullanılacağını belirten bir Boole değeridir. Bu parametre isteğe bağlıdır.[^3]

  [^3]: Bu olay için "on" önekini kullanmadığınızı unutmayın; "onclick" yerine "click" kullanın. :)

**Örneğin:**

```javascript
element.addEventListener("click", fonksiyonum);
element.addEventListener("mouseover", fonksiyonum);

function fonksiyonum() {
  alert("Selam Dünya!");
}
```

Bu, öğeye iki olay dinleyicisi ekler.

Dinleyicilerden birini kaldırabiliriz:

```javascript
element.removeEventListener("mouseover", fonksiyonum);
```

Hadi gelin, yürütüldükten sonra kendini kaldıran bir olay işleyicisi oluşturalım:

* HTML kodu:
```html
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <button id="demo">Başlat</button>
  </body>

</html>
```

* JavaScript kodu:
```javascript
window.onload = function() {
  var buton = document.getElementById("demo");
  buton.addEventListener("click", fonksiyonum);

  function fonksiyonum() {
    alert(Math.random());
    buton.removeEventListener("click", fonksiyonum);
  }
};
```

Düğmeye tıkladıktan sonra rastgele sayı içeren bir uyarı görüntülenir ve olay dinleyicisi kaldırılır.[^4]

  [^4]: Internet Explorer sürüm 8 ve altı, **addEventListener()** ve **removeEventListener()** yöntemlerini desteklemez. Ancak, Internet Explorer'da olay işleyicileri eklemek için document.**attachEvent()** yöntemini kullanabilirsiniz.

