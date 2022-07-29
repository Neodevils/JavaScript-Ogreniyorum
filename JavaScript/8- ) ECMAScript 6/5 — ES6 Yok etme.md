# ES6'da Dizi Yok Etme

**destructuring (yok etme)** atama sözdizimi, dizilerdeki değerleri veya nesnelerden gelen özellikleri farklı değişkenlere açmayı mümkün kılan bir JavaScript ifadesidir.

ES6, bir *diziyi* yok etmek için bir kısayol sözdizimi ekledi.


Aşağıdaki örnek, bir dizinin öğelerinin farklı değişkenlere nasıl açılacağını gösterir:

```javascript
let dizi = ['1', '2', '3'];
let ['bir', 'iki', 'üç'] = dizi;

console.log({bir, iki, üç}); // 1, 2 ve 3'ü nesne halinde dönderir 
```

Bir fonksiyon tarafından döndürülen bir diziyi yok etmeyi de kullanabiliriz.

```javascript
let a = () => {
  return [1, 3, 2];
};
let [bir,  , iki] = a();

console.table(a()); // tablo halinde a'yı dönderir 
```

İkinci argümanın yerini boş bıraktığımıza dikkat et! 🙃

Yıkıcı sözdizimi ayrıca değerleri atamayı ve değiştirmeyi de basitleştirir:

```javascript
let a,
    b,
    c = 4,
    d = 8;
    
[a, b = 6] = [2]; // a = 2, b = 6

[c, d] = [d, c]; // c = 8, d = 4

console.log(a, b, c, d); // 2 6 8 4 dönderir 
```

## ES6'da Nesne Yıkımı

Dizi yok etmeye benzer şekilde, **Nesne yok etme**, özellikleri farklı değişkenlere açar.

```javascript
let nesne = { h: 100, s: true }
let { h, s } = nesne;

console.log({ h, s }); // Object { h: 100, s: true } dönderir.
```

Bildirim olmadan atayabiliriz, ancak bunun için bazı sözdizimi gereksinimleri vardır:

```javascript
let a, b;
(a, b = { a: 'Merhaba ', b: 'Neo' });

console.log(a + b); // Merhaba Neo
```

Sondaki **noktalı virgül (;)** olan **()** işareti, bildirim yapılmadan **yok edilirken zorunludur**. Ancak, **()** gerekli olmadığında bunu aşağıdaki gibi de yapabilirsiniz:

```javascript
let (a, b) = { a: 'Merhaba ', b: 'Neo' };

console.log(a + b); // Merhaba Neo dönderir 
```

<hr>

Nesneyi yeni değişken adlarına da atayabilirsiniz.

###### Örneğin:

```javascript
var o = { h: 42, s: true };
var { h: bilgi, s: cubugu } = o;

// console.log(h); Hata verir!
console.log(bilgi); // 42
```

<hr>

Son olarak, nesneden çıkarılan değerin tanımsız olması durumunda, değişkenlere **varsayılan değerler** atayabilirsiniz.[^1]

```javascript
var nesne = { kimlik: undefined, isim: 'Neo' };
let { kimlik = 10, yas = 20 } = nesne;

console.log(kimlik); // 10 dönderir, yani varsayılan değeri görürüz 
console.log(yas); // 20 dönderir

```

  [^1]: Kodu dene ve ne dönderdiğine bir göz at! 🤠
  