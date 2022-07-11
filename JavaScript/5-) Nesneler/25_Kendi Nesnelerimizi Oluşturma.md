# Nesne Oluşturucu

Önceki derste, nesne değişmezi (veya başlatıcı) sözdizimini kullanarak bir nesne yarattık.

```javascript
var kisi = {
  isim: "Neo", 
  yas: 20, 
  favRenk: "Pastel Kırmızı",
};
```

Bu, yalnızca tek bir nesne oluşturmanıza olanak tanır.

Bazen, tek bir türden çok sayıda nesne oluşturmak için kullanılabilecek bir **"nesne türü"** ayarlamamız gerekir.

Bir "nesne türü" yaratmanın standart yolu, bir nesne **oluşturucu fonksiyonunu** kullanmaktır.

```javascript	
function kisi(isim, yas, renk) {
  this.isim = isim;
  this.yas = yas;
  this.favRenk = renk;
}
```	

*Yukarıdaki fonksiyon (kişi), parametreleri alan ve bunları nesne özelliklerine atayan bir nesne oluşturucudur.*[^1]

  [^1]: **`this`** anahtar sözcüğü, **geçerli nesneyi** ifade eder. Bunun bir değişken olmadığını unutmayın. **this** bir anahtar kelimedir ve değeri değiştirilemez.

## Nesneler Oluşturma

Bir nesne oluşturucunuz olduğunda, aynı türde yeni nesneler oluşturmak için **new** anahtar sözcüğünü kullanabilirsin.

```javascript	
function kisi(isim, yas, renk) {
  this.isim = isim;
  this.yas = yas;
  this.favRenk = renk;
}

var kisi1 = new kisi("Neo", 20, "kırmızı");
var kisi2 = new kisi("Mica", 16, "mavi");

document.write(kisi1.yas); // 20 döndürür.
document.write(kisi2.isim); // Mica döndürür.
```

***kisi1** ve **kisi2** artık kişi türünün nesneleridir. Özellikleri karşılık gelen değerlere atanır.*

<hr>

Aşağıdaki örneği bir göz önünde bulundur.

```javascript
function kisi(isim, yas) {
  this.isim = isim;
  this.yas = yas;
}

var Neo = new kisi("Neo", 20);
var Mica = new kisi("Mica", 16);

document.write(Neo.yas); // 20 döndürür.
```

Daha önce yaptığımız gibi **nokta sözdizimini** kullanarak nesnenin özelliklerine erişiriz.[^2]

| Nesnenin İsmi | Özelliğin İsmi |
| ----------- | ----------- |
| **Neo** | .isim |
| **Neo** | .yas |
| **Mica** | .isim |
| **Mica** | .yas |

  [^2]: Nesnelerin yaratılışını anlamak çok önemlidir.

