# ES6 Nesneleri

JavaScript değişkenleri, **özellikler** adı verilen birçok değeri içeren **Nesne** veri türleri olabilir.

Bir *nesne* ayrıca, *nesne* üzerinde eylemler gerçekleştirmeye yönelik **yöntemler** olarak adlandırılan işlev tanımları olan özelliklere de sahip olabilir.

ES6, nesneleri bildirmeyi ve kullanmayı daha kolay anlamayı sağlayan *kestirme* gösterimler ve *hesaplanmış* özellik adları sunar.

Yeni *yöntem* tanımı steno, **ağaç** nesnesi bildiriminin **büyüme** işlevinde olduğu gibi iki nokta üst üste (:) veya **function** anahtar sözcüğünü gerektirmez:

```javascript
let agac = {
  yukseklik: 10,
  renk: 'yeşil',
  buyume() {
    this.yukseklik += 2;
  }
};

agac.buyume(); // büyüme fonksiyonunu çağırıyoruz

console.log(agac.yukseklik); // 12 dönderir
```

Aynı ada sahip bir *değişkenle* özellikleri başlatırken bir özellik değeri kısayolu da kullanabilirsiniz.

Örneğin, **yükseklik** ve **sağlık** özellikleri, **yükseklik** ve **sağlık** adlı değişkenlerle başlatılıyor:

```javascript
let yukseklik = 5;
let saglik = 100;

let atlet = {
  yukseklik,
  saglik
}

console.log(atlet); // Atlet objesini dönderir
```

Yinelenen özellik adlarını kullanarak bir *nesne* oluştururken, son özellik, aynı adı taşıyan öncekilerin üzerine yazacaktır.[^1]

**Örneğin:**

```javascript
var a = {x: 1, x: 2, x: 3, x: 4}

console.log(a); // x: 4 objesini dönderir.
```

  [^1]: Yinelenen özellik adları, katı mod (strict mode) kullanılırken ES5'te bir **SyntaxError** hatasını oluştururdu. Ancak, ES6 bu sınırlamayı kaldırdı. 🤠
  
## Hesaplanan Özellik Adları

ES6 ile artık **hesaplanmış özellik** adlarını kullanabilirsiniz. Köşeli parantez [] gösterimini kullanarak, bir özellik adı için bitiştirilmiş dizeler de dahil olmak üzere bir ifade kullanabiliriz. Bu, kullanıcı verilerine (örn. id, e-posta vb.) dayalı olarak belirli nesneler oluşturmak istediğimiz durumlarda yararlı olabilir.[^2]

İşte üç örnek:

###### İlk Örnek:

```javascript
let ozel = 'isim',
    kimlik = '1234',
    mobil = '0987';

let kullanici = {
  ['ozel']: 'Neo',
  [`kullanici_${kimlik}`]: `${mobil}`
};

console.log(kullanici); // Object { ozel: "Neo", kullanici_1234: "0987" } dönderir
```

###### İkinci Örnek:

```javascript
var i = 0;
var a = {
  ['bilgi' + ++i]: i,
  ['bilgi' + ++i]: i,
  ['bilgi' + ++i]: i
}

console.log(a); // Object { bilgi1: 1, bilgi2: 2, bilgi3: 3 } dönderir
```

###### Üçüncü Örnek:

```javascript
var parametre = 'boyut';
var yapilandirma = {
  [parametre]: 12,
  ['mobil' + parametre.charAt(0).toUpperCase() + parametre.slice(1)]: 4
};

console.log(yapilandirma.mobilBoyut); // 4 dönderir
```
> `charAt(0)`: parametre değişkeninin ilk karakterini alır (Yani "b")
> `toUpperCase()`: indeksi 0 olan karakteri büyük harf yapar (Yani "B")
> `slice(1)`: parametre değişkeninin birinci indeks dahil son karakterine kadar alır (Yani "oyut")
  
> Sonuç ise "Boyut" olur. Ve biz bunu 'mobil' + 'B' + 'oyut' yaptığımız da sonuç olarakta "mobilBoyut" değerini alıyoruz.

  [^2]: Bazı değişkenlere dayalı özel nesneler oluşturmanız gerektiğinde çok kullanışlıdır. 🤗
  
## ES6'da `Object.assign()`

ES6, tek bir yeni *nesne* oluşturmak için birden çok kaynağı tek bir hedefte birleştirmemize olanak tanıyan yeni bir **Nesne** *yöntemi* **assign()** ekler.

**Object.assign()** ayrıca mevcut bir *nesnenin* bir kopyasını oluşturmak için de kullanışlıdır.

Nesnelerin nasıl birleştirileceğini görmek için aşağıdaki örneğe bakalım:

```javascript
let kisi = {
  isim: 'Neo',
  yas: 21,
  cinsiyet: 'Erkek'
};

let ogrenci = {
  isim: 'Micha',
  yas: 16,
  deneyim: '2'
};

let yeniOgrenci = Object.assign({}, ogrenci, kisi);

console.log(yeniOgrenci); // Object { isim: "Neo", yas: 21, deneyim: "2", cinsiyet: "Erkek" } dönderir 
```

Burada, ilk parametrenin yeni özellikler uygulamak istediğiniz **hedef nesne** olduğu **Object.assign()**'i kullandık.

İlkinden sonraki her parametre hedef için **kaynak** olarak kullanılacaktır. Kaynak parametrelerinin sayısında herhangi bir sınırlama yoktur. Ancak sıra önemlidir, çünkü ikinci parametredeki özellikler üçüncü parametredeki aynı ada sahip özellikler tarafından geçersiz kılınır ve bu böyle devam eder.

Yukarıdaki örnekte, hedef olarak yeni bir *nesne* {} kullandık ve kaynak olarak iki nesne kullandık.[^3]

  [^3]: Sonuca ne olduğunu görmek için ikinci ve üçüncü parametrelerin sırasını değiştirmeyi dene! 😳
  
<hr>

Şimdi, temel *nesneye* bir referans (mutasyona uğramadan) oluşturmadan yinelenen bir nesne oluşturmak için **assign()**'i nasıl kullanabileceğimizi görelim.

Aşağıdaki örnekte, yeni bir nesne oluşturmaya çalışmak için atama kullanılmıştır. Ancak, `=` kullanılması temel nesneye bir başvuru oluşturur. Bu başvuru nedeniyle, yeni bir nesneye yönelik değişiklikler orijinal nesneyi değiştirir:

```javascript
let sahis = {
  isim: 'Micha',
  yas: 16
};

let yeniSahis = sahis; // yeniSahis, sahis'i referans eder
yeniSahis.isim = 'Neo';

console.log(sahis.isim); // Neo
console.log(yeniSahis.isim); // Neo
```

Bunu (mutasyonlar) önlemek için, yeni bir nesne oluşturmak için **Object.assign()**'i kullanalım.

**Örneğin:**

```javascript
let sahis = {
  isim: 'Micha',
  yas: 16
};

let yeniSahis = Object.assign({}, sahis);

yeniSahis.isim = 'Neo';

console.log(sahis.isim); // Micha
console.log(yeniSahis.isim); // Neo
```

Ve son olarak, **Object.assign()** deyiminde bir nesne özelliğine bir değer atayabiliriz.[^4] 🙌🏻

**Örneğin:**

```javascript
let sahis = {
  isim: 'Micha',
  yas: 16
};

let yeniSahis = Object.assign({}, sahis, {isim: 'Neo'});
```

  [^4]: Kodu çalıştır ve nasıl çalıştığını gör! 🤠
  
