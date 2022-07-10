# `if` eğer ifadesi

Aferin! Büyük ilerleme kaydediyorsun. 😁

Genellikle kod yazarken, farklı koşullara göre farklı eylemler gerçekleştirmek isteriz.

Ve burada **koşullu ifadeler** devreye giriyor.

Ele alınması gereken bir sürü farklı koşul ifadesi var, ancak en kullanışlı olanlardan biriyle başlıyoruz: `if` (eğer) ifadesi.

Belirtilen bir koşul doğruysa yürütülmesini istediğimiz bir kod bloğunu belirtmek için **if** kullanırız.

```javascript	
if (koşul) {
  // koşul doğruysa yürütülen kod bloğu
}
```

İfadeler yalnızca belirtilen koşul **doğru**ysa yürütülür. Bir örneğe bakalım:

```javascript
var numara1 = 7;
var numara2 = 10;

if (numara1 < numara2) {
  alert("JavaScript'i öğrenmek kolaydır."); // çalışır.
}
```

İşte if ifadesi hakkında biraz daha ayrıntı.

Bu, **yanlış** bir koşullu ifadeye bir örnektir:

```javascript
var numara1 = 7;
var numara2 = 10;

if (numara1 > numara2) {
  alert("JavaScript'i öğrenmek kolaydır."); // çalışmaz
}
```

Koşul **false** olarak değerlendirildiği için, uyarı ifadesi atlanır ve program, if ifadesinin kapanış küme parantezinden sonraki satırla devam eder.[^1]

[^1]: `if` küçük harflerle yazılır. Büyük harfler (If veya IF) çalışmayacaktır.