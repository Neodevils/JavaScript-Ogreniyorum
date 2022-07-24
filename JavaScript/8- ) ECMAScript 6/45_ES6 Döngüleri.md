# ECMAScript 6'da Döngüler

JavaScript'te, bir listedeki değerleri yinelemek için genellikle **for** döngüsünü kullanırız:

```javascript
let dizi = [1, 2, 3];

for(let k = 0; k < dizi.length; k++) {
  console.log(dizi[k]); // Sırasıyla 1, 2 ve 3 döndürür.
}
```

**for...in** döngüsü, bir *nesnenin* numaralandırılabilir anahtarları üzerinde yineleme yapmak için tasarlanmıştır.[^1]

**Örneğin:**

```javascript
let nesne = {a: 1, b: 2, c: 3};

for (let ozellik in nesne) {
  console.log(ozellik + ': ' + nesne[ozellik]); // Sırasıyla a: 1, b: 2 ve c: 3 yazar.
}
```

  [^1]: **for...in** döngüsü diziler üzerinde yineleme yapmak için **KULLANILMAMALIDIR**, çünkü JavaScript motoruna bağlı olarak rastgele bir sırayla yinelenebilir. Ayrıca, yinelenen değişken bir sayı değil bir dizedir, bu nedenle değişkenle herhangi bir matematik yapmaya çalışırsanız, toplama yerine dize birleştirme işlemi gerçekleştirirsiniz. 😅
  
<hr>

ES6, yinelenebilir nesneler üzerinde yinelenen bir döngü oluşturan yeni **for...of** döngüsünü sunuyor! 😎

**Örneğin:**

```javascript
let liste = ["x", "y", "z"];

for(let deger of liste) {
  console.log(deger); // x, y ve z dönderir 
}
```

Her yineleme sırasında **deger** değişkenine listedeki karşılık gelen öğe atanır.

**for...of** döngüsü, dizeler de dahil olmak üzere diğer yinelenebilir nesneler için de çalışır[^2]

  [^2]: **for...of** döngüsü, yeni tanıtılan koleksiyonlarda da çalışır (Map, Set, WeakMap ve WeakSet).
  
<hr>

Kısa bir anlatım ile:

```javascript
let diller =['HTML', 'CSS', 'JavaScript'];

for(let dil in diller){
  console.log(dil); // for...in sıraları yazdırır iken
}

for(let dil of diller){
  console.log(dil); // for...of değerleri yazdırır. 
}
```

