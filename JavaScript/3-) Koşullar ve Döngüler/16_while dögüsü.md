# Süre Döngüsü


**while** ile, üç döngü ifademizin ikincisine geçme zamanı.[^1]

**while** döngüsü bir kod bloğu boyunca yinelenir, ancak yalnızca belirtilen koşul doğru olduğu sürece. 😉

**İşte sözdizimi:**

```javascript
while (koşul) {    
  // kod bloğu
}
```
  [^1]: Koşul, **true** veya **false** döndüren herhangi bir koşullu ifade olabilir.

<hr>

Tamam, sözdizimimiz var. Şimdi de gerçek bir örneğe bakalım:

```javascript	
var i = 0;

while (i <= 10) {
  document.write(i + "<br />"); // Alt alta 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 yazdırılır.
  
  i++;
} 
```

Bu kodda ki döngü, *i* 10'dan küçük veya 10'a eşit olduğu sürece çalışmaya devam edecektir. Ve döngü her çalıştığında **1** artacaktır.

Bu da, 0'dan 10'a kadar olan değerleri verecektir.[^2]

  [^2]: Koşulları yazarken dikkatli olun. Bir koşul her zaman doğruysa, **döngü sonsuza kadar çalışır!**

<hr>

Sonsuz döngüler iyi değildir. Ve bunun olmasının nedeni durumda kullanılan değişkeni arttırmayı unutmamızdır.[^3]

  [^3]: Bir süre döngüsündeki koşulun sonunda yanlış olduğundan emin olun.

