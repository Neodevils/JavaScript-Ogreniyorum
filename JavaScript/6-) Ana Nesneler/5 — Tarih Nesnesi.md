# `setInterval()` Aralığı Ayarlama

`setInterval()` yöntemi, bir işlevi çağırır veya belirtilen aralıklarla (milisaniye cinsinden) bir ifadeyi değerlendirir.

``clearInterval()`` çağrılıncaya veya pencere kapanana kadar işlevi çağırmaya devam edecektir.[^1]

**Örneğin:**

```javascript
function UYARIM() {
  alert("Merhaba!");
}

setInterval(UYARIM, 3000); // 3 saniye aralıkla UYARIM() fonksiyonunu çağırılır.
```

  [^1]: Fonksiyonu **setInterval** yöntemine aktarırken işlevin **adını** parantez olmadan yazın.

# ``Date()`` Tarih Nesnesi


**Date** nesnesi, tarihlerle çalışmamızı sağlar.

Tarih bir yıl, bir ay, bir gün, bir saat, bir dakika, bir saniye ve bir milisaniyeden oluşur.

**new Date()** kullanarak, geçerli tarih ve saatle yeni bir tarih nesnesi oluşturalım

```javascript	
var t = new Date(); //t geçerli tarih ve saati saklar.
```

Tarihleri başlatmanın diğer yolları, **belirtilen tarih ve saatten** yeni tarih nesnelerinin oluşturulmasına izin vermesi.[^2]

```javascript	
new Date(milliseconds);
new Date(dateString);
new Date(year, month, day, hours, minutes, seconds, milliseconds);
```

  [^2]: JavaScript tarihleri, 01 Ocak 1970 00:00:00 Evrensel Saat'ten (UTC) milisaniye cinsinden hesaplanır. Bir gün 86.400.000 milisaniye içerir.

**Örneğin:**
  
```javascript
//Cuma Ocak 02 1970 00:00:00
var t1 = new Date(86400000); 

//Cuma Ocak 02 2015 10:42:00
var t2 = new Date("January 2, 2015 10:42:00");

//Sat Jun 11 1988 11:42:00
var t3 = new Date(88,5,11,11,42,0,0);
```

> JavaScript, 0'dan 11'e kadar olan ayları sayar. Ocak 0 ve Aralık 11'dir. Tarih nesneleri dinamik değil, statiktir. Bilgisayar saati ilerliyor, ancak tarih nesneleri oluşturulduktan sonra değişmiyor.

## Tarih Yöntemleri

Bir Date nesnesi oluşturulduğunda, bir dizi **yöntem**, üzerinde işlem yapılmasını mümkün kılar.

| Yöntem | Açıklama |
| ------ | -------- |
| `getFullYear()` | Yılı döndürür. |
| `getMonth()` | Ayı döndürür. |
| `getWeek()` | Haftayı döndürür. |
| `getDate()` | Günü döndürür. |
| `getDay()` | Haftanın gününü döndürür. |
| `getHours()` | Saati döndürür. |
| `getMinutes()` | Dakikayı döndürür. |
| `getSeconds()` | Saniyeyi döndürür. |
| `getMilliseconds()` | Milisaniyeyi döndürür. |

**Örneğin:**

```javascript	
var t = new Date();
var saat = t.getHours();

console.log(saat); //Saat değerini çıktı olarak gösterir. Mesela bunu yazdığımızda, 13 olarak çıktısını görebiliriz. Çünkü saat 13'te olduğu için.
```

Şimdi de tarayıcımızda şu an ki saatini programımızda görebiliriz.

```javascript
function saatiYaz() {
  var t = new Date();
  var saat = t.getHours();
  var dakika = t.getMinutes();
  var saniye = t.getSeconds();
  
  document.body.innerHTML = saat + ":" + dakika + ":" + saniye;
}

setInterval(saatiYaz, 1000); //1 saniye aralıkla saatiYaz() fonksiyonunu çağırır.
```

Date nesnesinden o anki zamanı alan ve ekrana yazdıran **saatiYaz()** fonksiyonunu tanımladık.
Daha sonra **setInterval** yöntemini kullanarak işlevi saniyede bir kez çağırdık ve böylelikle mesajı yeniledik.[^3]

  [^3]: **innerHTML** özelliği, bir öğenin HTML içeriğini ayarlar veya döndürür. Bizim durumumuzda, belgemizin gövdesinin HTML içeriğini değiştiriyoruz. Bu, içeriği ekrana art arda yazdırmak yerine her saniye içeriğin üzerine yazıyoruz.

