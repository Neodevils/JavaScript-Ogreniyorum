# ECMAScript 6'da Fonksiyonlar

ES6'dan önce, bir JavaScript işlevi şu şekilde tanımlanmıştı:

```javascript
function topla(x, y) {
  var toplama = x + y;
  
  console.log(toplama); 
}

topla(3, 4); // 7 dönderir 
```

ES6, yazma işlevleri için yeni bir sözdizimi sunar. Yukarıdan aynı fonksiyon şu şekilde yazılabilir:

```javascript
const topla = (x, y) => {
  let toplama = x + y;
  
  console.log(toplama); 
}

topla(3, 4); // 7 dönderir 
```

Bu yeni sözdizimi, tek argümanlı basit bir işleve ihtiyacınız olduğunda oldukça kullanışlıdır.

Bazı parantez ve parantezlerin yanı sıra **function** ve **return**'u da atlayabilirsiniz.

```javascript
const selamla = x => "Hoşgeldin " + x;

selamla('Neo'); // x parametredir
```

Yukarıdaki kod, bir argümanı olan ve bir mesaj döndüren **selamla** adlı bir fonksiyonu tanımlar.

Parametre yoksa, aşağıdaki gibi boş bir parantez çifti kullanılmalıdır.

```javascript
const x = () => alert("Selam!");

x(); // Uyarı kutusunda "Selam!" çıktısı alırız
```

<hr>

Sözdizimi, satır içi işlevler için çok kullanışlıdır. Örneğin, bir *dizimiz* olduğunu ve dizinin her bir elemanı için bir fonksiyon yürütmemiz gerektiğini varsayalım. Her öğe için bir işlev çağırmak için *dizinin* **`forEach`** yöntemini kullanırız:

```javascript
var dizi = [2, 3, 7, 9];

dizi.forEach(function(elemanlar) {
  console.log(elemanlar * 2);
}); // dizi değişkeninin elemanlarını 2 ile çarpar ve dönderir.
```

Ancak, ES6'da yukarıdaki kod aşağıdaki gibi yeniden yazılabilir[^1]:

```javascript
const dizi = [2, 3, 7, 9];

dizi.forEach(el => {
  console.log(el * 2);
}); // dizi değişkeninin elemanlarını 2 ile çarpar ve dönderir.
```

  [^1]: Kod daha kısa ve çok daha güzel gözüküyor, değil mi? 🙃

## ES6'da Varsayılan Parametreler

ES6'da varsayılan değerleri fonksiyonların imzasına koyabiliriz.

**Örneğin:**

```javascript
function test(a, b = 3, c = 42) {
  return a + b + c;
}

console.log(test(5)); // a değerine 5 atanır ve toplam olarak 50 değerini dönderir
```

Ve işte varsayılan parametrelere sahip bir ok işlevi örneği 🤭:

```javascript
const test = (a, b = 3, c = 42) => {
  return a + b + c;
}

console.log(test(5)); // a değerine 5 atanır ve toplam olarak 50 değerini dönderir
```

