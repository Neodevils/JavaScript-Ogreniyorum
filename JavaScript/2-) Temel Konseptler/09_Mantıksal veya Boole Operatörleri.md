# Mantıksal operatörler

Boole Operatörleri olarak da bilinen **Mantıksal Operatörler** (veya Vulcan Operatörleri… Uh, bu doğru değil gibi) bir ifadeyi değerlendirir ve **doğru** veya **yanlış** döndürür.

Mantıksal operatörler **(VE, VEYA, DEĞİL)** hakkında daha fazla ayrıntı görmek için aşağıdaki tabloya bakalım[^1]:

[^1]: Her türlü veriyi kontrol edebilirsiniz; karşılaştırma operatörleri her zaman doğru veya yanlış döndürür.

| Mantıksal Operatörler | Açıklama |
| -------------------- | ------- |
| `&&` | Her iki işlenen de doğruysa true döndürür |
| `\|\|` | İşlenenlerden biri doğruysa true döndürür |
| `!` | İşlenenler yanlışsa true, işlenenler doğruysa false döndürür |

Bir örneğe bakalım. Burada AND operatörüne iki Boole ifadesi bağladık.

## Mantıksal operatörler

Bir örneğe bakalım. Burada **AND** operatörüne iki Boole ifadesi bağladık.

```javascript
( 4 > 3 ) && ( 5 < 10 ); // true
```

Bu ifadenin **doğru** olması için her iki koşulun da **doğru** olması gerekir.
- İlk koşul, 4'ün 3'den büyük olup olmadığını belirler, ki bu **doğru**dur.
- İkinci koşul, 5'in 10'dan küçük olup olmadığını belirler, bu da **doğru**dur.

Ta da! 🎉 Bütün ifade **doğru**dur...çok mantıklı!

## Koşullu (Üçlü) Operatör

Koşullu veya Üçlü operatörler, bir koşula dayalı olarak bir değişkene bir değer atar.

Sözdizimi şöyle görünür:

```javascript
değişken = (koşul) ? değer1 : değer2;
```	

**Ve işte bir örnek:**

```javascript	
var yaş = 42;
var yetişkinMi = ( yaş < 18 ) ? "Çok genç.": "Yetişkin.";

document.write(yetişkinMi);
```

Yaş değişkeni 18'in altında bir değerse, yetişkinMi değişkeninin değeri "Çok genç" olacaktır. Aksi takdirde yetişkinMi'nin değeri "Yetişkin." olacaktır.[^2]

  [^2]: Mantıksal operatörlerle, istediğiniz veya ihtiyaç duyduğunuz kadar çok ifade bağlayabilirsin.

