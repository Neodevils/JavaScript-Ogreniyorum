# Karşılaştırma Operatörleri

Değişkenlerin veya değerlerin farklı olup olmadığını öğrenmek için mantıksal ifadelerde karşılaştırma operatörlerini kullanabiliriz.

**Doğru** ya da **yanlış** alırsınız. Örneğin, eşittir `==` operatörü, işlenenlerin değerlerinin eşit olup olmadığını kontrol eder.[^1]	

```javascript
var a = 10;

console.log(a == 10); // true
```

  [^1]: Tüm veri türlerini karşılaştırma operatörleriyle karşılaştırabilirsiniz, her zaman **doğru** veya **yanlış** döndürürler.

Karşılaştırma operatörlerinin dökümünü görmek için bu tabloya bir göz at.[^2]

| Operatör | Açıklama | Örnek | Sonuç |
| -------- | -------- | ---- | ----- |
| == | Eşittir | 5 == 10 | yanlış |
| != | Eşit değil | 5 != 10 | doğru |
| === | Birebir aynı | 5 === 10 | yanlış |
| !== | Birebir aynı değil | 5 !== 10 | doğru |
| < | Küçüktür | 5 < 10 | doğru |
| > | Büyüktür | 5 > 10 | yanlış |
| <= | Küçük veya eşittir | 5 <= 10 | doğru |
| >= | Büyük veya eşittir | 5 >= 10 | yanlış |

  [^2]: Operatörleri kullandığımızda hatırlamamız gereken önemli bir şey, bunların yalnızca **aynı veri türünü** karşılaştırırken çalıştıklarıdır; sayılarla sayılar, dizelerle dizeler, anladınız siz 🙃.

