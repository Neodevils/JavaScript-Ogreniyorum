# ES6 Rest Parametreleri

ES6'dan önce, bir işleve değişken sayıda argüman iletmek istiyorsak, işleve iletilen parametrelere erişmek için dizi benzeri bir nesne olan **arguments** nesnesini kullanabilirdik.

Örneğin, bir dizinin iletilen tüm argümanları içerip içermediğini kontrol eden bir fonksiyon yazalım:

```javascript
function tumunuIcer(dizi) {
  for(let k = 1; k < arguments.length; k++) {
    let numara = arguments[k];
    
    if(dizi.indexOf(numara) === -1) {
      return false;
    }
  }
  return true;
}

let x = [2, 4, 6, 7];

console.log(tumunuIcer(x, 2, 4, 7)); // true, çünkü tüm argümanları içeriyor.
console.log(tumunuIcer(x, 6, 4, 9)); // false, çünkü 6 ve 9 yok.
```

> `indexOf()` yöntemi, dizide belirli bir öğenin bulunabileceği ilk dizini döndürür `-1` yoksa içindir.
> 
> Bu yüzden bu kod var:

```javascript
if (dizi.indexOf(numara) === -1) {
  return false;
}
```
<hr> 

İşleve herhangi bir sayıda argüman iletebilir ve **arguments** nesnesini kullanarak ona erişebiliriz.

Bu işi yaparken, ES6 bir **rest parametresi** kullanarak değişken sayıda parametre elde etmek için daha okunabilir bir sözdizimi sağlar:

```javascript
function tumunuIcer(dizi, ...numaralar) {
  for(let numara of numaralar) {
    if(dizi.indexOf(numara) === -1) {
      return false;
    }
  }
  return true;
}

let x = [2, 4, 6, 7];

console.log(tumunuIcer(x, 2, 4, 7)); // true
console.log(tumunuIcer(x, 6, 4, 9)); // false
```

**...numaralar** parametresine **rest parametresi** denir. İşleve iletilen tüm "ekstra" argümanları alır. Üç noktaya (...) **Yayılma operatörü** denir.[^1]

  [^1]: Bir fonksiyonun sadece son parametresi dinlenme parametresi olarak işaretlenebilir. Fazladan bağımsız değişken yoksa, rest parametresi yalnızca boş bir *dizi* olacaktır; rest parametresi asla *tanımsız* olmayacaktır.
  
##### Hadi bu soruyu beraber çözelim!

```javascript
function sihir(...numaralar) {
  let topla = 0;
  numaralar.filter(sayi => sayi % 2 == 0).map(element => topla += element);
  
  return topla;
}

console.log(sihir(1, 2, 3, 4, 5, 6));
```

Tek yapmanız gereken, ilk olarak filtre yöntemine `% 2 = 0` geçişlerini kaldırmaktır.

Kırmayı deniyelim! 🙌🏻

**sihir** fonksiyonunda ki `...numaralar` argümanları:

>  1,2,3,4,5,6

Sayı değişkenlerini `% 2 = 0` ile filtrelersek;

* 1 % 2 != 0,
* 2 % 2 = 0,
* 3 % 2 != 0,
* 4 % 2 = 0,
* 5 % 2 != 0,
* 6 % 2 = 0,

Şimdi yukarıdaki filtrelerden testi sadece 2,4,6 geçti. 

Testi geçen öğeden, testi geçen tüm öğeyi değişken toplamına eklemeyi söyleyen başka bir yöntem `map()` ekledik.

Şimdi, `2 + 4 + 6` sayılarını toplar isek,

Cevabımız **12** olur!

<hr> 

# Yayılma Operatörü

Bu operatör Rest Parametresine benzer, ancak nesnelerde veya dizilerde veya işlev çağrılarında (argümanlarda) kullanıldığında başka bir amacı vardır.

## İşlev çağrılarında yayılma

Bir dizinin öğelerini bir işleve argüman olarak iletmek yaygındır. ES6'dan önce aşağıdaki yöntemi kullandık:

```javascript
function fonksiyonum(w, x, y, z) {
  console.log(w + x + y + z);
};

var argumanlar = [1, 2, 3];
fonksiyonum.apply(null, argumanlar.concat(4)); // 10 dönderir
```
ES6, yukarıdaki örneği **spread operatörüyle** yapmanın kolay bir yolunu sunar[^1]

```javascript
const fonksiyonum = (w, x, y, z) => {
  console.log(w + x + y + z);
};

let argumanlar = [1, 2, 3];
fonksiyonum(...argumanlar, 4); // 10 dönderir
```

  [^1]: Örnekte anlatılmak istenen `...argumanlar = 1, 2, 3` ve biz aynı zamanda `4` parametresini de eklediğimizde konsola **w + x + y + z** yazdığımızdan bu sayıların toplamını dönderir.
  
###### Örneğin:

```javascript
var tarihAlanlari = [1970, 0, 1]; // 1 Ocak 1970
var tarih = new Date(...tarihAlanlari);

console.log(tarih); // Tarih nesnesini alırız
```

## Dizi değişmezlerinde yayılma

ES6'dan önce, bir dizinin ortasına bir öğe eklemek için aşağıdaki sözdizimini kullanırdık:

```javascript
var dizi = ["Bir", "İki", "Beş"];

dizi.splice(2, 0, "Üç");
dizi.splice(3, 0, "Dört");

console.log(dizi); // ["Bir", "İki", "Üç", "Dört", "Beş"] dönderir.
```

> `.splice(başlangıç: sayı, silinecekElement: sayı, ...öğeler: dize[])` kullanımı böyledir.

Örneğin, dizinin farklı konumlarında bunu başarmak için push, splice ve concat gibi yöntemleri kullanabilirsiniz. Ancak ES6'da spread operatörü bunu daha kolay yapmamızı sağlar:

```javascript
let yeniDizi = ["Üç", "Dört"];
let dizi = ["Bir", "İki", ...yeniDizi, "Beş"];

console.log(dizi); // ["Bir", "İki", "Üç", "Dört", "Beş"] dönderir 
```

## Nesne değişmezlerinde yayılma

Nesnelerde, sağlanan nesneden kendi numaralandırılabilir özelliklerini yeni bir nesneye kopyalar.

```javascript
const nesne1 = { bilgi: 'çubuk', x: 42 };
const nesne2 = { bilgi: 'baz', y: 5 };

const klonlanmisNesne = { ...nesne1 }; // { bilgi: 'çubuk', x: 42 }
const birlestirilmisNesne = { ...nesne1, ...nesne2 }; // { bilgi: 'baz', x: 42, y: 5 }
```

Ancak, bunları birleştirmeye çalışırsanız beklediğiniz sonucu elde edemezsiniz[^2]

```javascript
const nesne1 = { bilgi: 'çubuk', x: 42 };
const nesne2 = { bilgi: 'baz', y: 5 };

const birles = (...nesneler) => ({ ...nesneler }); // birles fonksiyonunu oluşturduk

let birlesmisNesne = birles(nesne1, nesne2); // { 0: { bilgi: 'çubuk', x: 42 }, 1: { bilgi: 'baz', y: 5 } }

let birlesmisNesne2 = birles({}, nesne1, nesne2); // { 0: {}, 1: { bilgi: 'çubuk', x: 42 }, 2: { bilgi: 'baz', y: 5 } }
```

  [^2]: Nesneleri sığ klonlama veya birleştirme, **Object.assign()** adlı başka bir operatörle mümkündür.