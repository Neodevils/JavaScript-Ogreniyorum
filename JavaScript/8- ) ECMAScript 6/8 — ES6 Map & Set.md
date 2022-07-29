# ES6'da `Map` (Harita)

**Anahtar/değer** çiftlerini tutmak için bir **Map** nesnesi kullanılabilir. Bir map'te ki anahtar veya değer herhangi bir şey olabilir (nesneler ve ilkel değerler). 

**new Map([yinelenebilir])** sözdizimi, yinelenebilir bir dizi veya öğeleri dizi olan (her biri bir anahtar/değer çifti olan) başka herhangi bir yinelenebilir nesne olan bir Map nesnesi oluşturur.

Bir Nesne, Map'e benzer, ancak belirli durumlarda bir Map kullanmayı tercih edilebilir kılan önemli farklılıklar vardır:

* Anahtarlar, işlevler, nesneler ve herhangi bir ilkel dahil olmak üzere herhangi bir türde olabilir.

* Bir Haritanın boyutunu alabilirsiniz.

* Harita üzerinde doğrudan yineleme yapabilirsiniz.

* Haritanın performansı, anahtar/değer çiftlerinin sık eklenmesini ve çıkarılmasını içeren senaryolarda daha iyidir.

**size** özelliği, bir haritadaki anahtar/değer çiftlerinin sayısını döndürür.

```javascript
let harita = new Map([['a1', 'd1'], ['a2', 'd2']]);

console.log(harita.size); // 2
```

<hr>

### Yöntemler 

* `set(anahtar, değer)` — Haritaya belirli bir anahtar/değer çifti ekler. Belirtilen anahtar zaten varsa, buna karşılık gelen değer belirtilen değerle değiştirilir.

* `get(anahtar)` — Haritada belirtilen bir anahtara karşılık gelen değeri alır. Belirtilen anahtar yoksa, tanımsız döndürülür.

* `has(anahtar)` — Haritada belirtilen bir anahtar varsa true, aksi takdirde false döndürür.

* `delete(anahtar)` — Belirtilen bir anahtarla anahtar/değer çiftini haritadan siler ve true değerini döndürür. Öğe yoksa false döndürür.

* `clear()` — Tüm anahtar/değer çiftlerini haritadan kaldırır.

* `keys()` — Her öğe için haritadaki anahtarların yineleyicisini döndürür.

* `values()` — Her öğe için haritadaki değerlerin bir Yineleyicisini döndürür.

* `entries()` — Her öğe için haritada [anahtar, değer] dizisinin yineleyicisini döndürür.
 
###### Örneğin:

```javascript
let harita = new Map();

harita.set('a1', 'd1').set('a2', 'd2');

console.log(harita.get('a1')); // d1
console.log(harita.has('a2')); // true

for(let ad of harita.entries()) {
  console.log(ad[0] + " : " + ad[1]); // anahtarları ve değerleri dönderir 
};
```

Yukarıdaki örnek, ES6 Harita yöntemlerinden bazılarını göstermektedir.[^1]

  [^1]: **Map** farklı veri türlerini destekler, yani **1** ve **"1"** iki farklı anahtar/değerdir.
  
# ES6'da `Set` (Ayarlama)

**Benzersiz** değerleri tutmak için bir `Set` nesnesi kullanılabilir (tekrarlara izin verilmez).

Bir kümedeki bir değer herhangi bir şey olabilir (nesneler ve ilkel değerler).

**new Set([yinelenebilir])** sözdizimi, yinelenebilir bir dizi veya başka herhangi bir **yinelenebilir** değerler nesnesi olan bir **Set** nesnesi oluşturur.

**size** özelliği, bir kümedeki farklı değerlerin sayısını döndürür.

###### Örneğin:

```javascript
let set = new Set([1, 2, 4, 2, 59, 9, 4, 9, 1]);

console.log(set.size); // 5 dönderir 
```

### Yöntemler 

* `add(değer)` — Set'e verilen değere sahip yeni bir eleman ekler.

* `delete(değer)` — Belirtilen bir değeri kümeden siler.

* `has(değer)` — Kümede belirtilen bir değer varsa true, aksi takdirde false döndürür.

* `clear()` — Kümeyi temizler.

* `values()` — Kümedeki değerlerin yineleyicisini döndürür.

###### Örneğin:

```javascript
let set = new Set();

set.add(5).add(9).add(59).add(9);

console.log(set.has(9)); // true

for(let d of set.values()) {
  console.log(d); // 5, 9 ve 59 dönderir 
};
```

Yukarıdaki örnek, ES6 Set yöntemlerinden bazılarını göstermektedir.[^2]

  [^2]: **Set**, farklı veri türlerini destekler, yani **1** ve **"1"** iki farklı değerdir. NaN ve undefined ayrıca Set'te saklanabilir.

