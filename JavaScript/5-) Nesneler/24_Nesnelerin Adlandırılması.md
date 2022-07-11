# JavaScript Nesneleri

JavaScript değişkenleri, veri değerleri için kapsayıcılardır. Nesneler de değişkendir, ancak birçok değer içerebilirler.

Bir nesneyi, adlar ve değerler iki nokta üst üste ile ayrılmış, ad:değer çiftleri olarak yazılan bir değerler listesi olarak düşünün.[^1]


**Örnek:**

```javascript	
var karakter = {
  isim: "Neo", 
  yas: 20, 
  favRengi: "Pastel Kırmızısı", 
  boy: 175
};
```

Bu değerlere **özellik** denir.

| Özellik | Özellik Değeri |
| ------- | -------------- |
| isim | Neo |
| yaş | 20 |
| favRengi | Pastel Kırmızısı |
| boy | 175 |

  [^1]: JavaScript nesneleri, **adlandırılmış değerler** için kaplardır.

## Nesne Özellikleri

Nesne özelliklerine iki şekilde erişebilirsiniz.

```javascript
nesneIsmi.özellikIsmi
// veya
nesneIsmi['özellikIsmi']
```	

Bu örnek, kişi nesnemizin yaşına nasıl erişileceğini gösterir.

```javascript	
var karakter = {
  isim: "Neo", 
  yas: 20, 
  favRengi: "Pastel Kırmızısı", 
  boy: 175
};

var x = karakter.yas;
var y = karakter['yas'];

document.write(x);
document.write(y);
// 2020 dönderir.
```

JavaScript'in **uzunluk** özelliği, bir özellik veya dizedeki karakter sayısını saymak için kullanılır.[^2]

```javascript
var ders = {
  isim: "Nesneler", 
  dizi: 24
};

document.write(ders.isim.length); // 8 döner, çünkü "Nesneler" isimli dersin uzunluğu 8 karakterdir.
```

  [^2]: Nesneler, JavaScript'teki temel kavramlardan biridir.

## Nesne Yöntemleri

Bir **nesne yöntemi**, bir **fonksiyon** tanımı içeren bir özelliktir.

Bir nesne yöntemine erişmek için aşağıdaki sözdizimini kullanırız.

```javascript	
nesneIsmi.yontemIsmi()
```

Bildiğiniz gibi, **`document.write()`** veri çıktısı verir. **write()** işlevi aslında **document** nesnesinin bir yöntemidir.[^3]

```javascript
document.write("Bu bir metindir.");
```

  [^3]: Yöntemler, nesne özellikleri olarak depolanan işlevlerdir.

