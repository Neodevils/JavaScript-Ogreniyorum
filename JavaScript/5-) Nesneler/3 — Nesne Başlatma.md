# Nesne Başlatma

Tek nesneler oluşturmak için **nesne değişmez** değerini veya **başlatıcı** sözdizimini kullanırız.[^1]

```javascript
var Neo = {isim: "Neo", yas: 20};
var Mica = {isim: "Mica", yas: 16};
```

  [^1]: Nesneler, bir nesneyi tanımlamak için kullanılan özelliklerden oluşur. Nesne özelliklerinin değerleri, ilkel veri türlerini veya diğer nesneleri içerebilir.

## Nesne Başlatıcıları Kullanma

Boşluklar ve satır sonları önemli değildir. Bir nesne tanımı birden çok satıra yayılabilir.

```javascript	
var Neo = {
  isim: "Neo", 
  yas: 20
};
var Mica = {
  isim: "Mica", 
  yas: 16
};
```

Nesne nasıl oluşturulursa oluşturulsun, özelliklere ve yöntemlere erişim sözdizimi değişmez.[^2]

```javascript
var Neo = {
  isim: "Neo", 
  yas: 20
};
var Mica = {
  isim: "Mica", 
  yas: 16
};

document.write(Neo.yas); // 20 döndürür.
```

  [^2]: İkinci erişim sözdizimini unutmayın: Neo['yas'].

