# `else` değilse ifadesi

Doğru, if ifadesini kullanan bir kod bloğu false olarak değerlendirdiğinde eylemin atlandığını gördük. 

> Peki ya başka bir şeyin olmasını istiyorsak?

Eh, elbette "else" ifadesini kullanıyoruz!

Koşul **yanlış**sa yürütülecek bir kod bloğu belirtmek için `else` ifadesini kullanabiliriz.[^1]

Bunun gibi:

```javascript	
if (koşul) {
  // koşul doğruysa yürütülen kod bloğu
} else {
  // koşul yanlışsa yürütülen kod bloğu
}
```

  [^1]: Koşul altındaki kod yalnızca bir komut içeriyorsa kıvrımlı ayraçları atlayabilirsiniz.

Birlikte çalışan **if** ve **else** ifadelerinin başka bir örneği:

```javascript
var num1 = 7;
var num2 = 10;

if ( num1 > num2 ) {
  alert("İlk koşulum.");
} else {
  alert("İkinci koşulum.");
}
```

Bu örneği tercüme edelim. Diyor ki:
- num1, num2'den büyükse, "İlk koşulum." uyarısı;
- Aksi takdirde, "İkinci koşulum." uyarısı.

Böylece tarayıcı, 7'nin 10'dan büyük olmadığı için ikinci koşulu yazdıracaktır.[^2]

  [^2]: Bu kontrolü yapmanın başka bir yolu var mı? Evet, şöyle: `operatör: a > b ? alert(a) : alert(b).`

