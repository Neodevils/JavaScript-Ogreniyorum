# Öğeleri Seçme

Tüm HTML öğeleri **nesnelerdir**. Ve bildiğimiz gibi, her nesnenin **özellikleri** ve **yöntemleri** vardır.

**document** nesnesi, istenen HTML öğesini seçmenize izin veren yöntemlere sahiptir.

Bu üç yöntem, HTML öğelerini seçmek için en yaygın olarak kullanılanlardır:

```javascript
//kimliğe göre eleman bulur
document.getElementById(id) 

//öğeleri sınıf adına göre bulur
document.getElementsByClassName(isim) 

//öğeleri etiket adına göre bulur
document.getElementsByTagName(isim)
```

Aşağıdaki örnekte, ``id="demo"`` olan öğeyi seçmek ve içeriğini değiştirmek için **getElementById** yöntemi kullanılır:[^1]

```javascript
var element = document.getElementById("demo");

element.innerHTML = "Selam Dünya!"; //Selam Dünya! yazdırılır.
```

  [^1]: Yukarıdaki örnek, HTML'nin `id="demo"` içeren bir öğe içerdiğini varsayar, örneğin \<div id = "demo">\</div>.

<hr>

**getElementsByClassName()** yöntemi, belirtilen sınıf adıyla belgedeki tüm öğelerin bir koleksiyonunu döndürür.

Örneğin, HTML sayfamız class="demo" içeren üç öğe içeriyorsa, aşağıdaki kod tüm bu öğeleri bir dizi olarak döndürür:

```javascript
var dizi =  document.getElementsByClassName("demo");
//ikinci elemana erişiyoruz

dizi[1].innerHTML = "Selam!";
```

<hr>

Benzer şekilde, **getElementsByTagName** yöntemi, belirtilen etiket adının tüm öğelerini bir dizi olarak döndürür.

Aşağıdaki örnek, sayfanın tüm paragraf öğelerini alır ve içeriğini değiştirir:

```html
<p>selam</p>
<p>merhaba</p>
<p>naber?</p>

<script>
  var dizi = document.getElementsByTagName("p");
  
  for (var x = 0; x < dizi.length; x++) {
    dizi[x].innerHTML = "Selam ordaki!";
  }
</script>
```

Komut dosyası aşağıdaki HTML ile sonuçlanacaktır:[^2]

```html	
<p>Selam ordaki!</p>
<p>Selam ordaki!</p>
<p>Selam ordaki!</p>
```

  [^2]: Yukarıdaki örnekte seçilen tüm öğeler arasında döngü yapmak için dizinin **length** özelliğini kullandık.

## DOM ile çalışma

DOM'deki her öğenin, DOM'deki ilişkileri hakkında bilgi sağlayan bir dizi özelliği ve yöntemi vardır:

* ``element.childNodes``, bir öğenin alt düğümlerinin bir dizisini döndürür.

* ``element.firstChild``, bir öğenin ilk alt düğümünü döndürür.

* ``element.lastChild``, bir öğenin son alt düğümünü döndürür.

* ``element.hasChildNodes``, bir öğenin alt düğümleri varsa true, aksi takdirde false döndürür.

* ``element.nextSibling``, aynı ağaç düzeyinde bir sonraki düğümü döndürür.

* ``element.previousSibling``, önceki düğümü aynı ağaç düzeyinde döndürür.

* ``element.parentNode``, bir öğenin üst düğümünü döndürür.

Örneğin, bir öğenin tüm alt düğümlerini seçebilir ve içeriklerini değiştirebiliriz:[^3]

*HTML kodu*

```html	
<html>
  <body>
    <div id = "demo">
      <p>bir metin</p>
      <p>başka bir metin</p>
    </div>
  </body>
</html>
```
 
*JavaScript kodu*

```javascript
function metinAyarla() {
  var a = document.getElementById("demo");
  var dizi = a.childNodes;
  
  for(var x = 0; x < dizi.length; x++) {
    dizi[x].innerHTML = "yeni metin";
  }
}

setTimeout(metinAyarla, 500); // HTML'nin yüklendiğinden emin olmak için işlevi setTimeout ile çağırma, 500ms sonra çalışacaktır.
```

  [^3]: Yukarıdaki kod, her iki paragrafın metnini "yeni metin" olarak değiştirir.