# ES6'da Sınıflar

Bu derste, aynı yapıdaki birden çok nesneyi oluşturmak için kullanılabilecek bir **class**'ın nasıl oluşturulacağını öğreneceğiz.

Bir sınıf, **class** anahtar sözcüğünü kullanır ve başlamak için bir **constructor** yöntemi içerir.

###### Örneğin:

```javascript
class Dikdortgen  {
  constructor(yukseklik, genislik) {
    this.yukseklik = yukseklik;
    this.genislik = genislik;
  }
};
```

Bildirilen bir sınıf daha sonra **new** anahtar sözcüğünü kullanarak birden çok nesne oluşturmak için kullanılabilir.[^1]

```javascript
const kare = new Dikdortgen(5, 5);
const poster = new Dikdortgen(2, 3);
```

  [^1]: İşlev Bildirgeleri yapılırken Sınıf Bildirimleri **kaldırılmaz**. Bildirmeden önce sınıfınıza erişmeye çalışırsanız **`ReferenceError`** döndürülür.
  
Ayrıca, sınıfın adlandırılabileceği veya adlandırılamayacağı bir **sınıf ifadesi** ile bir sınıf tanımlayabilirsiniz.

**Adlandırılmış bir sınıf** şöyle görünür:

```javascript
var Kare = class Dikdortgen {
  constructor(yukseklik, genislik) {
    this.yukseklik = yukseklik;
    this.genislik = genislik;
  }
};
```

Adsız sınıf ifadesinde, bir *değişkene* basitçe sınıf tanımı atanır[^2]

```javascript
var Kare = class {
  constructor(yukseklik, genislik) {
    this.yukseklik = yukseklik;
    this.genislik = genislik;
  }
};
```

  [^2]: `constructor`, bir sınıfla oluşturulan bir nesneyi oluşturmak ve başlatmak için kullanılan özel bir yöntemdir. Her sınıfta sadece bir `constructor` olabilir.
  
## ES6'da Sınıf Yöntemleri

ES6, bir yöntemin adına atanan bir **işlev** için anahtar sözcük işlevi gerektirmeyen bir kestirme yol sundu. Sınıf yönteminin bir türü, nesnenin nesneleri için kullanılabilen **prototip yöntemidir**.[^3]

```javascript
class Dikdortgen {
  constructor(yukseklik, genislik) {
    this.yukseklik = yukseklik;
    this.genislik = genislik
  }

  get alan() {
    return this.hesaplanmisAlan();
  }
  
  hesaplanmisAlan() {
    return this.yukseklik * this.genislik;
  }
}

const kare = new Dikdortgen(5, 5);

console.log(kare.alan); // 25 dönderir 
```

  [^3]: Yukarıdaki kodda **alan** bir *alıcı*, **calcArea** bir *yöntemdir*.
  
Başka bir yöntem türü, bir sınıf örneği aracılığıyla çağrılamayan **`static` yöntemdir**. Statik yöntemler genellikle bir uygulama için yardımcı işlevler oluşturmak için kullanılır.

###### Örneğin

```javascript
class Isaret {
  constructor(x, y) {
    this.x = x; // 7 veya 3
    this.y = y; // 2 veya 8
  }
  
  static mesafe(a, b) { 
  // i1 , i2 
    const mesx = a.x - b.x; 
  // 7 - 3 = 4
    const mesy = a.y - b.y; 
  // 2 - 8 = -6
    return Math.hypot(mesx, mesy); 
  // √(4)² + (-6)² = √52 = 7.21110255...
  }
}

const i1 = new Isaret(7, 2);
const i2 = new Isaret(3, 8);

console.log(Isaret.mesafe(i1, i2)); 

/*
   |    (3,8)=(x1,y1)
 8 |      .
   |      |\
   |      | \
   |      |  \
   |      |   \  √(x2-x1)² + (y2-y1)²
   |   -6 |    \
   |      |     \
   |      |      \
 2 |      |_______\.(7,2)=(x2,y2)
   |          4
___|________________________ x
  0|      3        7
   |
   |
   |
   |
   |
   |
   |
       
       
    

basitçe,

  |\
a | \ c = hipotenüs
  |__\
    b

a² + b² = c²
√a² + b² = c
*/

```

> Gördüğünüz gibi, statik **mesafe** yöntemi bir nesne olmadan doğrudan sınıf adı kullanılarak çağrılır.

## ES6'da kalıtım

**extends** anahtar sözcüğü, bir sınıfın alt öğesini oluşturmak için sınıf bildirimlerinde veya sınıf ifadelerinde kullanılır. Çocuk, ebeveynin özelliklerini ve yöntemlerini devralır.

```javascript
class Hayvan {
  constructor(isim) {
    this.isim = isim;
  }
  
  konusma() {
    console.log(`${this.isim} ses çıkarıyor.`);
  }
}

class Kopek extends Hayvan {
  konusma() {
    console.log(`${this.isim} havlıyor.`)
  }
}

let kopek = new Kopek('Max');
kopek.konusma();
```

Yukarıdaki kodda, **Kopek** sınıfı, özelliklerini ve yöntemlerini devralan **Hayvan** sınıfının bir çocuğudur.[^4]

  [^4]: Alt sınıfta bir kurucu varsa, **this**'i kullanmadan önce **super()**'i çağırması gerekir. Ayrıca, ebeveynin yöntemlerini çağırmak için **super** anahtar sözcüğü kullanılır.

<hr>
  
Örneğin, yukarıdaki programı aşağıdaki şekilde değiştirebiliriz:[^5]

```javascript
class Hayvan {
  constructor(isim) {
    this.isim = isim;
  }

  konusma() {
    console.log(`${this.isim} ses çıkarıyor.`);
  }
}

class Kopek extends Hayvan {
  konusma() {
    super.konusma(); // Süper
    console.log(`${this.isim} havlıyor.`)
  }
}

let kopek = new Kopek('Max');
kopek.konusma();
```

  [^5]: Yukarıdaki kodda, **super** anahtar sözcüğü kullanılarak ebeveynin `konusma()` yöntemi çağrılır.
  
