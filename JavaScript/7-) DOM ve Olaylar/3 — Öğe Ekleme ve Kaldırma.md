# Öğe Oluşturma

Yeni düğümler oluşturmak için aşağıdaki yöntemleri kullanın:

* ``element.cloneNode()`` bir öğeyi klonlar ve elde edilen düğümü döndürür.

* ``document.createElement(element)`` yeni bir öğe düğümü oluşturur.

* ``document.createTextNode(yazı)`` yeni bir metin düğümü oluşturur.

**Örneğin:**

```javascript
var düğüm = document.createTextNode("Yeni bir metin");
```	

Bu, yeni bir metin düğümü oluşturacaktır, ancak siz onu aşağıdaki yöntemlerden biriyle mevcut bir öğeye ekleyene kadar belgede görünmeyecektir:

* element.**appendChild(newNode)**, bir öğeye son alt düğüm olarak yeni bir alt düğüm ekler.

* element.**insertBefore(düğüm1, düğüm2)** düğüm1'i düğüm2'den önce alt öğe olarak ekler.

**Örnek:**

```html
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <div id="demo">Biraz içerik</div>

    <script>
      window.onload = function() {
        // Yeni bir paragraf oluşturuyoruz
        var p = document.createElement("p");
        var düğüm = document.createTextNode("Yeni bir yazı");

        // Yazıyı paragrafa ekliyoruz
        p.appendChild(node);

        var div = document.getElementById("demo");
        
        // Paragrafı div'e ekliyoruz
        div.appendChild(p);
      };
    </script>
  </body>
</html>
```

> Bu, yeni bir paragraf oluşturur ve onu sayfadaki mevcut div öğesine ekler.

# Öğeleri Kaldırma

Bir HTML öğesini kaldırmak için öğenin üst öğesini seçmeli ve **removeChild(düğüm)** yöntemini kullanmalısınız.[^1]

**Örneğin:**

```html
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <div id="demo">
      <p id="p1">Bu bir paragraf.</p>
      <p id="p2">Bu da başka bir paragraf.</p>
    </div>

    <script>
      window.onload = function() {
        var ebeveyn = document.getElementById("demo");
        var evlat = document.getElementById("p1");

        ebeveyn.removeChild(evlat); // p1'i ebeveyn'in altından kaldırır ve sonuçta p2'yi gösterir.
      };
    </script>
  </body>
</html>
```

> Bu, `id="p1"` içeren paragrafı sayfadan kaldırır.

  [^1]: Aynı sonucu elde etmenin alternatif bir yolu, çıkarmak istediğimiz öğenin ebeveynini almak için **parentNode** özelliğinin kullanılması olabilir: `var alt = document.getElementById("p1"); evlat.parentNode.removeChild(evlat);`

# Elemanları Değiştirme

Bir HTML yerleştirme için element.**replaceChild**(yeniDüğüm, eskiDüğüm) yöntemi kullanılır.

**Örneğin:**

```html
<!DOCTYPE html>
<html>

  <head>
    <title>Sayfa Başlığı</title>
  </head>

  <body>
    <div id="demo">
      <p id="p1">Bu bir paragraf.</p>
      <p id="p2">Bu da başka bir paragraf.</p>
    </div>

    <script>
      window.onload = function() {
        var p = document.createElement("p");
        var düğüm = document.createTextNode("Bu yeni olan bir paragraf");
        p.appendChild(düğüm);

        var ebeveyn = document.getElementById("demo");
        var evlat = document.getElementById("p1");
        ebeveyn.replaceChild(p, evlat);
      };
    </script>
  </body>
</html>
```

> Yukarıdaki kod, mevcut `p1` paragrafının yerini alan yeni bir paragraf öğesi oluşturur.

