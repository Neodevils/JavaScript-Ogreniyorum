# Uyarı, İstem, Onayla Fonksiyonları

JavaScript, Uyarı, İstem ve Onayla kutuları olmak üzere üç tür açılır kutu sunar.

## `alert()` Uyarı Kutusu

Bilginin kullanıcıya ulaşmasını sağlamak istediğinizde bir **uyarı kutusu** kullanabiliriz.

Bir uyarı kutusu açıldığında, kullanıcının devam etmek için **Tamam**'ı tıklaması gerekir.

**Uyarı** işlevi, açılır kutuda görüntülenen metin olan tek bir parametre alır.

**Örnek:**

```javascript	
alert("Derse devam etmek ister misin?");
```

Bir açılır kutu içinde **satır sonlarını** görüntülemek için ***ters eğik çizgi*** ve ardından ***n*** karakteri kullan.[^1]

```javascript
alert("Selam!\nNasılsın?");
```

  [^1]: Kullanıcı, yalnızca Tamam'ı tıkladıktan sonra sayfayı kullanmaya devam edebileceğinden, uyarı kutularını kullanırken dikkatli ol.

## `prompt()` İstem Kutusu

Kullanıcının bir sayfaya girmeden önce bir değer girmesini sağlamak için genellikle bir **bilgi istemi kutusu** kullanılır.

Bir istem kutusu açıldığında, kullanıcının giriş değerini girdikten sonra devam etmek için Tamam veya İptal'i tıklaması gerekir.
Kullanıcı Tamam'ı tıklatırsa, kutu **giriş değerini** döndürür. Kullanıcı İptal'i tıklatırsa kutu **boş** döner.[^2]

`promt()` yöntemi **iki parametre** alır.
- Birincisi, metin kutusunda görüntülemek istediğiniz yazıdır.
- İkincisi, metin kutusunda görüntülenecek varsayılan bir dizedir (isteğe bağlı).

**Örnek:**

```javascript
var kullanici = prompt("Lütfen kullanıcı ismini gir.", "NeoAIChan");

alert(kullanici);
```

  [^2]: Bir istem kutusu açıldığında, kullanıcının bir giriş değeri girdikten sonra devam etmek için "Tamam" veya "İptal"e tıklaması gerekir. Bu yöntemi aşırı kullanma, çünkü kutu kapanana kadar kullanıcının sayfanın diğer bölümlerine erişmesini engelliyor.

## `confirm()` Onay Kutusu

Kullanıcının bir şeyi doğrulamasını veya kabul etmesini sağlamak için genellikle bir **onay kutusu** kullanılır.
Bir onay kutusu açıldığında, kullanıcının devam etmek için Tamam veya İptal'i tıklaması gerekir.

Kullanıcı Tamam'ı tıklatırsa kutu **true** değerini döndürür. Kullanıcı İptal'i tıklatırsa kutu **false** döndürür.[^3]

**Örnek:**

```javascript
var sonuc = confirm("Dersten gerçektende ayrılmak istiyor musun?");

if (sonuc == true) {
  alert("Geldiğin için teşekkürler.");
} else {
  alert("Kaldığın için teşekkürler.");
}
```

  [^3]: Bu yöntemi aşırı kullanma, çünkü kutu kapanana kadar kullanıcının sayfanın diğer bölümlerine erişmesini de engelliyor.

