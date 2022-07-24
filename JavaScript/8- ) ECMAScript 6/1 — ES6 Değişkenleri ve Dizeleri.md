# `var` & `let`

ES6'da değişkenleri bildirmenin üç yolu vardır:

```javascript
var a = 10;

const b = 'selam';

let c = true;
```

Kullanılan beyan türü, gerekli **kapsama** bağlıdır. **Kapsam**, bir değişkenin görünürlüğünü tanımlayan tüm programlama dillerinde temel kavramdır.

**var** ve **let**
Bir değişkeni blok kapsamından bağımsız olarak global olarak veya yerel olarak tüm fonksiyon için tanımlayan **var** anahtar sözcüğünün aksine, **let** kapsamı sınırlı değişkenleri kullanıldıkları blok, deyim veya ifade ile bildirmenize izin verir.

<hr>

Örneğin:

```javascript
if (true) {
  let isim = 'Neo';
}

alert(isim); // hata oluşturur
```

Bu durumda **name** değişkeni **let** olarak bildirildiği için yalnızca if ifadesinin kapsamında erişilebilir.

**var** ve **let** arasındaki kapsam farkını göstermek için şu örneği göz önünde bulunduralım:

```javascript
function varTest() {
  var x = 1;
  
  if (true) {
    var x = 2; // aynı değişken 
    console.log(x); // 2 dönderir 
  }
  
  console.log(x); // 2 dönderir 
}

function letTest() {
  let x = 1;
  
  if (true) {
    let x = 2; // farklı değişken 
    console.log(x); // 2 dönderir 
  }
  
  console.log(x); // 1 dönderir 
}
```

<hr>

**let** için en iyi kullanımlardan biri döngülerdir:

```javascript
for(let i = 0; i < 3; i++) {
  document.write(i); // 0'dan 2'ye kadar aynı satırda yazar. Yani, "012" dönderir.
}
```

Burada, **i** değişkenine yalnızca gerekli olduğu yerde `for` döngüsü kapsamında erişilebilir.[^1]

  [^1]: **let**, **Değişken Kaldırmaya** tabi değildir; **let** bildirimlerinin geçerli yürütme bağlamının en üstüne taşınmadığı anlamına gelir.

# `const`

**const** değişkenleri, **let** kullanılarak bildirilen değişkenlerle aynı kapsama sahiptir. Farkı ise, **const** değişkenlerinin değişmez olmasıdır - **yeniden atanmalarına izin verilmiyor** kısacası.[^1] 🙌🏻

Örneğin, aşağıdakiler bir istisna oluşturur:

```javascript
const a = "Merhaba";
a = "Güle güle";

console.log(a); // Hata döndürecektir.
```

> **const**, **Değişken Kaldırmaya** da tabi değildir; bu, const bildirimlerinin mevcut yürütme bağlamının en üstüne taşınmadığı anlamına gelir. 
> 
> Ayrıca ES6 kodunun yalnızca onu destekleyen tarayıcılarda çalışacağını unutmayın. ES6'yı desteklemeyen daha eski cihazlar ve tarayıcılar bir sözdizimi hatası döndürür.

## ES6'da Şablon Değişmezleri

**Şablon değişmezleri**, dizedeki değişkenleri çıkarmanın bir yoludur.

ES6'dan önce dizeyi kırmamız gerekiyordu, örneğin:

```javascript
var isim = 'Neo';
var mesaj = 'Hoşgeldin ' + isim + '!';

console.log(mesaj); // Hoşgeldin Neo!
```

ES6, dizelerde değişken değerlerin çıktısını almanın yeni bir yolunu sunuyor. Yukarıdaki aynı kod şu şekilde yeniden yazılabilir 😁

```javascript
var isim = 'Neo';
var mesaj = `Hoşgeldin ${isim}!`;

console.log(mesaj); // Hoşgeldin Neo!
```

Şablon değişmezlerinin çift veya tek tırnak yerine **ters tik** (\` \`) karakteriyle çevrelendiğine dikkat edin.

**${ifade}** bir yer tutucudur ve değerlendirilecek ve şablon değişmezine eklenecek herhangi bir ifadeyi içerebilir.[^2]

<hr>

Örneğin:

```javascript
let a = 8;
let b = 34;
let mesaj = `Toplamları ${a+b} olur.`;

console.log(mesaj); // Toplamları 42 olur.
```

  [^2]: Bir şablon değişmezinde bir ters tik işaretinden kaçmak için, ters eğik çizgiden önce \ bir ters eğik çizgi koy! 
  
