# Yöntemler


**Yöntemler**, nesne özellikleri olarak depolanan işlevlerdir.

Bir nesne yöntemi oluşturmak için aşağıdaki sözdizimini kullanın:

```javascript
metodIsmi = function() { kod satırları };
```

Aşağıdaki sözdizimini kullanarak bir nesne yöntemine erişin:

```javascript
nesneIsmi.metodIsmi()
```	

Yöntem, bir nesneye ait olan bir işlevdir. **this** anahtar sözcüğü kullanılarak referans alınabilir.

**this** anahtar sözcüğü, geçerli nesneye referans olarak kullanılır; bu, onu kullanarak nesnelerin özelliklerine ve yöntemlerine erişebileceğiniz anlamına gelir.

Tanımlama yöntemleri yapıcı işlevi içinde yapılır.

**Örneğin:**

```javascript
function kisi(isim, yas) {
  this.isim = isim;
  this.yas = yas;
  this.isimDegistir = function (isim) {
    this.isim = isim;
  }
}

var k = new kisi("Twenty-Four", 20);
k.isimDegistir("Hedy");

document.write(k.isim);
// "Hedy" değerini yazdırır.
```

Yukarıdaki örnekte, bir parametre **isim** alan ve onu nesnenin **isim** özelliğine atayan bir fonksiyon olan kişimiz için **isimDegistir** adında bir yöntem tanımladık.

**this.isim**, nesnenin isim özelliğini ifade eder.[^1]

  
  [^1]: **isimDegistir** yöntemi, nesnenin **isim** özelliğini argümanına değiştirir.

<hr>

Ayrıca, fonksiyonu yapıcı işlevin dışında tanımlayabilir ve onu nesneyle ilişkilendirebilirsiniz.

```javascript
function kisi(isim, yas) {
  this.isim = isim;
  this.yas = yas;
  this.dogumSenesi = dogumYili;
}

function dogumYili() {
  return 2022 - this.yas;
}
```

Gördüğünüz gibi, **dogumYili** fonksiyonuna nesnenin **dogumSenesi** özelliğini atadık.
***this*** anahtar sözcüğü, yöntemi çağıracak olan nesnenin **yas** özelliğine erişmek için kullanılır.[^2]

  [^2]: Bir nesneye atanırken işlevin parantezlerini yazmanın gerekli olmadığını unutmayın.

<hr>

Yöntemi her zamanki gibi çağırın.

```javascript
function kisi(isim, yas) {
  this.isim = isim;
  this.yas = yas;
  this.dogumSenesi = dogumYili;
}

function dogumYili() {
  return 2022 - this.yas;
}

var k = new kisi("X", 31);

document.write(k.dogumSenesi()); // 1991
```	

Yöntemi, fonksiyon adı yerine yapıcı fonksiyonda belirttiğiniz özellik adıyla çağır.

