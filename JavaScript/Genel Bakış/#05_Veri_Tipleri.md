# Veri tipleri

**Veri tipi** terimi, bir programın çalışabileceği değer türlerini ifade eder. Gökyüzü, bir dizi farklı veri türünü tutabilen JavaScript değişkenlerinin sınırıdır -**sayılar, dizeler, diziler,** adını siz koyun. 🙃

Yine de basitten başlayalım.[^1]

Sayılar ondalıklı veya ondalıksız yazılabilir. Bunun gibi:

```javascript
var sayı = 42; // Ondalıksız bir sayı
```

```javascript
var fiyat = 55.55; // Ondalıklı bir sayı
document.write(fiyat);
```

  [^1]: Değişkenleri değiştirmek çok kolaydır, ona `sayı = 'biraz dize'` gibi başka bir veri türü değeri de atayabilirsin.

## Dizeler

*Tamam, hadi biraz ateşi açalım... 🔥*

JavaScript'te metinleri depolamak ve işlemek için dizeleri kullanabiliriz.
Bir dize, tırnak içine alınmış herhangi bir metin olabilir. Tek veya çift tırnak, onlarla tutarlı olduğunuz sürece önemli değil. Bunun gibi:

```javascript
var takma_isim = 'Neo';
var yazı = "Benim takma ismim Neo.";
```

> Yine de bir dize içinde tırnak kullanmak istersek ne olur? 

Sorun değil ki! 🙌 

Dizenin kendisini çevreleyen tırnak işaretleri ile eşleşmedikleri sürece, bir dize içinde tırnak işaretleri kullanabilirsin.[^2] Bir göz at derim:

```javascript
var yazı = "Benim takma ismim 'Neo'.";
```

  [^2]: Tek tırnak içinde `\"` veya `\'` gibi kaçış karakterini kullanarak çift tırnak içine çift tırnak alabilirsin.


Şimdi ters eğik çizgi `\` kaçış karakteri hakkında konuşmanın tam zamanı. Özel karakterleri dize karakterlerine dönüştürerek dizelere (ve bir dizi başka duruma) tırnak koymanız gerektiğinde kurtarmaya gelir.[^3] 🙂

İnceleyelim:

```javascript
var merhabaDe = 'Selam Dünya! \'Ben bir JavaScript geliştiricisiyim.\' ';
document.write(merhabaDe);
```

Kaçış karakteri `\` yalnızca tırnak işaretleri için değildir, dizelerin içine başka özel karakterler de koymanız gerektiğinde de çalışır!

* `\n`: yeni satır
* `\t`: tab karakteri
* `\r`: satır başı
* `\b`: geri alma
* `\f`: form besleme
* `\\`: ters eğik çizgi için kullanılır.
* `\'`: tek tırnak için kullanılır.
* `\"`: çift tırnak için kullanılır.

  [^3]: Bir dizeye tek tırnakla başlarsanız, onu da tek tırnakla bitirmeniz gerekir. Bu çift tırnak için de geçerlidir. Aksi takdirde, JavaScript'in kafası karışacaktır. Yazık ya bu JavaScript'e...

## Boole'ler

Sadece eğlenceli değil, JavaScript'teki Boolean'lar, **doğru** veya **yanlış** olmak üzere iki değerden birine sahip olmanıza izin vererek yararlı bir işlev sunar.

Bu nedenle, Evet/Hayır, açık/kapalı veya doğru/yanlış gibi iki olası değerden yalnızca birine sahip olabilen bir veri türüne ihtiyacınız olduğunda, Bay Boolean'dan başkasına bakmayın.[^4] 😅 

Örneğe bakalım:

```javascript
var aktifMi = true; 
var tatilMi = false;
```

  [^4]: 0 (sıfır), null, tanımsız, boş dizenin Boole değeri yanlıştır. "Gerçek" değeri olan her şey doğrudur.
