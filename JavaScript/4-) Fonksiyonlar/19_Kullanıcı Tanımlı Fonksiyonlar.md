# JavaScript Fonksiyonları

JavaScript **fonksiyonu**, belirli bir görevi gerçekleştirmek için tasarlanmış bir kod bloğudur.[^1]

Fonksiyonları kullanmanın ana avantajları:

* Kodun **yeniden kullanımı**: Kodu bir kez tanımlayın ve birçok kez kullanın.

* Farklı sonuçlar elde etmek için aynı kodu farklı **argümanlarla** birçok kez kullanın.

  [^1]: Bir JavaScript işlevi, "bir şey" onu çağırdığında yürütülür.

## Fonksiyon Tanımlama

Bir JavaScript işlevi tanımlamak için, `function` anahtar sözcüğünü, ardından bir ad ve ardından bir dizi **parantez()** kullanırız.

İşlev tarafından yürütülecek kod, küme parantezleri {} içine yerleştirilir.[^2]

```javascript
function isim() {
  // İşlevleri buraya yazarız
}
```

  [^2]: İşlev adları harfler, rakamlar, alt çizgiler ve dolar işaretleri içerebilir (değişkenlerle aynı kurallar).

## Fonksiyon Çağırma

Fonksiyonu yürütmek için onu çağırman gerekir.
Bir fonksiyonu çağırmak için, fonksiyonun adıyla başlar, ardından parantez içindeki argümanlarla takip ederiz.[^3]

**Örneğin:**

```javascript
function fonksiyonum() {
  alert("Fonksiyonu çağırıyorum!");
}

fonksiyonum();
```

  [^3]: Fonksiyonu çağırdıktan sonra her zaman ifadeyi **noktalı virgülle** bitirmeyi unutmayın.

<hr>

İşlev tanımlandıktan sonra, JavaScript onu istediğin kadar çağırmana izin verir.[^4]

```javascript
function fonksiyonum() {
  alert("Alert box!");
}

fonksiyonum();

// bazı diğer kodlar

fonksiyonum();
```

  [^4]: Bu sözdizimini kullanarak da bir işlevi çağırabiliriz: `fonksiyonum.call()`. Aradaki fark, bu şekilde çağırırken **'this'** anahtar sözcüğünü bir işleve geçirmiş olmamızdır. Bunu daha sonra öğreneceğiz. 🙃

