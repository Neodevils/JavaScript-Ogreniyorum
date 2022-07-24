# Aritmetik Operatörler

İsim biraz boş olabilir, ancak **aritmetik operatörler**, sayılar üzerinde (hem değişkenler hem de değişmezlerde) aritmetik işlevleri yerine getirir.

| Operatör | İşlev | Örnekler |
| -------- | ---- | -------- |
| + | Toplama | `25 + 5 = 30` |
| - | Çıkarma | `25 - 5 = 20` |
| * | Çarpma | `10 * 20 = 200` |
| / | Bölme | `20 / 2 = 10` |
| % | Mod | `56 % 3 = 2` |
| ++ | Artırma | `var a = 10; a++; Şimdi a = 11` |
| -- | Azaltma | `var b = 20; b--; Şimdi b = 19` |

## Toplama İşlemi
Aşağıda iki sayının toplamını belirleyen toplama operatörünü (+) çalışırken görebilirsin.

```javascript
var x = 10 + 5;
document.write(x); // 15
```

İstediğin veya ihtiyaç duyduğun kadar sayı veya değişken ekleyebilirsin.[^1]

```javascript
var x = 10;
var y = x + 5 + 15;
document.write(y); // 30
```
  
  [^1]: `eval("10 * 20 + 8")` gibi bir dize ifadesi argümanı alan ve sonucu döndüren **eval()** işlevini kullanarak bir dize ifadesinin sonucunu alabilirsin. Argüman boşsa, tanımsız döndürür.

## Çarpma işlemi

JavaScript matematikte de oldukça iyidir!

Bir sayıyı diğeriyle çarpmak için `*` operatörünü kullanırız.[^2]
Bunun gibi:
  
```javascript
var x = 10 * 5;
document.write(x); // 50
```

  [^2]: `10 * '5'` veya `'10' * '5'` aynı sonucu verecektir. Ancak, `'neo' * 5` gibi sayı olmayan dize değerleriyle bir sayıyı çarpmaya çalışmak **NaN** (Sayı Değil) döndürür.

## Bölme işlemi

Bölme işlemlerini gerçekleştirmek için / operatörünü kullanırız.[^3]
Bunun gibi:

```javascript
var x = 10 / 5;
document.write(x); // 2
```

  [^3]: 0'a bölmenin olabileceği durumlara dikkat edin, yaptığınızda işler biraz karışır! 😂

## Modül

Kalanları konuşma zamanı. Okulda onlardan nefret ettin, ama burada oldukça kolaylar, ciddiyim bak.

Modül `%` operatörü bölme kalanını (geriye kalanı) döndürür.[^4]

Bunun gibi:

```javascript	
var x = 10 % 5;
document.write(x); // 0
```

0 kalanını döndürür.

  [^4]: JavaScript'te modül operatörünü tam sayılarda VE ondalıklı sayılarında kullanabiliriz.

## Artırma ve Azaltma

> Bekle bir dakika artışı duydum gibi de, azaltma ne be?

Bazılarınız bunu söylediğini duyuyorum gibi. 😅

### Artış ++

Artırma operatörü, işlenenin sayısal değerini 1 artırır. İşlenenin önüne yerleştirildiğinde, artan değeri döndürür. Ondan sonra yerleştirildiğinde, orijinal değeri döndürür ve ardından işleneni artırır.

### Azaltma --

Azaltma operatörü, işlenenin sayısal değerini 1 azaltır. İşlenenin önüne yerleştirildiğinde, azaltılan değeri döndürür. İşlenenden sonra yerleştirildiğinde, orijinal değeri döndürür ve ardından işleneni azaltır.[^5]

  [^5]: Tıpkı okulda öğrendiğiniz matematik gibi, parantez kullanarak aritmetik işlemlerin sırasını değiştirebilirsiniz.
  Bunun gibi: `var x = (100 + 50) * 3;`

Bazı örnekler:

| Operatör | Açıklama | Örnek | Sonuç |
| -------- | -------- | ---- | ----- |
| var++ | Artış Sonrası | `var a = 0, var b = 10; var a = b++` | a = 10 ve b = 11 |
| ++var | Artış Öncesi | `var a = 0, var b = 10; var a = ++b` | a = 11 ve b = 11 |
| var-- | Azalış Sonrası | `var a = 0, var b = 10; var a = b--` | a = 10 ve b = 9 |
| --var | Azalış Öncesi | `var a = 0, var b = 10; var a = --b` | a = 9 ve b = 9 |
