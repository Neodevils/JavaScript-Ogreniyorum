# `return` döndür ifadesi

Bir fonksiyon, isteğe bağlı bir `return` ifadesine sahip olabilir. Fonksiyondan bir değer döndürmek için kullanılır.

Bu ifade, sonuç gerektiren hesaplamalar yaparken kullanışlıdır.[^1]

  [^1]: JavaScript bir *return* ifadesine ulaştığında, fonksiyon çalışmayı durdurur.

<hr>

Bir değer döndürmek için return ifadesini kullanırız.[^2]

Örneğin, iki sayının çarpımını hesaplayalım ve sonucu döndürelim. 😀

```javascript
function carpma(a, b) {
  return a * b;
}

var sonuc = carpma(8, 10); 

console.log(sonuc); // 80
```

  [^2]: Bir fonksiyondan hiçbir şey döndürmezsek, **tanımsız** olarak dönecektir.

<hr>

**Başka bir örnek:**

```javascript
function numaraEkle(a, b) {
  var c = a + b;

  return c;
}
document.write(numaraEkle(30, 2)); // 32
``` 

*`document.write` komutu, iki parametrenin toplamı olan işlev tarafından döndürülen değeri verir.*
