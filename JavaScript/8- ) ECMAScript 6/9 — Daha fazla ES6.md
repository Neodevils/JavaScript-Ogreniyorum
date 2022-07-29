# ES6 `Promises` Vaatleri

Bir **Promise**, **setTimeout()** tipi bir yöntem kullanmanın yaygın yolu ile karşılaştırıldığında, asenkron programlama için daha iyi bir yoldur.

###### Bu örneği düşünelim:

```javascript
setTimeout(function() {
  console.log('İş 1 başladı.');
  
  setTimeout(function() {
    console.log('İş 2 başladı.');
  }, 1000); // 1 saniye sonra dönderir.
}, 1000); // 1 saniye sonra dönderir.

console.log('İş başlıyor.');
```

Bu sırayla "İş başlıyor.", "İş 1 başladı." ve "İş 2 başladı." yazdırır (iş eşzamansız olarak yapılır). Ancak bunun gibi daha fazla olay varsa, kod çok karmaşık hale gelir.

ES6 bu gibi durumlarda kurtarmaya gelir. 🤠

Aşağıdaki gibi bir promise oluşturulabilir:

```javascript
new Promise(function(resolve, reject) {
    // Çalış 
    if (basarili) {
      resolve(sonuc);
    } else {
      reject(Error("Hata"));
    }
});
```

Burada **resolve**, **başarılının** yöntemidir ve **reject**, **başarısızlığın** yöntemidir.

Bir yöntem bir söz verirse, çağrıları iki yöntemi girdi olarak alan **then** yöntemini kullanmalıdır; biri başarı için diğeri başarısızlık için.

###### Örneğin:

```javascript
function asenkFonksiyon(is) {
  return new Promise(function(resolve, reject) {
    if (is === "")
      reject(Error("Hiçbir şey."));

    setTimeout(function() {
      resolve(is);
    }, 1000);
  });
}

asenkFonksiyon("İş 1") // Görev 1

.then(function(sonuc) {
  console.log(sonuc);

  return asenkFonksiyon("İş 2"); // Görev 2
}, function(hata) {
  console.log(hata);
})

.then(function(sonuc) {
  console.log(sonuc);
}, function(hata) {
  console.log(hata);
});

console.log("Son."); // İlk bunu dönderir.
```

Ayrıca "Son", "İş 1" ve "İş 2" yazdırır (iş eşzamansız olarak yapılır). Ancak bu, önceki örneğe göre açıkça daha okunabilir ve daha karmaşık durumlarda çalışmak daha kolay! 😳

# Yineleyiciler ve Üreticiler

**Symbol.iterator**, bir nesne için varsayılan yineleyicidir.  for...of döngüleri bu tür yineleyiciyi temel alır.

Aşağıdaki örnekte nasıl uygulamamız gerektiğini ve **üreteç fonksiyonlarının** nasıl kullanıldığını göreceğiz.

###### Örneğin:

```javascript
let yineleyiciNesnem = {
  [Symbol.iterator] : function*() {
    yield 1; yield 2; yield 3;
  }
};

console.log([...yineleyiciNesnem]); // [1, 2, 3]
```

İlk önce bir nesne oluşturuyoruz ve onu bazı değerlerle doldurmak için **Symbol.iterator** ve **generator işlevini** kullanıyoruz.

Kodun ikinci satırında **function** anahtar sözcüğüyle birlikte **\*** kullanıyoruz.  Buna **jeneratör** işlevi (veya **gen işlevi**) denir.

Örneğin, **gen işlevlerinin** nasıl yararlı olabileceğine dair basit bir örnek:

```javascript
function* kimlikOlusturucu() {
  let dizin = 0;
  
  while(dizin < 5) 
    yield dizin++;
}

var gen = kimlikOlusturucu();

console.log(gen.next().value); // 0 dönderir 
```

Daha sonra jeneratör fonksiyonlarından çıkıp tekrar girebiliriz. Değişken bağlamaları (bağlam) yeniden girişler arasında kaydedilecektir. Özellikle Promises ile birleştirildiğinde, asenkron programlama için çok güçlü bir araçtır. Özel gereksinimleri olan döngüler oluşturmak için de yararlı olabilirler.

Daha karmaşık yapılar oluşturmak için **üreteç işlevlerini** iç içe yerleştirebilir ve onları çağırırken onlara argümanlar iletebiliriz.

Aşağıdaki örnek, **üreteç fonksiyonlarını** ve **Symbol.iterators**'ı birlikte nasıl kullanabileceğimize dair faydalı bir durumu gösterecektir.

```javascript
const dizi = ['0', '1', '4', 'a', '9', 'c', '16'];
const nesnem = {
  [Symbol.iterator]: function*() {
    for (let dizin of dizi) {
      yield `${dizin}`;
    }
  }
};

const hepsi = [...nesnem]
  .map(i => parseInt(i, 10))
  .map(Math.sqrt)
  .filter((i) => i < 5)
  .reduce((i, d) => i + d);

console.log(hepsi); // 10 dönderir 
```

**Symbol.iterator** ve **generator fonksiyonlarını** kullanarak 7 elementten oluşan bir nesne oluşturuyoruz. İkinci bölümde, nesnemizi sabit bir **hepsi**ne atadık. Sonunda değerini yazdırıyoruz.

# Modüller

İlgili kodunuzu modüllere bölmek iyi bir uygulamadır. ES6'dan önce bunu mümkün kılan bazı kütüphaneler vardı (örneğin, RequireJS, CommonJS).  ES6 artık bu özelliği yerel olarak desteklemektedir.

**Modülleri kullanırken dikkat edilmesi gerekenler:**

İlk düşünce, **sürdürülebilirliktir**. Bir modül, diğer modüllerden bağımsızdır ve diğer modüllerdeki koda herhangi bir bağımlılık olmaksızın iyileştirme ve genişletmeyi mümkün kılar.

İkinci düşünce, **ad alanıdır**. Daha önceki bir derste değişkenler ve kapsam hakkında konuştuk. Bildiğiniz gibi, değişkenler global olarak bildirilir, bu nedenle, kodumuzun her yerinden alakasız değişkenlere erişilebilen ad alanı kirliliğine sahip olmak yaygındır. Modüller, değişkenler için özel bir alan oluşturarak bu sorunu çözer.

Bir diğer önemli husus **yeniden kullanılabilirliktir**. Başka projelerde kullanılabilecek kodu yazdığımızda, modüller, kodu yeni bir projede yeniden yazmaya gerek kalmadan kolayca yeniden kullanılmasını mümkün kılar.

Şimdi JS dosyalarında modülleri nasıl kullanmamız gerektiğine bakalım. 👀

###### Örneğin:

```javascript
// ktphn/mat.js

export let topla = (x, y) => { return x + y; }

export let pi = 3.14;

// uygulama.js
import * as matematik from "ktphn/mat"
console.log(`2p = + ${matematik.sum(matemayik.pi, matematik.pi)}`)
```

Burada topla işlevini ve pi değişkenini farklı dosyalarda kullanabilmemiz için dışa aktarıyoruz.[^1]

  [^1]: ES6, **modülleri** resmi olarak destekler, ancak bazı tarayıcılar henüz modülleri yerel olarak desteklememektedir. Bu nedenle, kodumuzu çalıştırmak için Webpack veya Browserify gibi paketleyiciler (oluşturucular) kullanmalıyız.
  
## Yerleşik Yöntemler

ES6 ayrıca birkaç görevi kolaylaştırmak için yeni yerleşik yöntemler de tanıttı. Burada en yaygın olanları ele alacağız.

## Dizi Öğesi Bulma

Bir dizinin ilk öğesini değerine ve kuralına göre bulmanın eski yolu şuydu:

```javascript
var deger = [4, 5, 1, 8, 2, 0].filter(function(x) {
    return x > 3;
})[0];

console.log(deger); // 4 dönderir, çünkü ilk dizini istiyoruz
```

Yeni sözdizimi daha temiz ve daha sağlamdır:

```javascript
let deger = [4, 5, 1, 8, 2, 0].find(x => x > 3);

console.log(deger); // 4 dönderir, .find() metodu ilk bulunan değeri dönderir.
```

Ayrıca `findIndex()` yöntemini kullanarak yukarıdaki öğenin dizinini alabilirsiniz:

```javascript
let deger = [4, 5, 1, 8, 2, 0].findIndex(x => x > 5);

console.log(deger); // 3 dönderir, yani 8 (dizin olarak 3. sırada)
```

## Tekrarlanan Dizeler

ES6'dan önce, bir dizeyi birden çok kez tekrarlamanın doğru yolu aşağıdaki sözdizimiydi:

```javascript
console.log(Array(3 + 1).join("neo")); //neoneoneo
```

Yeni sözdizimi ile şu hale gelir:

```javascript
console.log("neo".repeat(3)); //neoneoneo
```

## Dizeleri Arama

ES6'dan önce, metnin dizedeki konumunu bulmak için yalnızca `indexOf()` yöntemini kullanırdık. Örneğin:

```javascript
"Neodevil".indexOf("Neo") == 0; // true
"Neodevil".indexOf("Neo") == (3 - "Neo". length); // true
```

ES6, bunu daha temiz ve daha basitleştirilmiş sözdizimine sahip bir sürümle değiştirdi:

```javascript
"Neodevil".startsWith("Neo", 0); // true
"Neodevil".endsWith("devil", 4); // true
"Neodevil".includes("angel", 5); // false
```

> Yeni şeyler öğrenmek ve kodunuzu daha anlaşılır kılmak için kodunuzu yeni sözdizimi ile yeniden düzenlemek her zaman iyi bir uygulamadır.

