# Döngüler

Döngüler, bir kod bloğunu birkaç kez çalıştırabilir. Aynı kodu tekrar tekrar çalıştırmak ve her seferinde farklı bir değer eklemek istediğinizde kullanışlıdırlar.

JavaScript'te üç tür döngü vardır: `for`, `while` ve `do...while`.

Burada klasik for döngüsüyle başlayacağız.[^1]

**İşte sözdizimini inceleyelim:**

```javascript
for (ifade 1; ifade 2; ifade 3) {
  // yürütülecek kod bloğu
}
```

Ve işte çalıştığında ne olacağını aşağıda açıkladık:

- İfade 1, döngü (kod bloğu) başlamadan önce yürütülür.
- İfade 2, döngüyü (kod bloğu) çalıştırma koşulunu tanımlar.
- Döngü (kod bloğu) yürütüldükten sonra her seferinde ifade 3 yürütülür.

[^1]: Gördüğünüz gibi, **klasik for döngüsünün üç** bileşeni veya ifadesi vardır.

## for (için) Döngüsü

Şimdi teoriyi anladık, gelin bir özel örneğe bakalım.

Bu örnek, 1'den 5'e kadar sayıları yazdıran bir **for döngüsü** oluşturacak:

```javascript	
for (var i = 1; i <= 5; i++) {
  document.write(i + "<br>"); // Alt alta 1, 2, 3, 4, 5 yazdırılır.
}
```

> Peki gerçekte ne oluyor?

Bu örnekte, 
- **İfade 1**, döngü başlamadan önce bir değişken ayarlar (var i = 1).
- **İfade 2**, döngünün çalışması için koşulu tanımlar (5'ten küçük veya ona eşit olmalıdır).
- **İfade 3**, döngüdeki kod bloğu her çalıştırıldığında bir değeri (i++) artırır.

<hr>

**İfade 1** isteğe bağlıdır ve değerleriniz döngü başlamadan önce ayarlanmışsa, dışarıda bırakılabilir.

```javascript	
var i = 1;
for ( ; i <= 5; i++) {
  document.write(i + "<br />"); // Alt alta 1, 2, 3, 4, 5 yazdırılır.
}
```

<hr>

Ayrıca, **ifade 1**'de, bunları ayırmak için **virgül** kullanarak birden fazla değer başlatabilirsiniz.[^2]

```javascript
for (i = 1, text = ""; i <= 5; i++) {
  text = i;

  document.write(i + "<br />"); // Alt alta 1, 2, 3, 4, 5 yazdırılır.
}
```

  [^2]: ES6, diğer for döngü türlerini tanıtır; bunları daha sonra ES6 derslerinde göreceksin.

<hr>

**İkinci ifade** true dönerse döngü yeniden başlar, false dönerse döngü biter.

İkinci ifade de isteğe bağlıdır, ancak yalnızca döngünün içine bir ara verirseniz... *Aksi takdirde, döngü asla bitmez!*

İlk değişkeni değiştirmek için **üçüncü ifade** kullanılır. Negatif artış (i--), pozitif artış (i = i + 15) dahil her şeyi yapabilir.[^3]

Üçüncü ifade de isteğe bağlıdır, ancak yalnızca değerlerinizi döngü içinde artırırsanız. Bunun gibi:

```javascript
var i = 0;

for (; i < 10; ) {
  document.write(i);

  i++; // 0123456789 dönderir.
}
```

  [^3]: Birden çok **iç içe** `for` döngüsüne sahip olabilirsiniz.

